[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

#range of heights: 5’10” to 6’1” --> 177.8 cm to 185.42 cm

```
lower_bound = dist.cdf(177.8)
upper_bound = dist.cdf(185.42)
blue_men = upper_bound - lower_bound
print(blue_men)
```

>> The last line above returns "0.3427468376314737" meaning that about 34% of the population is between 5'10" and 6'1".
