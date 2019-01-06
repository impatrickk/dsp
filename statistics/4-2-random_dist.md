[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

Importing:

    import numpy as np
    import random
    import thinkstats2
    import thinkplot
    
Creating a sample with 1,000 values ranging from 0-1 in uniform distribution:
    
    sample = np.random.random(1000)
    
Creating a PMF of the sample and graphing it. The output is uniform blocks and the graph can be seen [here](https://github.com/impatrickk/dsp/blob/master/statistics/PMF.png)
    
    pmf = thinkstats2.Pmf(sample, label = "PMF")
    thinkplot.Pmf(pmf)
    thinkplot.Show(xlabel = "Value", ylabel = "Probability")
    
Creating a CDF of the sample and graphining it. The output is (almost) a straight line with a direct relationship with the x and y axis. This is a CDFcharacterisitic of a uniform distribution. The result can be seen [here](https://github.com/impatrickk/dsp/blob/master/statistics/CDF.png)
    
    cdf = thinkstats2.Cdf(sample, label = "CDF")
    thinkplot.Cdf(cdf)
    thinkplot.Show(xlabel = "Percentiles", ylabel = "CDF")
    
I plotted both on the same plane so we can see the results together. a straight horizontal line of the PMF shows that with each random value, the probability of hitting that number are (almost) equal. The results can be seen [here](https://github.com/impatrickk/dsp/blob/master/statistics/Both.png)
    
    thinkplot.PrePlot(2)
    thinkplot.Pmf(pmf)
    thinkplot.Cdf(cdf)
