[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (scoring)

```
def estimate(n=10, iters=1000):
    lam = 2

    means = []
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        L = 1 / np.mean(xs)
        means.append(L)

    ci = cdf.Percentile(5), cdf.Percentile(95)

    n_list.append(n)
    std_err_list.append(RMSE(means,lam))

    print('rmse L:', RMSE(means, lam))
    print('mean error L:', MeanError(means, lam))
    print('90% ci:', ci)

estimate()

n_list = []
std_err_list = []

def estimate(n=5, iters=1000):
    lam = 2

    means = []
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        L = 1 / np.mean(xs)
        means.append(L)

    ci = cdf.Percentile(5), cdf.Percentile(95)

    n_list.append(n)
    std_err_list.append(RMSE(means,lam))

    print('rmse L:', RMSE(means, lam))
    print('mean error L:', MeanError(means, lam))
    print('90% ci:', ci)

estimate()

def estimate(n=10, iters=1000):
    lam = 2

    means = []
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        L = 1 / np.mean(xs)
        means.append(L)

    ci = cdf.Percentile(5), cdf.Percentile(95)

    n_list.append(n)
    std_err_list.append(RMSE(means,lam))

    print('rmse L:', RMSE(means, lam))
    print('mean error L:', MeanError(means, lam))
    print('90% ci:', ci)

estimate()

def estimate(n=20, iters=1000):
    lam = 2

    means = []
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        L = 1 / np.mean(xs)
        means.append(L)

    ci = cdf.Percentile(5), cdf.Percentile(95)

    n_list.append(n)
    std_err_list.append(RMSE(means,lam))

    print('rmse L:', RMSE(means, lam))
    print('mean error L:', MeanError(means, lam))
    print('90% ci:', ci)

estimate()

def estimate(n=50, iters=1000):
    lam = 2

    means = []
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        L = 1 / np.mean(xs)
        means.append(L)

    ci = cdf.Percentile(5), cdf.Percentile(95)

    n_list.append(n)
    std_err_list.append(RMSE(means,lam))

    print('rmse L:', RMSE(means, lam))
    print('mean error L:', MeanError(means, lam))
    print('90% ci:', ci)

estimate()

def estimate(n=75, iters=1000):
    lam = 2

    means = []
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        L = 1 / np.mean(xs)
        means.append(L)

    ci = cdf.Percentile(5), cdf.Percentile(95)

    n_list.append(n)
    std_err_list.append(RMSE(means,lam))

    print('rmse L:', RMSE(means, lam))
    print('mean error L:', MeanError(means, lam))
    print('90% ci:', ci)

estimate()

def estimate(n=100, iters=1000):
    lam = 2

    means = []
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        L = 1 / np.mean(xs)
        means.append(L)

    ci = cdf.Percentile(5), cdf.Percentile(95)

    n_list.append(n)
    std_err_list.append(RMSE(means,lam))

    print('rmse L:', RMSE(means, lam))
    print('mean error L:', MeanError(means, lam))
    print('90% ci:', ci)

estimate()

import matplotlib.pyplot as plt

plt.plot(n_list,std_err_list)
plt.xlabel('n')
plt.ylabel('std error')
```

>> Results of experiment simulated 1000 times with n=10 and lambda=2:
rmse L: 0.8261571058022664
mean error L: 0.22671440108829377
90% ci: (85.97269915373764, 94.365245932097)
