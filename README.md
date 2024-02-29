# Price Action Reloaded
The models will be able to predict the trading range for the upcoming day.

## Regression Models and Generative AI model
Can the models determine the high and low for tomorrow?



## LSGAN Model
Gaussian Noise is generated from a normal distribution, a common approach for generating random numbers that mimic many natural phenomena due to the Central Limit Theorem.

Random Walk Noise is a cumulative sum of the Gaussian Noise over an axis. This process simulated a random walk, a common model in finance for price movement. 

Sequential model because of (1) good with multiple inputs/outputs, shared layers, and non-linear topology (residual connections). Sequential model is a linear stack of layers. This is also suitable for initial explorations.

testing against real data.


## ElasticNet Regressor Model
ElasticNet uses Lasso and Ridge to make the regression line better if there's a lot of similar varibles. Lasso removes unnecessary variables. Ridge doesn't remove varibles it reduces the impact of values that are similar. This makes the regression line more accurate.

## Linear Regression
Ordinary least squares Linear Regression.

LinearRegression fits a linear model with coefficients w = (w1, …, wp) to minimize the residual sum of squares between the observed targets in the dataset, and the targets predicted by the linear approximation.

## Random Forest Regressor

A random forest is a meta estimator that fits a number of decision tree regressors on various sub-samples of the dataset and uses averaging to improve the predictive accuracy and control over-fitting. Trees in the forest use the best split strategy, i.e. equivalent to passing splitter="best" to the underlying DecisionTreeRegressor. The sub-sample size is controlled with the max_samples parameter if bootstrap=True (default), otherwise the whole dataset is used to build each tree.

## Champion Model
Random Forest Regressor performed the best for both the **Close Success** and **High/Low Success**
RFR achieved on average 64% success rate for high/low and 81% success rate for close

## Success Function
### High/Low Success
The high/low success function returns a 1 when the actual close is in between the predicted high and low data.
### Close Success
The close success function returns a 1 when the predicted close moves in the same direction as the actual close in comparison to the previous day.