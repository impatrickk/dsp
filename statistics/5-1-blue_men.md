[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

Importing:

    import scipy.stats
      
Creating a converter for feet/inches to centimeters. Using the converter to find the CDF value for the lower and upper ranges: 
     
    def to_cent(feet,inches):
        cent = feet*30.48 + inches*2.54
        return cent

    lower = to_cent(5,10)
    upper = to_cent(6,1)

    print(lower)
    print(upper)
    
    
Using the values, I use scipy.stats.norm to find the CDF of the lower and upper bounds. Because CDF is a cumulative distribution, we need to subtract the upper from lower to find the range in between them:
    
    cdf_lower = scipy.stats.norm.cdf(lower, loc=178, scale=7.7)
    cdf_upper = scipy.stats.norm.cdf(upper, loc=178, scale=7.7)
    100*(cdf_upper - cdf_lower)
