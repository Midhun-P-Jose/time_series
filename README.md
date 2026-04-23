Time Series Forecasting using ARIMA & Exponential Smoothing
📌 Overview

This project focuses on forecasting time series data (Sales) using multiple statistical models including:

ARIMA
Simple Exponential Smoothing (SES)
Holt’s Linear Trend Method
Holt-Winters (Triple Exponential Smoothing)

The objective is to compare model performance and identify the most suitable approach for the dataset.

📂 Dataset
The dataset contains time-based sales information with features such as:

Date
Sales
Customers
Promo
Holidays

The data is aggregated into a univariate time series using the Sales column.

⚙️ Preprocessing Steps

Converted Date column to datetime format
Sorted dataset by date
Set datetime as index
Checked for missing values
Removed invalid entries (e.g., zero sales when store closed)


📊 Exploratory Data Analysis (EDA)
Time series visualization
Trend and seasonality analysis
Seasonal decomposition
Boxplots (day, month, year)
Observations:
Strong weekly seasonality
No strong long-term trend
Presence of noise and fluctuations


📈 Models Implemented
🔹 1. ARIMA
Identified parameters using ACF & PACF
Built ARIMA model

Result:

MAPE ≈ 16%
Prediction: Flat line (underfitting)
Failed to capture seasonality
🔹 2. Simple Exponential Smoothing (SES)
No trend or seasonality

Result:

MAPE ≈ 21.5%
Prediction: Smooth but unrealistic
🔹 3. Holt’s Linear Method
Captures trend only

Result:

MAPE ≈ 94% ❌
Prediction: Unrealistic increasing trend
🔹 4. Holt-Winters (Triple Exponential Smoothing)
Captures trend + seasonality

Result:

MAPE ≈ 21.9%
Prediction: Seasonal pattern captured
📊 Model Comparison
Model	MAPE	Pattern Capture	Performance
ARIMA	16%	❌ No	Misleading
SES	21.5%	❌ No	Weak
Holt	94%	❌ Wrong	Poor
Holt-Winters	21.9%	✅ Yes	Best

🧠 Key Insights
Lower MAPE does not always mean better model
ARIMA performed well numerically but failed to capture real patterns
Holt-Winters successfully modeled seasonality, making it more realistic
Models that reflect real-world behavior are preferred over purely low-error models

✅ Final Conclusion

Holt-Winters (Triple Exponential Smoothing) is the most suitable model for this dataset as it effectively captures seasonal patterns, even though its error metrics are slightly higher than ARIMA.
