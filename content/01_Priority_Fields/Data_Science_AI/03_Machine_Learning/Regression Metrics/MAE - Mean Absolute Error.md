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

## One-line idea
> Measures the average magnitude of prediction errors in the same unit as the target variable It is the average distance from the truth.

---

## Formula
$$
MAE = \frac{1}{n}\sum_{i=1}^{n} |y_i - \hat{y}_i|
$$

---

## Intuition
- Computes how far predictions are from actual values on average
- Treats all errors equally
- Does not amplify large errors

---
## Visual Aid 
![[MAE_ARCHER.png]]

## Range
- $(0 \rightarrow \infty)$
- Lower is better

---

## Unit
- Same unit as target variable  
  (e.g., sales units, revenue, demand)

---

## Strengths
- Easy to interpret
- Robust to outliers
- Linear penalty on errors
- Direct business meaning

---

## Limitations
- Does not penalize large errors strongly
- Not differentiable at zero
- Less sensitive to extreme misses

---

## Sensitive to Outliers?
- ❌ Low sensitivity
- Each error contributes linearly

---

## When to Use
- When outliers exist
- When consistent accuracy matters
- When business interpretability is important
- Baseline model comparison

---

## When NOT to Use
- When large errors are very costly
- When tail risk must be minimized
- When optimizing smooth loss functions

---

## Business Interpretation
- MAE = 120

👉 On average, predictions are off by **120 units**.

---

## Related Metrics
- [[WMAPE — Weighted Mean Absolute Percentage Error]]
- [[MAPE — Mean Absolute Percentage Error]]

---
## Key Takeaway
> MAE measures average error directly in business units, making it highly interpretable but less sensitive to extreme errors.

---