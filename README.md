# 📈 Stock Price Forecasting with ARIMA & SARIMAX

## 🔹 Project Overview
This project focuses on **forecasting Google (GOOG) stock closing prices** using **time series models** — specifically **ARIMA** and **SARIMAX**.  
The aim is to build a forecasting pipeline that starts from raw stock data, performs necessary statistical checks, and finally produces reliable **short-term forecasts** with confidence intervals.

---

## 🔹 Workflow

### 1. Data Collection
- Used **Yahoo Finance API (yfinance)** to download 1 year of historical stock prices of Google.
- Extracted relevant columns: **Date** and **Close Price**.

### 2. Data Visualization
- Plotted the **closing price trend** to observe stock movement over time.
- Identified the presence of **trend and seasonality** in the series.

### 3. Stationarity Check
- Applied **Augmented Dickey-Fuller (ADF) Test** to check if the data is stationary.
- Since the data showed **seasonality and trend**, differencing was applied to make it stationary.

### 4. ARIMA Model
- Built an **ARIMA(p, d, q)** model to test forecasting performance.
- Observed that ARIMA struggled because the data had strong **seasonal patterns**.

### 5. SARIMAX Model
- Implemented **SARIMAX(p, d, q)(P, D, Q, m)** from `statsmodels`.
- Seasonal order `(P, D, Q, m)` captures **monthly/periodic stock patterns**.
- SARIMAX outperformed ARIMA as it can handle **both trend and seasonality**.

### 6. Forecasting
- Generated **10-day ahead forecasts** for Google stock prices.
- Plotted results with:
  - Historical data
  - Predicted values
  - 95% confidence intervals (shaded region)

---

## 🔹 Results
- **ARIMA:** Poor fit due to ignoring seasonality.
- **SARIMAX:** Much better fit with clear short-term predictive capability.
- **Visualization:** Final plot shows **forecasted stock prices vs history**, highlighting model accuracy.

---

## 🔹 Tech Stack
- **Python**
- **Libraries:** pandas, numpy, matplotlib, statsmodels, yfinance
- **Models:** ARIMA, SARIMAX

---

## 🔹 Key Takeaways
- Stock price forecasting requires handling **non-stationarity** and **seasonality**.  
- **ARIMA is insufficient** for seasonal financial data.  
- **SARIMAX provides better forecasts**, especially for short-term prediction.  

---

## 🔹 How to Run
1. Clone this repo:
   ```bash
   git clone https://github.com/yourusername/Stock-Price-Forecasting.git
