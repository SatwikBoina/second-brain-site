---
type: moc
domain: machine-learning
category: regression
tags:
  - moc
  - regression
  - evaluation-metrics
  - ML
---

## 🧮 Error-Based Metrics

### Absolute Error Family
- [[MAE - Mean Absolute Error]]
- [[Median Absolute Error]]
- [[WMAPE — Weighted Mean Absolute Percentage Error]]

---

### Squared Error Family
- [[MSE — Mean Squared Error]]
- [[RMSE — Root Mean Squared Error]]
- [[Huber Loss]]

---

### Percentage Error Family
- [[MAPE — Mean Absolute Percentage Error]]
- [[sMAPE — Symmetric Mean Absolute Percentage Error]]

---

### Log-Based Metrics
- [[RMSLE — Root Mean Squared Log Error]]

---

## 📈 Variance Explained Metrics

- [[R-squared— Coefficient of Determination]]
- [[Adjusted R-squared]]

---

## 📉 Bias & Directional Metrics

- [[Mean Bias Error]]
- [[Forecast Bias Percentage]]
- [[Tracking Signal]]

---

## 📊 Forecasting-Specific Metrics

- [[WMAPE — Weighted Mean Absolute Percentage Error]]
- [[MASE — Mean Absolute Scaled Error]]
- [[Forecast Accuracy]]

---

## 📐 Likelihood & Model Selection Metrics

- [[AIC — Akaike Information Criterion]]
- [[BIC — Bayesian Information Criterion]]

---

## 🧠 Distribution-Based Metrics

- [[Quantile Loss (Pinball Loss)]]
- [[Poisson Deviance]]
- [[Gamma Deviance]]
- [[Tweedie Deviance]]

---

## 🔗 Core Supporting Concepts

- [[Residuals]]
- [[Loss Function vs Evaluation Metric]]
- [[Bias–Variance Tradeoff]]
- [[Cross Validation]]
- [[Overfitting and Underfitting]]

---

## 🏭 Business & Industry Views

- [[Forecast Accuracy Metrics in FMCG]]
- [[Demand Forecast Evaluation]]
- [[Promotion Forecast Validation]]
- [[Hierarchy Forecasting Metrics]]

---

## 🧩 Metric Selection Guide

| Scenario | Preferred Metric |
|-------|-------|
| Business forecasting | [[WMAPE]] |
| Model optimization | [[RMSE]] |
| Relative growth modeling | [[RMSLE]] |
| Interpretability | [[MAE - Mean Absolute Error]] |
| Reporting to leadership | [[WMAPE]] |
| Linear regression quality | [[Adjusted R-squared]] |
| Comparing models | [[AIC]] / [[BIC]] |
| Long-tail SKUs | [[MASE]] |

---

## ⚠️ Common Pitfalls

- Using only R² for model selection
- Optimizing on MAPE
- Ignoring scale sensitivity
- Mixing loss functions and evaluation metrics
- Comparing metrics across different data scales

---

## 🎯 Interview Perspective

Know how to answer:

- Why multiple metrics are required
- Difference between RMSE and MAE
- Why MAPE fails in real data
- Why WMAPE is preferred in FMCG
- Why RMSLE suits log-log models
- Why R² is misleading

---

## 🧠 Mental Model

