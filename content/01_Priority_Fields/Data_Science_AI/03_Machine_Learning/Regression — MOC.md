# 📌 MOC — Regression

> Central Map of Content for all **regression problems** in Machine Learning.
> Regression models predict a **continuous target variable**.

---

## 1. What is Regression?

Regression focuses on modeling the relationship between input features and a **continuous outcome**, optimizing prediction accuracy and generalization.

---

## 2. Regression Model Families

Algorithms are grouped by **learning philosophy**, not by popularity.

---

### 2.1 Linear Models

Models that are **linear in parameters**.

- [[Linear Models — MOC]]

Includes:
- [[Linear Regression]]
- [[Polynomial Regression]]
- [[Ridge Regression]]
- [[Lasso Regression]]
- [[Elastic Net]]

---

### 2.2 Tree-Based Models

Models that learn **hierarchical decision rules**.

- [[Tree-Based Models — MOC]]

Includes:
- [[Decision Tree Regressor]]
- [[Random Forest Regressor]]
- [[Gradient Boosting Regressor]]
- [[XGBoost Regressor]]
- [[LightGBM Regressor]]
- [[CatBoost Regressor]]

---

### 2.3 Distance-Based Models

Models based on **similarity and proximity** in feature space.

- [[Distance-Based Models — MOC]]

Includes:
- [[k-NN Regressor]]

---

### 2.4 Kernel-Based Models

Models that rely on **implicit feature mappings**.

- [[Kernel Methods — MOC]]

Includes:
- [[Support Vector Regression]]
- [[Kernel Ridge Regression]]

---

## 3. Loss Functions for Regression

Loss functions define *what the model optimizes*.

- [[Regression Loss Functions — MOC]]
- [[Squared Error Loss]]
- [[MAE - Mean Absolute Error]]
- [[Huber Loss]]
- [[Quantile Loss]]

---

## 4. Evaluation Metrics

Used to assess regression performance.

- [[Regression Metrics — MOC]]
- [[MSE — Mean Squared Error]]
- [[RMSE — Root Mean Squared Error]]
- [[MAE - Mean Absolute Error]]
- [[R-squared— Coefficient of Determination]]
- [[Adjusted R-squared]]

---

## 5. Bias–Variance Perspective

All regression models trade off:

- Model complexity
- Generalization
- Sensitivity to noise

🔗 Core concept:
- [[Bias–Variance Tradeoff]]

---

## 6. Feature Engineering for Regression

Regression performance depends heavily on features.

- [[Feature Scaling]]
- [[Feature Selection]]
- [[Polynomial Features]]
- [[Outliers]]
- [[Handling Missing Data]]

---

## 7. Model Selection & Validation

Choosing the right regression model.

- [[Train-Test Split]]
- [[Cross Validation]]
- [[Hyperparameter Tuning — MOC]]
- [[Model Selection]]

---

## 8. Interpretability & Diagnostics

Understanding and trusting regression models.

- [[Residual Analysis]]
- [[Model Interpretability]]
- [[Coefficient Interpretation in Linear Models]]
- [[Feature Importance]]

---

## 9. Practical Considerations

- [[Overfitting vs Underfitting]]
- [[Multicollinearity]]
- [[Data Leakage]]
- [[Extrapolation Risk]]

---

## 10. Relationship to Other Learning Tasks

- Contrast with [[Classification — MOC]]
- Foundation for [[Time Series — MOC]]
- Used in [[Forecasting]]

---

## Usage Rules

- This MOC contains **no derivations**
- Algorithms must live in separate notes
- Concepts must remain atomic
- Extend by adding links, not explanations
