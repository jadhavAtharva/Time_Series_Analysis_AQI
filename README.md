# Air Quality Index Forecasting using ARMA and SARIMA Models

## Overview

This project applies advanced time series modeling to forecast the Air Quality Index (AQI), with a specific focus on Carbon Monoxide (CO) levels, using historical pollution data from two major US counties—Cook (Illinois) and Maricopa (Arizona). We compare ARMA and SARIMA models to identify temporal trends and develop accurate predictive systems for environmental monitoring.

## Team

- **Atharva Jadhav** (ajadhav16@hawk.iit.edu)
- **Harshali Gaikwad** (hgaikwad@hawk.iit.edu)
- **Sriujan Harihar** (harihar1@hawk.iit.edu)  
- **Instructor**: Prof. Stasi Despina

## Project Goals

- Forecast AQI using ARMA and SARIMA time series models.
- Analyze temporal trends and seasonality in pollution data.
- Compare one-step ahead vs. dynamic forecasting.
- Evaluate model performance using MSE, MAE, and RMSE.

## Dataset

- **Source**: [US Pollution Dataset (Kaggle)](https://www.kaggle.com/datasets/sogun3/uspollution)
- **Period**: 2000–2016
- **Focus Counties**: Cook (IL) and Maricopa (AZ)

## Tools & Technologies

- **Language**: R
- **Libraries**: `tidyverse`, `tseries`, `forecast`, `ggplot2`, `scales`, `tibble`
- **Environment**: RStudio

## Methodology

### Data Preprocessing
- Cleaned missing values using column-wise means.
- Aggregated data by month.
- Focused on CO levels in Cook and Maricopa counties.

### Exploratory Data Analysis (EDA)
- Assessed stationarity using ADF tests.
- Visualized trends, seasonality, and autocorrelation (ACF/PACF).
- Seasonal decomposition and subseries plots.

### Model Selection and Fitting
- **Cook County**: ARMA model after differencing.
- **Maricopa County**: SARIMA model due to clear seasonality.
- Used `auto.arima()` for parameter tuning.
- Residuals checked for white noise using Ljung-Box test.

### Forecasting
- One-step and 12-step ahead forecasts with confidence intervals.
- Evaluation using:
  - **MSE**
  - **MAE**
  - **RMSE**

## Results

### Cook County
- ARMA(0,0,2) model yielded low RMSE with normally distributed residuals.
- Forecasts reverted to zero due to the model's zero-mean configuration.

### Maricopa County
- SARIMA(2,0,1)(2,1,0) with drift effectively modeled trends and seasonality.
- Residuals showed greater spread and variance, indicating model limitations.

### Comparative Analysis
- Cook County's model fit was more consistent and residuals tighter.
- Maricopa showed higher variance and possible unmodeled dynamics.
- Suggests need for more complex modeling or external variable inclusion for Maricopa.

## Conclusion

- ARMA and SARIMA models are effective for AQI forecasting.
- Temporal patterns and seasonality were well captured.
- Results support the use of statistical forecasting for public health policy.

## References

- Kaggle Dataset: [US Pollution Data](https://www.kaggle.com/datasets/sogun3/uspollution)
- Time Series Literature: *Introduction to Time Series and Forecasting* by Brockwell & Davis
- R Packages: `forecast`, `tseries`, `ggplot2`, `tidyverse`

