[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

Importing:

    import nsfg
    import math
    import thinkstats2
    import thinkplot

Reading the response file and creating a pmf with the respondent variable "numkdhh":

    resp = nsfg.ReadFemResp()
    pmf = thinkstats2.Pmf(resp.numkdhh, label = "NUMKDHH")

Putting the Number of Kids and their respective PMF's onto a graph, based on the respondent variable.
 
    thinkplot.Pmf(pmf)
    thinkplot.Config(xlabel = "Number of Kids", ylabel = "PMF")

Creating a function for making a "biased" pmf by multiplying the pmf for each "Number of Kids" value by their respective number of kids. Plotting the biased pmf and the original/actual pmf on the same plane.

    def BiasPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)
    for x, p in pmf.Items():
        new_pmf.Mult(x,x)
    new_pmf.Normalize()
    return new_pmf
    biased_pmf = BiasPmf(pmf, label= "biased")
    thinkplot.PrePlot(2)
    thinkplot.Pmfs([pmf, biased_pmf])
    thinkplot.Show(xlabel = "Number of Kids", ylabel = "PMF")

The final result of the graph can be found [here](https://github.com/impatrickk/dsp/blob/master/statistics/actual%20vs%20bias.png).

Lastly, used pmf.Mean() and biased_pmf.Mean() to get the mean of each pmf at 1.024205155043831 and 2.403679100664282 respectively.
