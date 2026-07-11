# 📈 Time Series Forecasting of the NIFTY 50 Index using ARIMA

A statistical time series forecasting project that applies the **AutoRegressive Integrated Moving Average (ARIMA)** model to forecast the **NIFTY 50 Index** using over ten years of historical daily market data. The project demonstrates a complete forecasting workflow, from data acquisition and exploratory analysis to model selection, forecasting, and residual diagnostics.

---

## Project Overview

Time series forecasting plays a significant role in financial analysis by helping identify underlying patterns in historical market data. In this project, the NIFTY 50 Index is modelled using the ARIMA framework after examining stationarity and selecting an appropriate model based on statistical criteria.

The project follows an end-to-end workflow that includes:

- Historical data collection using the Yahoo Finance API
- Exploratory Data Analysis (EDA)
- Stationarity testing using the Augmented Dickey-Fuller (ADF) Test
- Time series differencing
- ACF and PACF analysis
- ARIMA model selection using Akaike Information Criterion (AIC)
- Forecast generation
- Performance evaluation
- Residual diagnostics

---

## Dataset

| Attribute | Details |
|-----------|---------|
| **Index** | NIFTY 50 |
| **Source** | Yahoo Finance |
| **Access Method** | `yfinance` Python API |
| **Frequency** | Daily |
| **Time Period** | January 2015 – Latest Available Date |
| **Variables** | Open, High, Low, Close, Volume |

The dataset is downloaded dynamically using the `yfinance` library, making the notebook fully reproducible without requiring manual dataset downloads.

---

## Methodology

The complete modelling pipeline is illustrated below:

```text
Historical Data Collection
          │
          ▼
Exploratory Data Analysis
          │
          ▼
Train-Test Split (85 : 15)
          │
          ▼
ADF Stationarity Test
          │
          ▼
Differencing (if required)
          │
          ▼
ACF & PACF Analysis
          │
          ▼
Candidate ARIMA Models
          │
          ▼
Model Selection using AIC
          │
          ▼
Forecast Generation
          │
          ▼
Performance Evaluation
          │
          ▼
Residual Diagnostics
```

---

## Model Selection

Multiple candidate ARIMA models were trained and compared using the **Akaike Information Criterion (AIC)**.

| Model | AIC |
|--------|------:|
| **ARIMA(2,1,2)** | **30422.19** |
| ARIMA(1,1,2) | 30424.37 |
| ARIMA(2,1,1) | 30424.42 |
| ARIMA(1,1,1) | 30425.45 |
| ARIMA(3,1,1) | 30425.93 |
| ARIMA(3,1,2) | 30428.57 |

The model with the lowest AIC, **ARIMA(2,1,2)**, was selected as the final forecasting model.

---

## Performance

| Metric | Value |
|--------|------:|
| **Mean Absolute Error (MAE)** | **919.56** |
| **Root Mean Squared Error (RMSE)** | **1130.66** |
| **Mean Absolute Percentage Error (MAPE)** | **3.85%** |

The evaluation indicates that the ARIMA model provides a reasonable statistical baseline for short-term forecasting of the NIFTY 50 Index.

---

## Visualizations

The notebook includes:

- Historical NIFTY 50 Closing Price
- Rolling Mean and Rolling Standard Deviation
- Correlation Matrix
- ACF and PACF Plots
- Actual vs Forecast Comparison
- Residual Time Series
- Residual Distribution
- Q-Q Plot

---

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Statsmodels
- Scikit-learn
- Yahoo Finance API (`yfinance`)
- Google Colab

---

## Repository Structure

```text
.
├── ARIMA_NIFTY50.ipynb
├── README.md
└── requirements.txt
```

---

## Limitations

While ARIMA is a widely used statistical forecasting model, it has several limitations when applied to financial time series:

- Assumes linear relationships in the data.
- Does not explicitly model changing market volatility.
- Cannot capture unexpected macroeconomic or geopolitical events.
- Produces smoother forecasts over longer forecasting horizons.
- Limited ability to model nonlinear market behaviour.

---

## Future Work

Possible extensions of this project include:

- Seasonal ARIMA (SARIMA)
- GARCH-based volatility modelling
- Prophet forecasting
- LSTM-based deep learning models
- Transformer-based time series forecasting
- ARIMAX/SARIMAX models incorporating external economic indicators

---

## Key Takeaways

- Developed an end-to-end statistical forecasting pipeline for the NIFTY 50 Index.
- Applied stationarity testing and differencing prior to model development.
- Compared multiple ARIMA models using the Akaike Information Criterion (AIC).
- Selected **ARIMA(2,1,2)** as the optimal forecasting model.
- Evaluated forecasting performance using MAE, RMSE, and MAPE.
- Performed residual diagnostics to assess model adequacy and identify forecasting limitations.

---

## Conclusion

This project demonstrates the application of the ARIMA model to financial time series forecasting using more than ten years of historical NIFTY 50 data. After verifying stationarity and comparing multiple candidate models using the Akaike Information Criterion (AIC), **ARIMA(2,1,2)** was selected as the final forecasting model.

The model achieved a **Mean Absolute Percentage Error (MAPE) of 3.85%**, indicating reasonable short-term forecasting performance. Residual diagnostics suggest that although the model captures the underlying trend, it is unable to fully represent the nonlinear and highly stochastic nature of financial markets. Consequently, the ARIMA model serves as a strong statistical baseline, while more advanced approaches may further improve forecasting performance.

---
