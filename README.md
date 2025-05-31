#  Ethereum Price Forecasting Using ARIMA (2020–2024)

This project applies time series analysis using the ARIMA model to forecast Ethereum (ETH/USDT) prices based on historical data. The workflow includes data collection, preprocessing, exploratory analysis, model selection via ACF/PACF and AIC, model evaluation, and a 30-day forecast with confidence intervals.

---

## 🔧 Key Features

-  **Automated Data Collection** from Yahoo Finance using `yfinance`
-  **Data Cleaning & Structuring**: Includes daily `open`, `high`, `low`, `close`, `volume`, and calculated `market_cap`
-  **Exploratory Data Analysis (EDA)**: Visualizes trends, volatility, and rolling averages
-  **Stationarity Testing** using Augmented Dickey-Fuller (ADF) Test
-  **Model Selection & Tuning**: Optimal ARIMA(p, d, q) chosen using ACF/PACF and AIC
-  **Model Evaluation** using RMSE and MAPE
-  **30-Day Price Forecasting** with 95% confidence intervals


##  Methodology Overview

### 1. Data Collection
- **Source**: Yahoo Finance (`ETH-USD`)
- **Tool**: `yfinance` Python library
- **Period**: Jan 2020 – Dec 2024
- **Frequency**: Daily

### 2. Data Preparation
- Converted timestamps to datetime
- Cleaned null and invalid rows
- Calculated `market_cap` = `close × volume`
- Exported cleaned dataset to CSV

### 3. Exploratory Data Analysis (EDA)
- Line plots of daily closing price
- 30-day rolling average
- Volume trends
- Descriptive statistics

### 4. Stationarity Testing
- ADF Test on raw data → p-value = 0.31 (non-stationary)
- First-order differencing → p-value ≈ 0.00  (stationary)

### 5. ARIMA Model Development
- ACF and PACF analysis for selecting p and q
- Evaluated multiple (p, d, q) combinations
- Selected **ARIMA(2, 1, 2)** based on lowest AIC
- Verified residuals as white noise

### 6. Model Evaluation
- RMSE: **92.17**
- MAPE: **2.99%**
- Plotted predicted vs actual prices
- Analyzed residuals for randomness

### 7. Forecasting
- Forecasted Ethereum prices for the next 30 days
- Visualized forecast with 95% confidence bands

--

##  Setup Instructions

###  Requirements:
Install required packages:

```bash
pip install yfinance pandas numpy matplotlib statsmodels scikit-learn
