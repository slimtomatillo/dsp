[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

```
def cohen_effect_size(group1, group2):
    """Computes the Cohen's effect size between group1 and group2
    group1: Series or DataFrame
    group2: Series or DataFrame
    returns: float if the arguments are Series;
             Series if the arguments are DataFrames
    """

    difference = group1.mean() - group2.mean()

    var_1 = group1.var()
    var_2 = group2.var()
    group1_len = len(group1)
    group2_len = len(group2)  

    pooled_var = (var_1*group1_len + var_2*group2_len)/(group1_len+group2_len)  

    d = difference/np.sqrt(pooled_var)

    return(d)
  ```

>> The effect size of between the weight of first born and non-first born babies is -0.088672927072602, while the effect size between the length of pregnancy of first born and non-first born babies is 0.028879044654449883.

>> The effect size between the two groups for weight is slightly larger, but both are relatively small.

>> The effect size between the two groups for weight is negative, meaning the mean is higher for non-first born babies than the mean for first born babies.
