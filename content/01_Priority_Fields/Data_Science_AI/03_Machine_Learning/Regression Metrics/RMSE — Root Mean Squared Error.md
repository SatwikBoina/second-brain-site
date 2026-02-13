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
> Measures the typical magnitude of prediction error while penalizing large errors more strongly than MAE.

---

## Formula
$$
RMSE = \sqrt{
\frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2
}
$$

---

## Intuition
- Squares errors → emphasizes large mistakes
- Averages them → overall error level
- Square root restores original unit

---

## Range
- $(0 \rightarrow \infty)$
- Lower is better

---

## Unit
- Same unit as target variable  
  (e.g., sales units, revenue, demand)

---

## Strengths
- Penalizes large errors strongly
- Same unit as target variable
- Smooth and differentiable
- Widely used and well understood

---

## Limitations
- Highly sensitive to outliers
- Can be dominated by few large errors
- Less robust for noisy data

---

## Sensitive to Outliers?
- ✅ High sensitivity
- Squaring amplifies extreme residuals

---

## When to Use
- When large errors are costly
- Model comparison
- Evaluation after training
- Forecasting accuracy assessment

---

## When NOT to Use
- Heavy-tailed distributions
- Extreme outliers present
- When typical error matters more than worst-case error

---

## Business Interpretation
- RMSE = 150

👉 Typical prediction error is about **150 units**,  
with stronger penalty on large misses.

---

## Relationship to Other Metrics
- RMSE = √MSE
- MAE penalizes errors linearly
- RMSE penalizes errors quadratically
- WMAPE normalizes absolute error

---

## Related Metrics
- [[MSE — Mean Squared Error]]

---

## Key Takeaway
> RMSE reflects typical error magnitude while heavily penalizing large prediction mistakes.
