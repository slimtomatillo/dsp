[Think Stats Chapter 7 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2008.html#toc70) (weight vs. age)

```
import first

live, firsts, others = first.MakeFrames()
live = live.dropna(subset=['agepreg', 'totalwgt_lb'])

def SampleNSFG(df, nrows, replace=False):
    indices = np.random.choice(df.index, nrows, replace=replace)
    sample = df.loc[indices]
    return(sample)

sample = SampleNSFG(live, 5000)
ages, weights = sample.agepreg, sample.totalwgt_lb

thinkplot.Scatter(ages, weights, alpha=1)
thinkplot.Config(xlabel='Age of mother (years)',
                 ylabel='Weight of baby (lbs)',
                legend=False)

bins = np.arange(10, 45, 5)
indices = np.digitize(live.agepreg, bins)
groups = live.groupby(indices)

for i, group in groups:
    print(i, len(group))

mean_ages = [group.agepreg.mean() for i, group in groups]
cdfs = [thinkstats2.Cdf(group.totalwgt_lb) for i, group in groups]

for percent in [74, 50, 25]:
    age_percentiles = [cdf.Percentile(percent) for cdf in cdfs]
    label = '%dth' % percent
    thinkplot.Plot(mean_ages, age_percentiles, label=label)

thinkplot.Config(xlabel='Age of mother (years)',
                 ylabel='Weight of baby (lbs)',
                 axis=[13, 42, 0, 10],
                 legend=False
                )

np.corrcoef(ages, weights)

def SpearmanCorr(xs, ys):
    xs = pd.Series(xs)
    ys = pd.Series(ys)
    return(xs.corr(ys, method='spearman'))

SpearmanCorr(ages, weights)
```

>> Pearson's correlation is 0.0497 and Spearman's correlation is 0.0810. As both correlations are close to 0, it seems like there is little predictive relationship between the two. Generally, as a woman's age increases or decreases, the weight of the baby does not vary significantly. Spearman's correlation is slightly higher than Pearson's correlation, which signifies that there is some skew or outliers in the data that explain Pearson's correlation.
