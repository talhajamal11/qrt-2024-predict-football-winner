## Challenge Context

Challenge context
Over the last two decades, professional sports around the world have adapted towards a data-driven approach to their decision-making. Sports analytics are part of live broadcasts, fantasy sports, and every-day discussions. This growth has been fueled by an exponential evolution in sports data.

Data science and machine learning can be useful to tackle the growing field of sports analytics. It can be used by fantasy league players and professional gamblers alike to make better informed decisions. Sports betting websites have become quite sophisticated in this area in the last few years. Models can also be used by managers of professional sports teams and recruiters to build rosters and strategically deploy players in a way that increases the team’s chance of winning.

Football has been at the heart of the sports analytics revolution. All types of statistics, both historical and real-time, are available. This challenge leverages Football data obtained from Sportmonks, a top-tier sports data provider widely used to enhance various online applications and websites. For additional details, feel free to explore sportmonks.com.

Feel free to visit and register to our dedicated forum at challengedata.qube-rt.com for more information about the challenge, the data and QRT.

## Challenge Goals

As this year’s QRT data challenge, we propose a match result prediction challenge. You will be provided with real historical data at the player, team and league level, and be asked to predict which team wins, or if there is a draw.

We have data for many leagues around the world and at different divisions. Your goal is to build a rich predictive models that can work in any football league regardless of competitive level or geographical location.

## Data Description

We provide data at the team and player level for dozens of football leagues.

The data comes packed in two zip files, X_train.zip, and X_test.zip, as well as two csv files Y_train.csv, and Y_train_supp.csv

The zip files contain the input data, which is divided into 4 csv files. The data is separated into HOME and AWAY team statistics, which is aggregated at the team and player level. All statistics come from real historical matches. They are summaries of the last 5 games prior to the match, as well as season-to-date statistics of the game being predicted.

The ID column links tables in X_train, with Y_train and Y_train_supp. The same holds true for the test data.

Input team data sets comprise the following 3 identifier columns:

ID, LEAGUE and TEAM_NAME (note that LEAGUE and TEAM_NAME are not included in the test data)
The following 25 statistics, which are aggregated by sum, average and standard deviation.

'TEAM_ATTACKS'
'TEAM_BALL_POSSESSION'
'TEAM_BALL_SAFE'
'TEAM_CORNERS'
'TEAM_DANGEROUS_ATTACKS'
'TEAM_FOULS'
'TEAM_GAME_DRAW'
'TEAM_GAME_LOST'
'TEAM_GAME_WON'
'TEAM_GOALS'
'TEAM_INJURIES'
'TEAM_OFFSIDES'
'TEAM_PASSES'
'TEAM_PENALTIES'
'TEAM_REDCARDS'
'TEAM_SAVES'
'TEAM_SHOTS_INSIDEBOX'
'TEAM_SHOTS_OFF_TARGET'
'TEAM_SHOTS_ON_TARGET',
'TEAM_SHOTS_OUTSIDEBOX'
'TEAM_SHOTS_TOTAL'
'TEAM_SUBSTITUTIONS'
'TEAM_SUCCESSFUL_PASSES'
'TEAM_SUCCESSFUL_PASSES_PERCENTAGE'
'TEAM_YELLOWCARDS'
Input player data sets comprise the following 3 identifier columns:

ID, LEAGUE and TEAM_NAME, POSITION and PLAYER_NAME (note that LEAGUE, TEAM_NAME, and PLAYER_NAME are not included in the test data)
52 statistics, which are aggregated by sum, average and standard deviation. They are similar to the team statistics though more fine-grained.

Output data sets are composed of 4 columns:

ID: Unique row identifier - corresponding to the input identifiers,
HOME_WINS,
DRAW,
AWAY_WINS,
The target score is the accuracy of prediction for the vector [HOME_WINS, DRAW,AWAY_WINS], for which there are three possible choices, [1,0,0]. [0,1,0] and [0,0,1].

All variables have been standardized and team/players/and league names have been removed from the test set. We have provided as much data in the train set as possible for your convenience. We expect from you to not use any external data, which can lead to disqualification.

An example of submission file containing random predictions is provided - see also the notebook in the supplementary material section for the benchmark output.

We have included other alternate training targets, such as GOAL_DIFF_HOME_AWAY, which is the difference of goals between the HOME and AWAY team, in the Y_train_supp file in case you want to train richer models with different targets.

Disclaimer: The data provided is exclusively intended for use in this challenge, and any usage of this dataset for other purposes is strictly prohibited. General terms or service are applicable: terms of service.

## Benchmark Description

There are two benchmarks for this challenge, the first is always predicting that the HOME team wins. This gives you an accuracy of around 44% on the training set.

The second benchmark, which is the one you will see in the leaderboard, uses only team data. It uses all numerical columns as features, and trains a gradient boosting tree model to predict if the AWAY team wins or not. This gives you an accuracy of around 47.5% on the training set.

Feel free to tweak existing benchmark, build your own models and use supplementary files as you want. Good luck for this challenge !