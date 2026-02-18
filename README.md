# Pattern or noise

# Introduction
Financial Time Series exhibit white noise. Raw prices can not be used for statistical analyses because the assumption for stationarity is not given (most of the time). While prices violates the assumption for stationarity, daily returns do not. 

It is not easy to distinguish between real returns and white noise. In the following plot Bitcoins daily returns and generated white noise are shown. Which one of these two is real? 

<img width="1312" height="659" alt="image" src="https://github.com/user-attachments/assets/22e64c83-b796-4679-95c2-e2f0ecc26420" />

In fact, one assumption of stationarity is the constant variance over time. One sequence exhibts periods where the variance is relatively low and hence, is not generated. 
But when returns behave like white noise, how is it possible that Bitcoin had such a great performance over the last years? 

Is it possible that daily returns are autocorrelated? Autocorrelation is in this case something like momentum.
A scatter plot with daily returns and white noise are visible in the next image. When autocorrelation exists, a linear relationship in daily returns could be present. 
For comparison purposes white noise and shifted values from white noise are also shown in the image.

<img width="1331" height="679" alt="image" src="https://github.com/user-attachments/assets/7776adda-2aa3-4070-9e58-0803650af39c" />

Which one of these is generated? First, it doesn't matter. Both are looking like the data comes from the same distribution. And the correlation coefficent for both series is approximately the same:
Bitcoin: -0.0330009. White noise: -0.01952083. Daily returns are clearly independent from each other. 
When Bitcoin had such a great performance over the last years and daily returns behave like white noise, why is no clear pattern visible?  

Or the problem should be adressed backward: How is it possible to quantify momentum? 

Another example is shown in the image below. Pattern or methodological error?
<img width="1189" height="589" alt="image" src="https://github.com/user-attachments/assets/08833fd5-98ec-43be-b84f-8087a1e2d0ca" />

It looks like a beautiful and mostly perfect linear relationship. But the data overlaps in the shifted series. This explains the mostly perfect linear relationship. 
The correct plot is visible at the end.  

# Objective
The objective is not to evaluate the strategy performance on real data, but to evaluate performance under randomness. For this purpose, a monte carlo apporach with geometric brownian motion is used. The research goal is clear: Does a stragey capture some real world phenomena or is the performance only good because rules or parameters are tweaked?

# Methodology 
Constant strategy rules are applied on simulated universes. A baseline or zero-distribution will be generated. Based on this zero-distribution the "real" alpha can be judged. 
For demonstration purposes only the distribution from the simulated "Information Ratios" is shown. 
A "null-hypothesis" can be constructed based on the confidence intervall from the zero-distribution. 

H0: The strategy performance is due to chance.
HA: The strategy performance is due to a real pattern in the data. 

Alternative the p-value can be calculated.

# Results

<img width="986" height="505" alt="image" src="https://github.com/user-attachments/assets/d09ba434-0816-4008-a2c1-183055e6543c" />

# Real Momentum Plot

<img width="1189" height="589" alt="image" src="https://github.com/user-attachments/assets/a9227719-e1a7-4480-820f-00d1e6176876" />








