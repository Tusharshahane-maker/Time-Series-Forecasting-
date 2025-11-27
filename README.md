
# ⏱️ Time Series Forecasting — ARIMA & SARIMAX (Univariate)

This repository provides a complete workflow for **univariate time series forecasting** using the classical statistical models **ARIMA** and **SARIMAX**. It covers data preparation, exploratory analysis, model training, hyperparameter tuning, diagnostics, and future forecasting.

---

## 📌 Features

* ✔️ Data cleaning & preprocessing
* ✔️ Exploratory time series analysis (trend, seasonality, stationarity)
* ✔️ Differencing & transformations to achieve stationarity
* ✔️ ARIMA model selection using AIC/BIC / auto-arima
* ✔️ SARIMAX for capturing seasonality and exogenous effects (if needed)
* ✔️ Residual diagnostics & model validation
* ✔️ Forecast visualization & evaluation

---

## 📂 Project Structure (example)

```
├── data/
│   └── time_series.csv
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_arima_model.ipynb
│   └── 03_sarimax_model.ipynb
├── src/
│   ├── utils.py
│   ├── arima_model.py
│   └── sarimax_model.py
├── results/
│   └── forecasts.png
└── README.md
```

---

## 🔧 Installation

```bash
pip install -r requirements.txt
```

**Key libraries:**

* `pandas`
* `numpy`
* `statsmodels`
* `pmdarima`
* `matplotlib / seaborn`

---

## 🚀 Usage

### 1️⃣ Load & preprocess the dataset

```python
import pandas as pd

df = pd.read_csv("data/time_series.csv", parse_dates=True, index_col="date")
ts = df["value"]
```

### 2️⃣ Fit ARIMA

```python
from pmdarima import auto_arima

model = auto_arima(ts, seasonal=False, trace=True)
forecast = model.predict(n_periods=30)
```

### 3️⃣ Fit SARIMAX (for seasonal data)

```python
from statsmodels.tsa.statespace.sarimax import SARIMAX

model = SARIMAX(ts, order=(1,1,1), seasonal_order=(1,1,1,12))
results = model.fit()
forecast = results.forecast(steps=30)
```

---

## 📊 Model Evaluation

* Residual diagnostics (ACF/PACF)

---

✅ badges, visuals, or diagrams
Just tell me your repo name or upload your code!
