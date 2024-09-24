1. Augmented Dickey-Fuller (ADF) Test:
Purpose: The ADF test checks for stationarity in the differenced time series. A stationary series is one where the statistical properties (mean, variance, autocorrelation) do not change over time.
How it works: The null hypothesis for the ADF test is that the time series has a unit root (i.e., it is non-stationary). If the p-value from the test is below a certain threshold (commonly 0.05), you reject the null hypothesis, indicating that the time series is stationary.
On differenced data: After differencing, you're typically aiming for the series to become stationary, and the ADF test will confirm if your differencing was successful.
2. Autocorrelation Function (ACF):
Purpose: ACF measures the correlation between the current value and its previous values (lags). It shows how the observations in the time series relate to each other at different time lags.
How it works: For each lag k, it calculates the correlation between yt and yt-k.
On differenced data:
For a well-differenced stationary series, the ACF will often decay quickly, typically within a few lags.
If significant spikes are observed at certain lags, it might indicate seasonality or short-term dependencies in the data.
Use in modeling: ACF helps determine the MA (Moving Average) terms in ARIMA models by identifying significant correlations at specific lags.
3. Partial Autocorrelation Function (PACF):
Purpose: PACF shows the correlation between the current value and its lag, controlling for the values of the time series at all intermediate lags. This isolates the direct effect of each lag on the current value.
How it works: PACF removes the influence of shorter lags, showing only the "pure" correlation with a specific lag.
On differenced data:
A sharp drop in PACF after a few lags indicates that only a few lagged terms are directly related to the current observation.
If the PACF cuts off after a certain lag, it might suggest the AR (AutoRegressive) terms in an ARIMA model.
Summary of What Each Tool Reveals:
ADF Test: Confirms if the differenced series is stationary (a prerequisite for ARIMA modeling).
ACF: Helps identify MA terms (by examining the behavior of correlations over time).
PACF: Helps identify AR terms (by showing how much each lag directly influences the series).
In the context of ARIMA modeling:

A strong drop-off in ACF after a few lags suggests you need an MA component. <br>
A sharp cut-off in PACF after a few lags indicates the need for an AR component.

Non Stationary -> Stationary (for analysis)
Can be done by doing:
- Differencing
- Transformation