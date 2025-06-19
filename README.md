# Time Series Analysis

## Introduction

This project is summarising Chapter 7, Time Series Models for Financial Data, from Introduction to Time Series and Forecasting (Third Edition) by Brockwell and Davis, and to implement a technique mentioned. This explores time series models that are useful for analyzing financial data. For example, given P<sub>t</sub> as the price of a stock or financial asset at time t, t ∈ Z, the log returns,{Z<sub>t</sub>≔log P<sub>t</sub>-log P<sub>t-1</sub>}, is often modelled as a stationary time series, which their statistical properties, such as mean and variance, remain constant over time. Traditional linear time series models, such as ARMA, assume constant conditional variance h<sub>t</sub> for Z<sub>t</sub>, which is independent of time and past data. However, this assumption is often violated in practice due to the changing variability of log returns Z<sub>t</sub>.

Therefore, this project focuses on discrete-time series models designed to capture and forecast volatility. These include ARCH, GARCH, modified GARCH processes and stochastic volatility models, which can better reflect the stylized characteristics of financial time series, such as tail heaviness, asymmetry, volatility clustering and serial dependence.

## Implementation
![image](https://github.com/user-attachments/assets/97070429-5691-46c4-a23d-fde321fa2adb) <br>
*Fig. 1*


We will analyze the time series data of the S&P 500 Index, focusing on its adjusted closing prices from December 30th 1927 to November 15th 2024, used to compute the daily log returns. Fig. 1 (left) shows the log returns, which has sustained periods of high and low volatility. Notably, high volatility is observed before 1940, around 1995, 2010, and 2020. An ARMA(2,2) model, identified as the best ARIMA model, is fitted to the data and the residuals are evaluated.

Fig. 1 (right) shows the autocorrelation of the standardized residuals and the absolute standardized residuals. While the autocorrelation of standardized residuals is small, the autocorrelation of absolute standardized residuals is significantly different from zero, suggesting the presence of volatility clustering in the data and potential suitability of GARCH model.

![image](https://github.com/user-attachments/assets/e9dc9acd-4757-4aeb-8527-9a720d664472) <br>
*Fig. 2*

GARCH(1,1) models are fitted on the daily log returns, with both normal residuals and t-distributed residuals. The AICC values for the previously fitted ARMA(2,2) model, the GARCH(1,1) model with normal residuals, and the GARCH(1,1) model with t-distributed residuals are -146382, -159288 and -161049 respectively. Both GARCH models outperform the ARMA model, with the GARCH(1,1) model with t-distributed residuals yielded the lowest AICC, indicating the best fit.

Fig.2 (left) shows the conditional volatility from GARCH(1,1) model with t-distributed residuals, reflecting the changing volatility patterns seen in Fig. 1 (left). Fig. 2 (right) shows that both the autocorrelation of the standardized residuals and the absolute standardized residuals from the GARCH model are low, indicating that the GARCH model has effectively captured the underlying data's structure.

The GARCH(1,1) model with t-distributed residuals reveals a mean close to zero, with a highly significant constant mean. The omega parameter is small but significant. The alpha (0.1) and beta (0.88) parameters suggest that 10% of current volatility is explained by past squared residuals, and 88% is explained by past volatility.

In summary, the GARCH(1,1) model with t-distributed residuals offers the best fit for the S&P 500 daily log returns, outperforming both the ARMA model and the GARCH model with normal residuals. The use of t-distributed residuals accounts for the heavy-tailed nature of the data (with kurtosis of 21.75), and the model successfully captures volatility clustering making it a robust model for modelling financial time series volatility.





