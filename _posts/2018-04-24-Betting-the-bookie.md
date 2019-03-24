---
title: Beating the bookie and winning 
tags: Python Betting PersonalProject
layout: single
mathjax: true
---

As long as society, people like to beat the odds and win; be it a race, or guessing game. We, humans like to gamble and more importantly, we like to win. Betting companies know this, hence why betting is $45 billion industry. With development of Machine learning and deep learning, predicting game outcomes has become more and more complicated. It's a constant rat race between betting companies and people trying to outsmart them.

However, a new approach to 'beating the bookies' was proposed by a team of researchers. In [this](https://arxiv.org/pdf/1710.02824.pdf) paper, the team suggests rather than trying to beat the companies; find odds which are favourable. There are certain occasions where betting companies change their odds, in order to attact customers, therefore offered odds are much favouble to the person rather than the company. This post sets out to present the code for this paper and explain how it works, and hopefully make you a litle money.

Script for this project can be found at [this](https://github.com/vladdtuz/PersonalProjects/blob/master/betting.py) github repository. In the script, there are three functions:
* TrueProb : function which takes as input database of odds. This odds would be for a specific game from across a number of betting sites
* TrueOdds : function to qunatify the true odds (takes in consideration taxes and calibration) for a specfic game outcome
* ToBuy : function to compare calculated true odds vs offered odds. This function will point out which odds and from which site, are odds favourable

Making use of this script is a follows. On 24/March/19 the following odds are given for Fulham vsMan city:
```python
odds_game_A = [[15,8.5,1.17],
                [15,8.9,1.19],
                [15,8.9,1.19],
                [16,8.4,1.18],
                [14.37,7.91,1.16],
                [17,7.5,1.14],
                [15,8,1.18],
                [14,8,1.17],
                [15.5,8.75,1.19],
                [16,8.9,1.18],
                [13.06,8.36,1.18],
                [16,8,1.18],
                [17,8,1.15]]
```
Therefore, next step is to determine true probablity for each outcome. This is done using the 'TrueProb' function as follows:

```python
>>> TrueProb(odds_game_A)
>>> out
array([0.06568596, 0.12057168, 0.85204042])
```

Therefore this shows that based on the bookies, Manchester city has an 85% chance of winning the game; there's a 12% chance of a draw and 6% chance Fulham takes this once (sorry Fulham fans). With the true probability in place, we can now determine true odds for which we can make a profit. We determine this by making use of the 'TrueOdds' function.

```python
>>> TrueOdds([0.06568596, 0.12057168, 0.85204042])
>>> out
array([63.75127821, 14.16999   ,  1.24681995])
```

Therefore, we have now determined that fair odds for us are :
* 63.75 for a Fulham win
* 14.16 for a draw
* 1.24 for Man city win

Now, we need to compare these odds to the odds we have saved earlier. We can do this comparison by using 'ToBuy' function. This is done so, as follows:

```python
ToBuy(odds_game_A,[63.75127821, 14.16999   ,  1.24681995])
>>> out
FavourableOnA  FavourableOnDraw  FavourableOnB
0             NaN               NaN            NaN
1             NaN               NaN            NaN
2             NaN               NaN            NaN
3             NaN               NaN            NaN
4             NaN               NaN            NaN
5             NaN               NaN            NaN
6             NaN               NaN            NaN
7             NaN               NaN            NaN
8             NaN               NaN            NaN
9             NaN               NaN            NaN
10            NaN               NaN            NaN
11            NaN               NaN            NaN
12            NaN               NaN            NaN
```

The output is three tables. First one is sorted by first coloumn, second by the second and so on. Unfortunately in our example, none of the odds offered are fair to us. This is mainly the case for 'big' games, however where this script comes into its own, is the smaller games. Games where otherwise we would miss. This is where the this post stops, however an extension to this script is to create a large dataset of betting odds. With large dataset, we are bound to find the those favourable odds


