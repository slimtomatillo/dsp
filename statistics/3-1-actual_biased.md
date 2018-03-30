[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

#setting up the PMF
```
resp = nsfg.ReadFemResp()
numkd_freq = resp['numkdhh']
pmf_kds = thinkstats2.Pmf(numkd_freq,label='actual')
```

#plot the PMF of actual distribution
```
thinkplot.Hist(pmf_kds)
thinkplot.Pmf(pmf_kds)
```

#set up biased PMF
```
def BiasedPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)
    for x,p in pmf.Items():
        new_pmf.Mult(x,x)
    new_pmf.Normalize()
    return(new_pmf)

biased_pmf_kds = BiasedPmf(pmf_kds, label='observed')
```

#plot actual and biased PMFs on same graph
```
thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf_kds,biased_pmf_kds])
thinkplot.Show(xlabel='number of kids',ylabel='PMF')
```

#compare means of actual and biased PMFs
```
print('The mean of the actual distribution is:', pmf_kds.Mean())
print('The mean of the actual distribution is:', biased_pmf_kds.Mean())
```

>> The biased PMF distribution is obviously quite biased when both distributions are viewed on the same graph. The bias created by asking children how many kids are in their home and reporting based on that significantly skews the mean from around 1 (actual distribution) to more than twice that number at around 2.4 for the biased distribution. Very interesting.
