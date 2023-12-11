# MLB_Digital_Engagement_Drivers
**Major League Baseball Digital Engagement Drivers**

**Objective**

The goal of this project was to utilize the MLB’s digital engagement data to explain the question of what on field events drive fan engagement through digital platforms. The scope of this analysis was to review the on-field drivers of non-pitcher positions for the 2018 to 2021 seasons.

**Data Selection**

To conduct this project, a dataset from Kaggle was sourced and selected. The 1990-2021 MLB data was utilized which contain main dimensions of MLB games, players as well as their daily digital engagement metrics from 3 digital platforms: https://www.kaggle.com/competitions/mlb-player-digital-engagement-forecasting/overview.

**Data Exploration & Analysis**

For this analysis, an in-depth EDA was not truly required as the Explainable Machine Learning (ExML) output would be the analysis. The data package consisted of 14 data files containing data such as player information, game by game stats by player, team information and more.

All this data needed to by merged to develop ExML for digital engagement drivers. This data engineering was conducted in Python as per this workbook: https://github.com/mmarra23/MLB_Digital_Engagement_Drivers/blob/main/MLB%20Engagement%20-%2001%20-%20Data%20Import%20-%20v01%202023-01-13.ipynb

![image](https://user-images.githubusercontent.com/89919659/227675431-5ee9267a-5e35-4956-a621-e3e09afb81eb.png)

**Data Cleaning Transformation & Feature Engineering**

*	In the data engineering procedures, we filter season greater than 2018 season. I also develop new features such as Major Market teams, Season categories like Pre-Season, Regular, Post.
*	Removed features with significant percentage of NULL values.
*	Transformed specific feature data types to the appropriate data type.
*	Create new features from an offence player perceptive as well as team. The features create where Batting Avg on Balls in Play, Isolated Power, Runs Created and a binary ID to note where the team was in the American or National league.

**Explainable Machine Learning (ExML)**

*	Since the goal was to explain the on-field events that drove digital engagement I had selected a Regression model to be the input to the ExML development. The regression model selected was XGBoost.
*	XGBoost was selected because it is one of my favourite ML packages which yield impressive results out of the box in an efficient runtime perspective.
*	Before resulting the ExML I scaled using Standard Scaler and OneHotEncorder.
*	Isolated the 3 target variables which were the engagement results of the 3 digital platforms.
*	Created a 4th target variable by taking the mean of the 3 engagement results to obtain an overall digital engagement view.
*	Isolated all the input features to the regressor.
*	Generated the output with the target variables and input features using XGBoost Regressor.
*	The last step was to utilize the SHAP package to output the drivers and a rank order.
*	Here is the workbook with all the analytical procedures executed: https://github.com/mmarra23/MLB_Digital_Engagement_Drivers/blob/main/MLB%20Engagement%20-%2002%20-%20Analysis%20-%20v01%202023-01-16.ipynb

**Conclusion**

Each digital platform yielded similar drivers and ranking order with some slight differences between them. Using the average engagement scoring the following are the top 5 on-field events that drove digital engagement from the 2018 season and beyond.

*	Whether the team was in a **Major Market**.
*	When a **Home Run** was hit in a game.
*	Number of **At Bat Appearances** by a player in a game.
*	An **RBI scored**.
*	**Runs Created** by a player in a game.

![download](https://user-images.githubusercontent.com/89919659/224550750-435b32a2-7ee4-42a0-98e2-690991a312a0.png)

***Update***

A feature that I will add in future to this analysis is whether the player was of a franchise and/or all-star type player. I believe this will be in top 5 drivers of increased digital engagement.
