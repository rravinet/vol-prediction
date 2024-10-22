# Intraday Volatility Prediction Model

This repository contains a Python implementation of **intraday volatility prediction** inspired by the paper *A Practical Model for Prediction of Intraday Volatility* from Young Li. The project extends the paper by integrating **GARCH models** with diurnal patterns to enhance intraday volatility forecasting for selected stocks.

## Features

- **Data Pipeline**: Retrieves **minute, hourly, and daily stock data** from a SQL database.
- **Volatility Models**:
  - **EWMA (Exponentially Weighted Moving Average)** volatility model.
  - **GARCH(1,1)** model, with flexibility to use other GARCH variations.
- **Diurnal Profile**: Estimates intraday volatility using the **Garman-Klass** volatility estimator.
- **Intraday Volatility Prediction**: Scales daily volatility to intraday levels with diurnal components.
- **Visualization**: Provides functions to visualize predicted vs. realized volatility and diurnal patterns.

---

## Architecture

The key components of this project are:

### 1. **Data Retrieval**

- **`Pipeline`**: Class for fetching stock data at different frequencies (minute, hour, day).

### 2. **Volatility Models**

- **`ewma_vol()`**: Calculates daily volatility using the **EWMA** method.
- **`garch_vol()`**: Computes daily volatility using the **GARCH(1,1)** model, with options for variations.

### 3. **Diurnal Profile Calculation**

- Utilizes **Garman-Klass volatility** to estimate normalized intraday volatility for different times of the day.

### 4. **Intraday Volatility Prediction**

- Combines daily volatility, diurnal components, and dynamic averages to predict future intraday volatility:
