---
type: zettel
domain: machine-learning
category: regression
topic: evaluation-metric
status: draft
tags:
  - regression
  - evaluation-metrics
  - ML
---


---
## One-line idea
> Measures the average squared difference between logarithms of actual and predicted values, focusing on relative growth rather than absolute error.

---

## Formula
$$
RMSLE =
\sqrt{
\frac{1}{n}
\sum_{i=1}^{n}
\left(
\log(y_i + 1) - \log(\hat{y}_i + 1)
\right)^2
}
$$

---

## Intuition
- Compares **log-scale differences**
- Penalizes **relative errors**, not absolute differences
- Treats 10→20 and 100→200 similarly
- Focuses on growth ratios

## Visual Aid
![[RMSLE.png]]
---

## Range
- $(0 \rightarrow \infty)$
- Lower is better

---

## Unit
- Log-scaled unit (dimensionless)

---

## Strengths
- Handles skewed targets well
- Reduces impact of large absolute values
- Penalizes under-prediction more than over-prediction
- Ideal for multiplicative relationships

---

## Limitations
- Requires non-negative targets
- Cannot handle negative values
- Less interpretable for business users
- Not suitable for zero-heavy series (without care)

---

## Sensitive to Outliers?
- ❌ Low sensitivity to large absolute outliers
- Sensitive to relative deviations

---

## When to Use
- Log-log regression models
- Demand modeling
- Price elasticity estimation
- Growth prediction
- Long-tailed target distributions

---

## When NOT to Use
- Negative target values
- Absolute error matters more than growth
- Linear-scale forecasting problems

---

## Business Interpretation
- RMSLE = 0.2

👉 Typical prediction error ≈ **20% in relative terms**  
(approximately multiplicative error)

---

## Relationship to Other Metrics
- RMSE → absolute error
- RMSLE → relative error
- MAE → linear penalty
- WMAPE → business-weighted MAE

---

## Related Metrics
- [[RMSE — Root Mean Squared Error]]

---

## Key Takeaway
> RMSLE evaluates relative prediction error and is best suited for multiplicative relationships and skewed targets.

---
