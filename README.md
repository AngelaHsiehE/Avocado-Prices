# Predict Avocado-Prices
## Introduction
Avocados are a staple in many people's diet. Whether it's warm avocado toast in winter or guacamole drizzled with olive oil in summer, avocado has been our our all time favorite. For the past decades, our appetite for avocados have only risen. In 2000, Americans were consuming a little more than 1 billion avocados, and that number has since exploded, reaching nearly 5 billion.

However, avocado prices can vary quite a bit throughout the year. During certain time of the year, they can be quite expensive for foodies. In this project, we'll explore the underlying trends and patterns of avocado prices, and then develop the optimal SARIMA model to forecast the average prices over the next two years.

## Data Preprocessing and Visualization

#### Organic Avocados V.S Conventional Avocados
The majority of the sales are conventional avocados. Conventional avocados are also cheaper by about 50 cents each than organic ones.

<img src="https://user-images.githubusercontent.com/57699414/78824462-9d0d2e80-799b-11ea-8a7e-a51810740708.png"
	height="300" width="350" /><img src="https://user-images.githubusercontent.com/57699414/78750134-da86a300-792c-11ea-9f2b-ac8ecdef1b17.png"
	height="300" width="450" />

#### Average Price 2015-2018
The monthly average price in 2015 ranges between $1.3-$1.5 without much fluctuation. In 2016 and 2017, there are seasonal patterns where the average price starts going up in spring/summer and starts going down after its peak around October. We can see the distribution for 2017 has an usual highest peak in September and then it abruptly drops, which coincides with the fact that California avocados had a weak harvest that year and there was a surginf demand for avocados.

<img src="https://user-images.githubusercontent.com/57699414/78824786-29b7ec80-799c-11ea-8808-28c6a214f771.png"
	height="300" width="400" /><img src="https://user-images.githubusercontent.com/57699414/78825141-af3b9c80-799c-11ea-9753-568cedb71cbe.png"
	height="300" width="400" />

#### Decomposition 



#### ACF AND PACF Plots

## Time Series Forecasting With Seasonal ARIMA
We applied Seasonal ARIMA model on training set because the data has obvious seasonality, and used grid search to find the optimal parameters for our model. 
![forecast](https://user-images.githubusercontent.com/57699414/78818290-aabdb680-7991-11ea-8cc4-0ef99908ff55.png)

Our primary concern is to ensure that the residuals of our model are uncorrelated and normally distributed with zero-mean. If the seasonal ARIMA model does not satisfy these properties, it is a good indication that it can be further improved.

#### Model Diagnostics
Based on the model diagnostics, we can see the resisuals of the model are normally distributed and have correlations with each other.

![evaluate](https://user-images.githubusercontent.com/57699414/78818827-80b8c400-7992-11ea-853e-4c02d17b650c.png)

- The stardard resisual plot (top left) shows that the residuals over time doesn't have any obvious seasonality.
- In the top right plot, the KDE line follows closely to the N(0.1) line which is the standard notation for a normal distribution with mean 0 and standard deviation of 1.
- The qq plot (bottom left) shows that the ordered distribution of residuals (blue dots) follows the linear trend of the samples taken from a standard normal distribution.
- In the correlogram plot (bottom right) shows that time series of residuals have low correlations with its previous lags.

## Actionable Recommendations
#### Summary Of Findings
- Avocados are the cheapest in the winter and the most expensive in the fall.

- Type of avocados doesn't have a significant impact on the fluctuation of price. Average price of organic avocados has always been about 50 cents more than conventional ones.

- Avocado prices are the highest at the end of each month.

- Avocados are cheaper in the south central region such as Texas and California.

- Avocado prices are the highest in 2017, but also fluctuate the most in that year due to a surging demand and a smaller crop in California and Mexico.

- Based on the forecast, avocado prices will slightly decline over 2018 and 2019 and the average price will not be more than 1.5. However, the price of avocados is largely influenced by the harvest in California and Mexico, as well as trade tariffs. Surging price in a single year due to weather or political event is likely to happen.

#### Recommendations For Avocado Lovers:
Early summer is the best time to stock up on avocados. Prices are likely to go up in September. However, freezing can affect the texture. The possible solution is to blend thawed avocados into guacamole and other dishes and you can enjoy it till November. By then, prices will significantly decrease and stay low till spring.

It might not be worth the money to buy organic avocados since organic avocados are at least 50 cents more expensive then conventional ones.The main reason that people purchase organic products is to avoid pesticides. There are fruits or vegetables that are likely to absorb pesticides such as peaches and apples. But it may not be the case for avocados because we don't eat the skin, where pesticides may have directly touched.
