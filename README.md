# Time Series Analysis

## Introduction
This project is summarising Chapter 7, Time Series Models for Financial Data, from Introduction to Time Series and Forecasting (Third Edition) by Brockwell and Davis, and to implement a technique mentioned. This explores time series models that are useful for analyzing financial data. For example, given Pt as the price of a stock or financial asset at time 𝑡, 𝑡 ∈ ℤ, the log returns,{𝑍𝑡≔𝑙𝑜𝑔 𝑃𝑡−𝑙𝑜𝑔 𝑃𝑡−1}, is often modelled as a stationary time series, which their statistical properties, such as mean and variance, remain constant over time. Traditional linear time series models, such as ARMA, assume constant conditional variance ℎ𝑡 for 𝑍𝑡, which is independent of time and past data. However, this assumption is often violated in practice due to the changing variability of log returns 𝑍𝑡.

Therefore, this project focuses on discrete-time series models designed to capture and forecast volatility. These include ARCH, GARCH, modified GARCH processes and stochastic volatility models, which can better reflect the stylized characteristics of financial time series, such as tail heaviness, asymmetry, volatility clustering and serial dependence.

## Implementation
![image](https://github.com/user-attachments/assets/97070429-5691-46c4-a23d-fde321fa2adb)



![image](https://github.com/user-attachments/assets/e9dc9acd-4757-4aeb-8527-9a720d664472)
