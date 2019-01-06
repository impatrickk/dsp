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
