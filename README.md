## 📈 NVIDIA Stock Price Dataset (1999 - 2025) 🚀

### 📝 Dataset Overview

This dataset contains historical stock price data for NVIDIA Corporation (NVDA) from *1999 to 2025, extracted from *Yahoo Finance using the yfinance library. NVIDIA is a global leader in AI, gaming, and high-performance computing, making its stock highly relevant for financial analysis and machine learning models.

### 📊 Data Summary

Column Name	Description

📅 Date--->	Trading date (YYYY-MM-DD)
⬆ Open---->  Opening stock price of the day
🔼 High---->  Highest stock price of the day
🔽 Low---->	 Lowest stock price of the day
📉 Close----> Closing stock price of the day
🔄 Adj Close--->  Adjusted closing price after stock splits & dividends
📦 Volume---->  Number of shares trade



## Project Overview
This project analyzes NVIDIA's stock prices from January 1999 to February 2025 using time series analysis techniques. The project includes exploratory data analysis (EDA), data preprocessing, stock price prediction, and evaluation using metrics such as RMSE and MAPE. Various prediction algorithms, including Simple Moving Average (SMA), Exponential Weighted Moving Average (EWMA), and Long Short-Term Memory (LSTM), are applied to forecast trends.

---

## 1. Exploratory Data Analysis (EDA) with Time Series
### 1.1 Data Reading
- The dataset consists of daily stock prices of NVIDIA from 1999 to 2025.
- The 'Date' column is set as the index to facilitate time series analysis.

### 1.2 Time Resampling
- Resampling is performed to analyze stock prices at different intervals (weekly, monthly, yearly) for trend identification.

### 1.3 Time Shifts
- Shifting data forward or backward helps in understanding past trends' influence on future values.

### 1.4 Rolling Mean and Expanding Mean
- Rolling mean smooths out short-term fluctuations to highlight longer-term trends.
- Expanding mean considers all available data up to the current point for trend analysis.

### 1.5 Time Series Visualization
- Various attributes such as 'Open', 'High', 'Low', 'Close', 'Volume' are plotted over time to identify patterns.
- Moving averages (10-day, 30-day, 50-day) are compared with actual stock prices.

### 1.6 Observations
1. The data spans from January 1999 to February 2025.
2. There is an overall increase in 'High' values over the years.
3. A decline in stock prices was observed between 2020 and 2024.
4. Volume of traded shares significantly decreased in early 2022, a year before the dip in stock prices.
5. The adjusted closing price saw a sudden increase after 2023.
6. On January 7, 2025, NVIDIA achieved its highest stock price of 153.13 USD
7. The 10-day SMA closely follows the actual stock price, suggesting a strong trend.
8. The 50-day EWMA provides better smoothing and interpretability.
9. The lowest stock price was recorded on June 3, 1999, at $0.035.

---

## 2. Data Preprocessing
### 2.1 Standardization
- StandardScaler is used instead of MinMaxScaler to handle stock price fluctuations more effectively.

### 2.2 Training and Testing Data Split
- The dataset is split into training and testing sets for model evaluation.

---

## 3. Prediction Models
### 3.1 Moving Average (MA)
- SMA is used for trend identification.
- Common periods used: 20-day (short-term), 50-day (medium-term), 200-day (long-term).
- SMA provides a general idea of price trends but lags behind real-time fluctuations.

### 3.2 Exponential Weighted Moving Average (EWMA)
- EWMA assigns higher weights to recent prices, making it more responsive to market changes.
- The 50-day EWMA shows better trend identification than the 200-day EWMA.

### 3.3 Long Short-Term Memory (LSTM)
- LSTM, a deep learning model, is applied for stock price prediction.
- Hyperparameters:
  - LSTM units: 128
  - Optimizer: Adam (learning rate = 0.0001)
  - Epochs: 50
  - Batch size: 32
- Data is transformed using a predefined function that takes 50 past data points to predict the next value.

---

## 4. Evaluation Metrics
### 4.1 Root Mean Squared Error (RMSE)
- Measures the difference between predicted and actual values.

### 4.2 Mean Absolute Percentage Error (MAPE)
- Evaluates the relative accuracy of predictions compared to actual values.

| Model  | RMSE | MAPE (%) |
|--------|------|----------|
| SMA    | 6.8688 | 10.7071 |
| EWMA   | 6.0438 | 9.5945  |
| LSTM   | 7.5679 | 6.1034  |

**Conclusion:**
- EWMA performs better than SMA in terms of trend analysis and prediction.
- LSTM provides promising results with the lowest MAPE, indicating good predictive accuracy.

---

## Future Improvements
- Implementing ARIMA and Prophet models for better time series forecasting.
- Hyperparameter tuning for LSTM to improve accuracy.
- Incorporating external market factors such as economic indicators and news sentiment analysis.
- Exploring Transformer-based deep learning models for stock prediction.

This analysis provides valuable insights into NVIDIA's stock price trends and forecasting, leveraging various statistical and machine learning techniques.

