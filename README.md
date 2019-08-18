# Data-driven football betting strategy

_Executive summary_

Football betting is one of the most popular gambling activity today and betting sites often offer a mulititude of bet types to punters. Bookmakers in turn generate revenue by factoring in an overround to the odds that are offered to punters. These odds are then updated live until the start of the match based on the betting amounts placed by punters in a manner that reduces the total exposure of bookmakers to one side of a bet. Considering this, coupled with the tendency for most gamblers to rely on intuition, we will attempt to create a system that places value bets when they are available.

_Methodology_

The first topic of interest is to consider the relationship between the different match statistics and the number of goals scored or conceded. Some examples of the statistics we will attempt to collect include ball possession, pass accuracy (%), corners, fouls, shot accuracy(%), offsides, tackles won, headers won, etc. We will evaluate this relationship with the use of historical data available (e.g. matches played in English Premier League from the 2010/11 to 2017/18 season). 

In the above mentioned step, we utlizied data-cleaning techniques, visualizations, modelling and web scrapping for data collection. After identifying the most important predictors, we fitted these variables into a linear regression model that returned the expected goals scored or conceded by the home and away team. 

In the next step, we tested the robustness of the model with the match results of the 2018/19 season (recently ended) by utilizing the match odds for matches in 2018/19 and the match statistics that will be available to us on a rolling basis. We converted the match odds into implied odds for certain events happening (e.g. 2/1 offered on home win will mean a 33% chance of home win in the long run). After which, we used a Poisson distribution to translate the expected goals scored (from our earlier model) into percentages of different events occuring. If the percentages of our model exceeds the implied odds by a certain margin, we will place a bet and record the results of the bet.

The final step involves evaluation the results of all our bets and whether we can generate a statistically significant profit. 
