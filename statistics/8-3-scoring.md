[Think Stats Chapter 8 Exercise 3](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77)

---
```
def SimulateGame(lam):
    """Simulates a game and returns the estimated goal-scoring rate.

    lam: actual goal scoring rate in goals per game
    """
    goals = 0
    t = 0
    while True:
        time_between_goals = random.expovariate(lam)
        t += time_between_goals
        if t > 1:
            break
        goals += 1

    # estimated goal-scoring rate is the actual number of goals scored
    L = goals
    return(L)

def SimulateManyGames(lam=2, num_games=10000):
    goals_per_game = []
    for x in range(num_games):
        gls = SimulateGame(lam)
        goals_per_game.append(gls)

    print('rmse L', RMSE(goals_per_game, lam))
    print('mean error L', MeanError(goals_per_game, lam))

    pmf = thinkstats2.Pmf(goals_per_game)
    thinkplot.Hist(pmf)
    thinkplot.Config(xlabel='Goals scored', ylabel='PMF')

SimulateManyGames()

```

>> The standard error is 1.41  
Because the mean error is  small (-0.02) and decreases as m increases, it appears that this method of estimation is not biased.

---
