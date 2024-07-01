# NBA Player Statistics

![NBA](nba.jpeg)

## NBA Player Salary Range

NBA players salary ranges are negotiated through contracts on a players performance metrics while playing in the NBA. NBA player salary ranges are calculated based on several key players statistics that relate to performance. These metrics help determine the salary range an indiviual player obtains. 

* NBA players salary ranges are negotiated through contracts on a players performance metrics while playing in the NBA.





### 1.Data

The data for this project was found through Kaggle and was loaded in by using an ODBC connection. The link to the data can be found here:
[NBA Player Statistics](https://www.kaggle.com/datasets/joebeachcapital/nba-player-statistics)

### 2.Data Cleaning

When the data was loaded into the jupyter notebook there were two columns that needed to be removed because they served no real purpose. Those two columns included the index column as well as the player-additional column. The next step was to check for null or NaN values within the data set. 
* Null values were intitially checked to see if there were any in the data set. 

![Null values](Nullvalues.jpeg)

* The few null values that were found in the data set were then removed.
* The next step was to find out if there were any na-values in the data set. We found that there were no na-values within our data set.
* Finally, we used df.info() to find out the vaious data types within or data set columns, as well as calling on df.describe() to generate descriptive statistics.

### 3. Exploratory Data Analysis (EDA)
We needed to explore the data and find out if we had any outliers in the data set, as well as find out if there was any correlation between the players stats and salary range. We did this in the following steps:

1. We first generated a boxplot using seaborn for the various columns and seeing if they had in outliers within the columns. 
![Boxplot](Boxplot.jpeg)

2. We then needed to create a boxplot for the salary range by itself, because its values were so high we couldnt properly graph it with the other columns.
![Salary box plot](Salary.jpeg)

3. We needed to create a heatmap of our data set to see the correlation between salary range and the associated stats columns.
![Heat Map](Heat.jpeg)

We then needed to plot the relationship between our most highly correlated columns associated with the salary column. The three most highly correlated columns were FG, FGA, and PTS. Below is a graph for each column vs the salary column.
* PTS were our most highly correlated statistic versus salary.![PTS](fg.jpeg)

* FGA was our second highest correlated statistic versus salary. ![FGA](fga.jpeg)

* FG was our third highest correlated statistic versus salary![FG](fg1.jpeg)

### 4. Preprocessing
For preprocessing we had to standardize our dependent variable. We first needed to see how we would standardize it. From the below image you can see that the data is skewed to the right. For this reason we chose to use a log scale (Powertransform) to standardize our data.
![Powerscale](Standardize.jpeg)

### 5. Modeling
Three different machine learning models were used for this data set. They included, linear regression, Ordinary Least Squares, and Random Forest. Below is a report on each model and which one peformed the best:

1. For the first linear regression we chose to make our independent variable our three best statistics versus players salary (FG, FGA, PTS). We can see from the first image that we were only able to obtain an Root Mean Square Error (RMSE) of 0.76. RMSE measures the amount of error we have in our model. This is a somewhat high amount of error. We then graphed our y_test and y_pred.![best](lr1.jpeg).
2. For our second model we performed a linear regression but with the independent variable being all columns except the salary column. With this model we were able to obtain a RMSE of 0.49! This is better than our previous model, but lets continue on to see if we get a better RMSE![lr](lrgraph.jpeg)
3. Next we chose to run an Ordinary Least Squares model. Just like with our last linear regression model we kept the independent variable as all of the columns except for salary. With this model we were able to obtain an RMSE of 0.51. ![ol](ols.jpeg)
4. For our fourth model, we chose to do a Random Forest. For each model previously we calculated the R-squared score. In doing so we found that the Random forest had the best R-squared, so we chose to perform hyper parameters on our model to increase performance and hopefully obtain a lower RMSE. In doing so we actually calcualted an RMSE of    5845684.85. We can see that from our model there is a lot of error within our model. ![Random Forest](Random.jpeg).

### 6. Final Model Chosen
We can see from the modeling that our Linear Regression of all statistics peformed better than our random forest, Ordinary Least Squares, and our linear regression of the three best statistics. This indicates that every statistic has a direct role in a players salary.  

### 6. Recommendations
1. From the above modeling we chose to go with the linear regression model since it gave us the smallest error (RMSE) and the model fit the data well when it was plotted.
2. Based off of these findings I believe that when it comes time to negotiate a players salary, management should look at all available player statistics to calculate a players salary. 
3. Teams can also benefit from this analysis by being able to stay within budget when calculating a players salary range against the budget.
4. As a player progresses over the years this analysis will be able to keep track of their performance and how their salary varies with performance.


