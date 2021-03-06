# dataproject2stockmarket

A template for time series analysis on the shares' data on any company.

## Here is an example for Ford Motors

#### The data fetched is from yahoo for the last 15 years

### Close
Closing prices are stationary
![closing-prices](https://cloud.githubusercontent.com/assets/11637437/23563095/0ce97f66-fffa-11e6-868b-fc68e1576ec8.png)

### First Difference

We can consider analyzing a first difference of the series. value of (t-1) is subtracted from value of (t).

![first-difference](https://cloud.githubusercontent.com/assets/11637437/23563098/0ceb2afa-fffa-11e6-91a5-d123249fa989.png)

First difference is relatively stationary and mostly fluctuates around 0. But variance of this series can vary over time. We need to incorporate mechanism to accomodate for sensing smaller variances along with the larger ones. Hence, Log.

### Log

Log of closing price

![log-closing-price](https://cloud.githubusercontent.com/assets/11637437/23563096/0ceaa97c-fffa-11e6-8308-3b150fbbca98.png)

So that gives us the original closing price with a log transform applied to <b>"flatten"</b> the data from an exponential curve to a linear curve. One way to visually see the effect that the log transform had is to analyze the variance over time. We can use a rolling variance statistic and compare both the original series and the logged series.


### Variance - with and without Log
![variance](https://cloud.githubusercontent.com/assets/11637437/23563103/0cfdbe04-fffa-11e6-805a-73b3094498fa.png)

![variance-log](https://cloud.githubusercontent.com/assets/11637437/23563101/0cfbad44-fffa-11e6-844c-9440efeb7dee.png)

### Normal and Logged First Difference
![normal-first-difference](https://cloud.githubusercontent.com/assets/11637437/23563102/0cfc4cea-fffa-11e6-8ad5-2f8fce20d87e.png)

![log-first-difference](https://cloud.githubusercontent.com/assets/11637437/23563100/0cedca08-fffa-11e6-8ab4-48fc744043df.png)

### Create a few more lag variables

Now we create a few more lab variables with lag of 1, 2, 5 and 30 days

![correlation-between-log-variables](https://cloud.githubusercontent.com/assets/11637437/23563097/0ceae2a2-fffa-11e6-892a-814d8908251c.png)

#### No apparent Correlation. It means that today's index values does not tell much about at least a few days in the future.

### Lag relationships

There could be relation in the values we did not try. There is a function to test those relationships. Let's try those.

![lag-correlation](https://cloud.githubusercontent.com/assets/11637437/23563099/0cebfc8c-fffa-11e6-8faa-3dbd730a3004.png)

### Seasonal Decomposition
 
![seasonal-decomposition](https://cloud.githubusercontent.com/assets/11637437/23563104/0cff2280-fffa-11e6-9bcf-8b30f208e991.png)

### ARIMA analysis

Analyis for perfomed, but as expected, it yielded inaccurate predictions. (Predicting shared ain't that easy!)
