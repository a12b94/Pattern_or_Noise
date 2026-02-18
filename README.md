# Pattern or noise

# Introduction
Financial time series often resemble white noise.
Raw price leves are typically non-stationary and therefore unsuitable for statistical analysis. However, daily returns are generally closer to stationary processes and are therefore commonly used in quantitative finance.

Yet, distinguishing between genuine market behavior and random noise is not straightforward.

The following figure compares Bitcoin daily returns with generated white noise.
At first glance, both series appear similar.

Which of the two is real?

<img width="1312" height="659" alt="image" src="https://github.com/user-attachments/assets/22e64c83-b796-4679-95c2-e2f0ecc26420" />

One key assumption of stationarity is constant variance over time.
Closer inspection reveals that one series exhibits periods of chaning volatility. A characteristic not consistent with pure white noise.

But this raises a fundamental question:
If daily returns behave like white noise, how could Bitcoin achieve such extraordinary long-term performance?

# Are Returns Predictable?

One possible explanation is autocorrelation. Commonly referred to as momentum. 

If momentum exists, past returns should contain some information about future returns.
This can be visualized using scatter plots comparing returns with their lagged values.

The next figure shows:
- Bitcoin daily returns vs. lagged returns
- White noise vs. shifted white noise

<img width="1331" height="679" alt="image" src="https://github.com/user-attachments/assets/7776adda-2aa3-4070-9e58-0803650af39c" />

At first glance, both appear drawn from the same distribution. 
The correlation coefficients confirm this:
- Bitcoin: -0.033
- White noise: -0.020
This suggests that daily returns are largely independent.

This leads to another paradox:
If returns look like white noise and show little autocorrelation, why do long-term trends exist?

# Quantifying Momentum - A Methodological Trap

Momentum is often measured as the rate of change or rolling returns over longer horizons.

The following figure appears to show an almost perfect linear relationship.

<img width="1189" height="589" alt="image" src="https://github.com/user-attachments/assets/08833fd5-98ec-43be-b84f-8087a1e2d0ca" /> 

However, this is a methodological illusion.

The apparent relationship arises because the windows overlap, creating a high correlation. Once overlapping is removed, the relationship becomes far weaker and more realistic.

# Objective
The objective of this project is not to evaluate strategy performance on historical data, but rather to asses how strategies behave under randomness.

To achieve this, a Monte Carlo framework based on geometric Brownian motions is used.

The core research question is:
Does a strategy capture genuine market structure, or does its performance arise purely from chance?

# Methodology 

A fixed strategy is applied to thousand of simulated market universes.

This produces a baseline distribution. A "zero-distribution", representing performance under pure randomness. 

From this distribution, statistical inference becomes possible.

Two approaches are used:
-Confidence intervals for hypothesis testing
-p-value estimation

Hypotheses:
H0: Strategy performance is due to chance.
HA: Strategy performance reflects a genuine market pattern.

# Results

The following figure shows the distribution of simulated Information Ratios under the null hypothesis.

<img width="986" height="505" alt="image" src="https://github.com/user-attachments/assets/d09ba434-0816-4008-a2c1-183055e6543c" />

This provides a benchmark against which real strategy performance can be evaluated.

# Real Momentum Example

Finally, the corrected momentum scatter plot illustrates the key insight:

Even in Bitcoin, predictive relationships are weak and contains some noise.

Momentum exists, but its signal-to-noise ratio is very low.

<img width="1189" height="589" alt="image" src="https://github.com/user-attachments/assets/a9227719-e1a7-4480-820f-00d1e6176876" />








