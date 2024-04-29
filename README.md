My 2023 College Baseball model was inspired by advanced football metrics.
Historically, advanced metrics and sports stats began in baseball, but in football advanced metrics, Success Rate and Explosiveness were two stats that stood out to me. I wanted to experiment to see if those metrics could be utilized in a college baseball power ranking.

My baseball "advanced metrics" became Efficiency and Explosiveness.
Efficiency - In football, the efficiency metric is Success Rate, which is the percentage of plays that provide "positive" value to your chance of scoring. The "positive" value is defined differently by different analysts, either: a positive Expected Points Added play or a play that exceeds a threshold of yards to the next first down, where the threshold varies based on what down it is.

In baseball, On-Base Percentage or Batting Average are great proxies for Success Rate. But there's a non-linear relationship between hits and batting average, for example. In a no-hitter, the denominator for Batting Average is 27, but if a team get's three hits, the demoninator is 30. If I modify "Success Rate" to be Batter On-Base Per Out, we get a more linear relationship to runs scored - which is my Target Variable.

The "Explosiveness" metric is essentially Slugging Percentage, so I'm looking at doubles, triples, and home runs. Explosiveness has been harder to accurately predict, so there could be some work done there to improve it's performance.

# Linear Regression:
The components of Efficiency and Explosiveness from the 2022 College Baseball Season were used in a linear regression model (using statsmodels.OLS) to determine the coefficients for each component. Those components are then combined respectively into Efficiency and Explosiveness.

Afterwards, opponent adjustments are made through recurrsion.
Finally, "Expected Runs" is calculated as the number of runs expected over average vs an average opponent.

# Findings:
Notably, despite struggling late in the season, LSU remained #2 overall with the #1 Hitting Team and #4 Pitching team entering the regionals. They would go on to win the National Championship against Florida, who was #3 overall. 

The Model correctly picked the winner about 63% of the time through the season, picking every game (unless a game was missing from the NCAA's website).

Week          Percent of Games Correct

02/20/2023    0.609731

02/27/2023    0.641071

03/06/2023    0.696649

03/13/2023    0.638739

03/20/2023    0.654049

03/27/2023    0.607843

04/03/2023    0.594645

04/10/2023    0.684391

04/17/2023    0.609375

04/24/2023    0.661792

05/01/2023    0.656556

05/08/2023    0.643137

05/15/2023    0.632696

05/22/2023    0.587963

05/29/2023    0.673913

Full Rankings:
https://bootanalytics.github.io/

<img width="970" alt="image" src="https://github.com/BootAnalytics/2023Baseball/assets/125611355/c914bfdd-54f2-4579-808a-80cf36433b4a">
