# 📌 MOC — Time Series Analysis & Forecasting

> Central hub for **Time Series** in Machine Learning and Statistics.
> Time series problems involve data collected **over time**, where **order, dependence, and temporal structure** are fundamental.

---

## 1. Core Idea

A time series is a sequence of observations indexed by time:

\[
X = \{x_1, x_2, \dots, x_T\}
\]

Key difference from standard ML:
> **Observations are NOT independent**.

Past influences present.  
Order matters.  
Shuffling breaks meaning.

---

## 2. Why Time Series Is Different from Standard ML

Time series violates core ML assumptions:

- IID assumption ❌
- Random train–test split ❌
- Stationarity often ❌

Instead, we must handle:
- Temporal dependence
- Trends and seasonality
- Concept drift
- Delayed effects

---

## 3. Types of Time Series Problems

---

### 3.1 Time Series Forecasting

Goal:
- Predict future values

Examples:
- Sales forecasting
- Demand planning
- Stock prices

---

### 3.2 Time Series Classification

Goal:
- Assign labels to sequences

Examples:
- Fault detection
- Activity recognition

---

### 3.3 Time Series Anomaly Detection

Goal:
- Detect unusual temporal patterns

Examples:
- Fraud spikes
- System failures

---

### 3.4 Time Series Regression

Goal:
- Predict continuous values using temporal features

---

## 4. Components of a Time Series

A time series is often decomposed into:

- Trend
- Seasonality
- Cyclic patterns
- Noise

Understanding components guides model choice.

---

## 5. Stationarity (Critical Concept)

Many models assume **stationarity**.

Stationary series:
- Constant mean
- Constant variance
- Stable autocorrelation

Most real-world series are **non-stationary**.

🔗 Related:
- [[Stationarity]]
- [[Differencing]]

---

## 6. Temporal Dependence

Key concepts:
- Autocorrelation (ACF)
- Partial autocorrelation (PACF)
- Lag features

Past values influence future values.

---

## 7. Classical Time Series Models

---

### 7.1 Autoregressive Models

- AR
- MA
- ARMA
- ARIMA
- SARIMA

Characteristics:
- Strong assumptions
- Interpretable
- Data-efficient

---

### 7.2 State Space Models

- Kalman Filter
- Structural Time Series

Used for:
- Dynamic systems
- Hidden states

---

## 8. Machine Learning for Time Series

ML adapts time series into **supervised learning** using features.

Approaches:
- Lag-based features
- Rolling statistics
- Calendar features

Models:
- Linear Regression
- Tree-based models
- Gradient Boosting

🔗 Related:
- [[Regression — MOC]]
- [[Ensemble Learning — MOC]]

---

## 9. Deep Learning for Time Series

Used when:
- Large datasets
- Complex temporal patterns

Models:
- RNN
- LSTM
- GRU
- Temporal CNNs
- Transformers

🔗 Related:
- [[Neural Networks — MOC]]

---

## 10. Feature Engineering for Time Series

Crucial techniques:
- Lag features
- Rolling windows
- Exponentially weighted stats
- Fourier terms
- Calendar effects

Feature design often matters more than model choice.

---

## 11. Evaluation in Time Series

Standard CV fails.

Correct strategies:
- Temporal train–test split
- Rolling / expanding window validation
- Backtesting

Metrics must respect time ordering.

🔗 Related:
- [[Evaluation Metrics — MOC]]
- [[Cross Validation]]

---

## 12. Forecast Horizons

Different horizons = different problems:

- Short-term
- Medium-term
- Long-term

Model performance degrades as horizon increases.

---

## 13. Error Analysis in Time Series

Look for:
- Bias across seasons
- Drift over time
- Regime changes

Temporal error patterns matter more than averages.

🔗 Related:
- [[Error Analysis]]

---

## 14. Time Series and Concept Drift

Distributions change over time.

Causes:
- Market shifts
- User behavior changes
- External shocks

Models must adapt.

🔗 Related:
- [[Concept Drift]]

---

## 15. Time Series and Probabilistic Forecasting

Uncertainty increases with time.

Often better to predict:
- Prediction intervals
- Distributions, not points

🔗 Related:
- [[Probabilistic Models — MOC]]

---

## 16. Common Pitfalls

- ❌ Random shuffling  
- ❌ Data leakage from future  
- ❌ Ignoring seasonality  
- ❌ Using static CV  
- ❌ Assuming stationarity blindly  

Time series punishes shortcuts.

---

## 17. How Time Series Fits in ML

Data with Time Order  
↓  
Time Series Modeling ← this  
↓  
Forecasting / Detection / Decisions

Time series is **sequence modeling under uncertainty**.

---

## 18. Relationship to Other Concepts

Time series connects strongly to:

- [[Regression — MOC]]
- [[Classification — MOC]]
- [[Probabilistic Models — MOC]]
- [[Neural Networks — MOC]]
- [[Evaluation Metrics — MOC]]
- [[Error Analysis]]

---

## Usage Rules

- This MOC is a conceptual + navigational hub
- Each model family lives in its own note
- Never randomize time
- Always ask: *what temporal structure exists?*
