[Think Stats Chapter 9 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2010.html#toc90) (resampling)

```
class DiffMeansResample(DiffMeansPermute):
    def RunModel(self):
        group1 = np.random.choice(self.pool, self.n, replace=True)
        group2 = np.random.choice(self.pool, self.m, replace=True)
        return(group1, group2)

def Resample(firsts, others):
    data = firsts.prglngth.values, others.prglngth.values
    ht = DiffMeansResample(data)
    p_value = ht.PValue(iters=10000)
    print('differences in means resample prglngth')
    print('p-value:',p_value)
    print('actual:',ht.actual)

    print()
    data = (firsts.totalwgt_lb.dropna().values,
            others.totalwgt_lb.dropna().values)
    ht = DiffMeansPermute(data)
    p_value = ht.PValue(iters=10000)
    print('differences in means resample birthweight')
    print('p-value:',p_value)
    print('actual:',ht.actual)

Resample(firsts,others)
```

>> Results from above resampling:  

>> differences in means resample prglngth  
p-value: 0.1749  
actual: 0.07803726677754952  

>> differences in means resample birthweight  
p-value: 0.0001  
actual: 0.12476118453549034  

>> Using resampling instead of permutation seems to have some effect on the results though I am a little unsure of how to interpret the results. Different p-values (to a somewhat substantial level) were produced by the models though they are based on slightly different assumptions, which play into the differences.
