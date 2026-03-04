# 🌞 Solar Power Generation Forecasting
### Time Series Modeling with ARIMA & SARIMAX

> Data-driven forecasting of solar photovoltaic power using classical statistical time series models with meteorological features.

---

## 🚀 Project Summary

This project builds and evaluates forecasting models for daily solar power generation.

We compare:

| Model | Type |
|-------|------|
| 📉 Polynomial Trend Model | Baseline |
| 📊 ARIMA | Statistical |
| 🌦 SARIMAX | Seasonal + Weather Variables |

The objective is to determine whether incorporating exogenous meteorological variables improves forecasting accuracy.

---

## 🧠 Business Motivation

Accurate solar power forecasting enables:

- ⚡ Grid stability and load balancing
- 📅 Renewable energy scheduling
- 💹 Energy trading optimization
- 🏭 Operational efficiency planning

> Solar output is inherently weather-dependent and seasonal — making it a strong candidate for advanced time series modeling.

---

## 📂 Dataset

Daily aggregated solar plant data with **3,157 observations**:

| Feature | Description |
|---------|-------------|
| `AC_POWER` | Solar power generation (kW) |
| `AMBIENT_TEMPERATURE` | Environmental temperature (°C) |
| `MODULE_TEMPERATURE` | Solar panel temperature (°C) |
| `IRRADIATION` | Solar radiation intensity (W/m²) |

---

## 🔎 Exploratory Data Analysis

The notebook includes:

- 📈 Time series visualization
- 🔥 Correlation heatmap
- 🔄 Seasonal decomposition
- 📉 ACF & PACF analysis
- 🧪 Stationarity testing (ADF test)

### 📌 Stationarity Results

| Series | ADF p-value |
|--------|-------------|
| Original | 0.00826 |
| Differenced | 0.0000736 |

> ✅ The series becomes fully stationary after first differencing.

---

## ⚙️ Modeling Approach

### 1️⃣ Polynomial Regression
Baseline model capturing long-term trend only.

### 2️⃣ ARIMA(1,1,1)
Captures internal autocorrelation but ignores weather effects.

### 3️⃣ SARIMAX(1,1,1)(1,1,1,7)
Includes:
- 📅 Weekly seasonality
- 🌡️ Ambient temperature
- ☀️ Module temperature
- 🌤️ Irradiation

---

## 📊 Model Performance

| Model | RMSE | MAE | AIC |
|-------|------|-----|-----|
| Polynomial | 77,005.28 | — | — |
| ARIMA | 148,789.72 | 141,700.60 | 505.65 |
| **SARIMAX** | **20,990.94** | **17,028.60** | **482.62** |

---

## 🎯 Key Insights

- ✅ **SARIMAX reduces RMSE by ~85%** compared to ARIMA
- 🌦️ Weather variables significantly improve predictive accuracy
- 📅 Weekly seasonality (`s = 7`) is strongly present
- 🔬 Residual diagnostics confirm model adequacy *(Ljung–Box p = 0.0755)*
- 🏆 SARIMAX clearly outperforms traditional ARIMA

---

## 📈 Forecasting Output

The SARIMAX model:

- Tracks actual test data closely
- Captures seasonal structure
- Produces stable short-term forecasts
- Generates reliable confidence intervals

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat)
![Statsmodels](https://img.shields.io/badge/Statsmodels-3A5FCD?style=flat)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)

---

## 📁 Project Structure

```
Solar-Power-Forecasting/
│
├── Solar_Forecasting_Notebook.ipynb
├── Project_Report.pdf
├── data/
│   └── solar_data.csv
└── README.md
```

---

## 🧪 How to Run

**1. Install dependencies:**
```bash
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn
```

**2. Launch the notebook:**
```bash
jupyter notebook Solar_Forecasting_Notebook.ipynb
```

---

## 📌 Future Improvements

- [ ] Hyperparameter optimization
- [ ] Cross-validation for time series
- [ ] LSTM / Deep learning models
- [ ] Hybrid forecasting approaches
- [ ] Multi-year dataset expansion

---

## 👩‍💻 Author

**P.M. Sanodya V. Jinadasa**  
BSc in Data Science  
Sabaragamuwa University of Sri Lanka

---

<p align="center">
  <i>If you found this project helpful, please consider giving it a ⭐</i>
</p>
