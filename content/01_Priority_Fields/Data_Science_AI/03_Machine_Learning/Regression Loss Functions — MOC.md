# 📌 MOC — Regression Loss Functions

> Central hub for **loss functions used in regression problems**.
> Regression loss functions define *how prediction errors are measured* and directly influence robustness, bias–variance behavior, and model training dynamics.

---

## 1. Core Idea

A regression loss function quantifies the discrepancy between:

- True value \(y\)
- Predicted value $(\hat{y})$

The choice of loss function determines:
- Sensitivity to outliers
- Optimization behavior
- Bias–variance characteristics
- Business alignment of the model

---

## 2. Absolute Error Family (L1-based)

Loss functions that penalize **absolute deviations**.

Characteristics:
- Robust to outliers
- Median-oriented estimates
- Non-smooth at zero

### Losses
- [[MAE - Mean Absolute Error]]
- [[Median Absolute Error]]
- [[WMAPE — Weighted Mean Absolute Percentage Error]]
- [[sMAPE — Symmetric Mean Absolute Percentage Error]]

🔗 Related:
- [[Outliers]]
- [[Robust Statistics]]

---

## 3. Squared Error Family (L2-based)

Loss functions that penalize **squared deviations**.

Characteristics:
- Sensitive to outliers
- Mean-oriented estimates
- Smooth and differentiable

### Losses
- [[MSE — Mean Squared Error]]
- [[RMSE — Root Mean Squared Error]]
- [[R-squared— Coefficient of Determination]]
- [[Adjusted R-squared]]

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 4. Hybrid / Robust Losses

Loss functions designed to balance **robustness and smoothness**.

Characteristics:
- Quadratic for small errors
- Linear for large errors

### Losses
- [[Huber Loss]]
- [[Pseudo Huber Loss]]
- [[Quantile Loss]]

🔗 Related:
- [[Outliers]]
- [[Robust Regression]]

---

## 5. Percentage-Based Losses

Loss functions that measure **relative error**.

Characteristics:
- Scale-independent
- Sensitive near zero
- Useful for business metrics

### Losses
- [[MAPE — Mean Absolute Percentage Error]]
- [[sMAPE — Symmetric Mean Absolute Percentage Error]]
- [[WMAPE — Weighted Mean Absolute Percentage Error]]

🔗 Related:
- [[Scale Invariance]]

---

## 6. Logarithmic Error Losses

Loss functions that penalize **relative differences in log space**.

Characteristics:
- Focus on ratio errors
- Dampens large absolute deviations
- Requires strictly positive targets

### Losses
- [[Root Mean Squared Logarithmic Error]]
- [[Log-Cosh Loss]]

🔗 Related:
- [[Feature Transformation]]
- [[Log Transformation]]

---

## 7. Asymmetric Losses

Loss functions where **overprediction and underprediction are penalized differently**.

Characteristics:
- Business-driven
- Directional risk modeling

### Losses
- [[Quantile Loss]]
- [[Pinball Loss]]

🔗 Related:
- [[Cost-Sensitive Learning]]

---

## 8. Loss Functions and Outliers

| Loss Family | Outlier Sensitivity |
|-----------|--------------------|
| L2 (MSE) | Very High |
| L1 (MAE) | Low |
| Huber | Medium |
| Log-based | Low |
| Quantile | Configurable |

🔗 Core concept:
- [[Outliers]]

---

## 9. Loss Functions and Bias–Variance

- L2 losses → low bias, high variance
- L1 losses → higher bias, lower variance
- Hybrid losses → controlled tradeoff

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 10. Loss Functions and Optimization

Loss choice affects:
- Gradient smoothness
- Convergence speed
- Stability of training

Examples:
- MSE → smooth gradients
- MAE → unstable gradients near zero
- Huber → stable compromise

🔗 Related:
- [[Gradient Descent]]

---

## 11. Algorithm-Specific Preferences

| Algorithm | Common Loss |
|--------|-------------|
| Linear Regression | MSE |
| Ridge / Lasso | MSE + penalty |
| Quantile Regression | Quantile Loss |
| Gradient Boosting | MSE / MAE / Huber |
| XGBoost | Custom loss |
| LightGBM | Custom loss |
| CatBoost | Custom loss |

---

## 12. Business Alignment Perspective

Loss functions encode **what “error” means**:

- Revenue forecasting → WMAPE
- Demand forecasting → RMSLE
- Risk modeling → Quantile loss

Choosing the wrong loss optimizes the wrong objective.

---

## 13. Common Misconceptions

- ❌ Lower loss always means better business outcome  
- ❌ One loss works for all problems  
- ❌ R² is a loss function  
- ❌ Robust losses remove need for data cleaning  

Loss functions reflect **priorities**, not truth.

---

## 14. Relationship to Evaluation Metrics

- Loss functions → optimized during training
- Metrics → used for evaluation

They may differ intentionally.

🔗 Related:
- [[Evaluation Metrics — MOC]]

---

## Usage Rules

- No derivations in this MOC
- Each loss function lives in its own note
- Algorithms should link to the chosen loss
- Extend via links, not explanations
