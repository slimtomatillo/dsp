[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```
sample = np.random.random(1000)
sample_pmf = thinkstats2.Pmf(sample, label='pmf')
thinkplot.pmf(sample_pmf)

sample_cdf = thinkstats2.Cdf(sample, label='cdf')
thinkplot.cdf(sample_cdf)
```
>> When plotting the PMF of a random sample of 1000 numbers, it is very difficult to see the distribution because when there are so many numbers, the probability of each value is smaller and random noise occurs. As stated in the book, PMFs are helpful with smaller amounts of values, but CDFs tend to be more useful for larger amounts of values. When looking at the plot of the CDF of the sample, it is clear the there is a uniform distribution.
