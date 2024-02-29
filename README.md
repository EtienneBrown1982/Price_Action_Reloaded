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

## Back Testing SPY and QQQ with RFR
The strategy model was trained with 10 years of historical data.  The strategy involved buying and selling based on the action produced from the estimated close data.  The strategy involved starting with 1000 dollars to buy or sell 1 share based on the action and comparing the results to buying and holding SPY or QQQ for that 10 year period with the maximum purchasable number of shares with the initial 1000 dollars.

<img src="/Resources/Images/spy_returns_rfr.png"  width="500" height="300">

<img src="/Resources/Images/qqq_returns_rfr.png"  width="500" height="300">

## Future Work and Next Steps
* The next major feature would be to improve the function for how many shares are bought/sold based on the current cash position. Currently, if the cash position is too high ( > 1000 dollars) there is a drag on strategy returns because of the flat returns from holding cash.
*  Jupyter Notebook to explore how **good** the close success has to be in order to be profitable for individual equities.
* Use GridSearch to explore if there are better parameters to use in Random Forest Regressor to improve the **close success** outcome.
