

## 📈 Objective

To predict hourly electricity load in Italy using historical demand data, solar generation, and temporal features. The predictions aim to support better load planning, peak demand management, and integration of renewable energy.

---

## 📦 Dataset Overview

- **Time Period**: January 1, 2016 to December 31, 2016 (hourly resolution)
- **Features**:
  - `utc_timestamp`: Timestamp of observation
  - `IT_load_new`: Electricity demand in MW (target variable)
  - `IT_solar_generation`: Solar generation in MW (external regressor)

---

## 🔧 Methods Used

| Model | Description | Accuracy |
|-------|-------------|----------|
| **Prophet** | Additive model with trend + daily/weekly seasonality | MAE ≈ 4,336 MW |
| **Prophet + Solar** | Adds `IT_solar_generation` as external regressor | MAE ≈ 4,200 MW |
| **XGBoost (Tuned)** | Tree-based model with lags, time features, and solar | **MAE ≈ 573 MW**, RMSE ≈ 811 MW |

---

## 📊 Feature Engineering

- Lag features: `lag1`, `lag24`
- Calendar features: `hour`, `dayofweek`
- External regressor: `IT_solar_generation`
- Hyperparameter tuning via `RandomizedSearchCV`

---

## 📉 Evaluation Metrics

- **MAE (Mean Absolute Error)**
- **RMSE (Root Mean Squared Error)**
- Visual plots of actual vs forecast

---

## 📌 Key Insights

- **XGBoost outperformed** both SARIMA and Prophet models in accuracy
- Short-term lags and calendar features are strong predictors
- External solar generation improved Prophet’s performance slightly

---

## 🚀 Future Improvements

- Integrate weather data (temperature, humidity)
- Incorporate holiday effects
- Add rolling retraining for real-time forecasting
- Explore deep learning models (LSTM, Temporal Fusion Transformer)

---

## 🤝 Acknowledgements

Special thanks to the academic support and open data resources enabling the simulation and analysis of real-world energy forecasting problems.



