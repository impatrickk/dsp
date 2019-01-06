[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

Importing the necessary modules:

    import nsfg
    import math

Reading the data and filtering the data for live births:

    preg = nsfg.ReadFemPreg()
    live = preg[preg.outcome == 1]
    
Creating two groups, one for first borns and another for all others:

    firsts = live[live.birthord == 1]
    others = live[live.birthord != 1]
    
    
First look at comparing the two groups, I looked at the mean for the total weight:

    print("The total weight mean of first borns are:", round(firsts.totalwgt_lb.mean(),3))
    print("The total weight mean of others are:", round(others.totalwgt_lb.mean(),3))

Our output tells us that "the total weight mean of first borns are: 7.201" abd "the total weight mean of others are: 7.326"
    
Next, using the prebuilt function in the textbook, I looked at the Cohen's d to quanitfy the differences and see the effect size of the two groups:

    def CohenEffectSize(group1, group2):
        diff = group1.mean() - group2.mean()
        var1 = group1.var()
        var2 = group2.var()
        n1, n2 = len(group1), len(group2)
        pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
        d = diff / math.sqrt(pooled_var)
        return d
        
        round(CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb),3)
        
Our Cohen's d result of -0.089 standard deviations is greater than 0.029 standard deviations for the difference in pregnanc length (in terms of absolute value), but it is still a very small effect size, relative to the difference in height between men and women (1.7 standard deviations).
