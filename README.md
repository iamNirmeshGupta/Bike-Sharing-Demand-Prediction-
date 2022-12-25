# Bike-Sharing-Demand-Prediction-
Making a regression model to predict bike count required for stable supply of rental bikes.

Abstract:

Bike sharing systems have been gaining prominence all over the world with more than 500 successful systems being deployed in major cities like New York, Washington, London etc. With an increasing awareness of the harms of fossil based means of transportation, problems of traffic congestion in the cities and increasing health consciousness in urban areas, citizens are adopting bike sharing systems with zest. Even developing countries like India are adopting the trend with a bike sharing system in the pipeline for Karnataka. 
This project tackles the problem of predicting the number of bikes which will be rented at any given hour. This project investigates the efficacy of standard Machine Learning techniques namely Linear Regression, Decision Tree Regressor, Random Forest Regressor and Gradient Boosting by implementing and analyzing their performance with respect to each other. 

1. Problem Statement:

Currently Rental bikes are introduced in many urban cities for the enhancement of  mobility comfort. It is important to make the rental bikes available and accessible to the public at the right time as it lessens the waiting time.
Eventually, providing the city with a stable supply of rental bikes becomes a major concern. The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes.
We are tasked with predicting the number of bikes rented each hour so as to make an approximate estimation of the number of bikes to be made available to the public given a particular hour of the day.

2. Introduction:

Bike sharing systems are innovative ways of renting bikes for use without the onus of ownership. The users of Bike sharing system can pick up bikes from a kiosk in one location and return them to a kiosk, at possibly any location of the city.
Bike sharing systems have been gaining a lot of traction around the world. With more than 500 bike renting schemes across the globe, these schemes provide a rich dataset for analysis..


3. Data:

The dataset contains rental and usage data of bike renting spread across two years. The dataset has 8760 observations for 365 days of bike rental count, 13 independent variables and 1 dependent variable.
 
The data generated from these variables can be analyzed to draw inferences regarding bike sharing demand. Factors such as Season of renting, Temperature and Time of renting etc, play an important role in determining the patterns of bikes renting demand in the city 

4. Steps Involved:

The steps involved in this exploratory data analysis are:

Understanding the Data:

The first step in any exploratory data analysis and modeling is to understand what we are looking at, but without going into the details. We try to understand the problem we want to solve, thinking about the entire dataset and the meaning of the variables.
This phase can be slow and boring but it will give us the opportunity to make an opinion of our dataset.


Data Preparation and Cleaning:

In this stage, I tried to do basic cleaning of the data in order to continue the analysis like:

Renamed a few variables:-

I renamed a few variables and removed the units attached to them for ease of typing.

Treated the null values:-

There were no null values to take care of in our dataset.

Converting the Data columns:-

I converted the date column first to datetime datatype and then split it into three separate columns named - Year, Month and Day of week. Then made a new column Weekend_Weekday by using Day of week column and then deleted Day, Year and Date column after analyzing they will not be needed for further analysis.

Data type conversion:-

Then I converted the data type of columns like Hour, Weekend_weekday and month from Int64 to Category.

                      
Exploratory Analysis:

In this section, I explored the data to get insights about it. Some of the key information that I could collect from the data are:-



Distribution of Dependent Variable:

The Rented Bike Count feature, which is our target feature, was normally distributed with a little right skew. Then  I applied square root transformation to treat the skewness.
 
Categorical Variable Analysis:

Hour : More number of bookings were made during work going hours(7am - 9am) and during later parts of the day(3pm to 10pm).

Season : Bookings for way less in winters as compared with other seasons.

Holiday : More bikes were rented on working days as compared with holidays.

Functioning Day : Very few bikes were rented on non functioning days.

Month : Bike rentals were higher during summer months(April to October)


Numerical Variable Analysis:

Distribution : I checked for the distribution of the numerical variables and found that most of them had a degree of skewness in their distribution and applied log transformation and square root transformation to treat the skewness.

Regression Plot : From the regression plot of all the numerical variables with respect to the target variable, I found that features like Wind Speed, Temperature, Dew point Temperature, Visibility and Solar Radiation are positively correlated with the target feature and features like Rainfall, Snowfall and Humidity are negatively correlated with the target feature.

Multicollinearity : None of the independent variables had high correlation with each other and no multicollinearity was detected. 
	

Feature Engineering:

Then I did some feature engineering using the ‘get_dummies’ function for features like Hour, Seasons, Holiday, functioning Day, Month etc.




Modeling:

After declaring the independent and target variables and splitting them into test and train data, I used a number of algorithms to train from the train data and then predict on the test data. Then I compared these predicted values with the actual values with the help of some evaluation metrics.
Algorithms : The algorithms that I used are : 

Linear Regression:

Linear Regression is a machine learning algorithm based on supervised machine learning. It performs a regression task. Regression models a target prediction based on independent variables. It is mostly used for finding out relationships between variables and forecasting. Linear regression performs the task to predict a dependent variable value based on a given independent variable. So, this regression technique finds out a linear relationship between input and output. Hence, the name is Linear Regression.

Lasso Regression:

Lasso Regression is a type of Linear Regression that uses shrinkage. Shrinkage is where data values are shrunk towards a central point, like the mean. The lasso procedure encourages simple and sparse models. This particular type of regression is well suited for models showing high levels of multicollinearity.

Ridge Regression:

Ridge regression is the method used for analysis of multicollinearity in multiple regression data. It is most suitable when a dataset contains a higher number of predictor variables than the number of observations. The second scenario is when multicollinearity is experienced in a set.

ElasticNet:

ElasticNet is a combination of Ridge and Lasso regression that combines the L1 and L2 penalties of the Lasso and Ridge methods.

Decision Tree Regression:

Decision Tree Regression observes features of an object and trains a model in  the structure of a tree to predict data in the future to produce meaningful continuous output. Continuous output means that the output is not discrete.



Random Forest Regression:

Random Forest is an ensemble technique capable of performing both regression and classification tasks with the use of multiple decision trees and a technique called Bootstrap and Aggregation, commonly known as Bagging.

Gradient Boosting Regression:

Gradient Boosting algorithm is used to generate an ensemble model by combining the weak learners or weak predictive models. Gradient boosting builds an additive mode by using multiple decision trees of fixed sizes as weak predictive models. The parameter, n_estimator, decides the number of decision trees which will be used in the boosting stages.

GridSearchCv for Gradient Boosting Regressor:

GridSearchCV is the process of hyperparameter tuning in order to determine the optimal values for a given model. Note that there is no way to know in advance the best values for hyperparameters so ideally, we need to try all possible values to know the optimal values. Doing this manually could take a considerable amount of time and resources and thus we use GridSearchCV to automate the tuning of hyperparameters.
	
Evaluation Metrics : The evaluation metrics that I used are : 

Mean Squared Error(MSE) : 

The mean squared error measures how close a regression line is to a set of data points. Mean squared error is calculated by taking the average, specifically mean, of errors(Actual - Predicted) squared from data.

Root Mean Squared Error(RMSE) : 

Root mean squared error is the measure of how well a regression line fits the data points. It is Standard  deviation of the residuals. In other words, it tells you how concentrated the data is around the line of best fit. It is simply calculated by taking a  square root of Mean Squared Error.

R-Squared :

R-squared is the goodness-of-fit measure for linear regression models. This statistic indicates  the percentage of the variance in the dependent variable that the independent variables explain collectively. It measures the strength of the relationship between your model and the dependent variable on a convenient 0-100% scale. It is also called the Coefficient of Determination.

Adjusted R-Squared :

The Adjusted R-squared is a modified version of R-squared that adjusts for predictors that are not significant in a regression model. The adjusted R-squared looks at whether additional input variables are contributing to the model.
	

5. References:

Researchgate.net

Eezeeabsolute.com

GeeksforGeeks

