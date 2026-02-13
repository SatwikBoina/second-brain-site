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
> Measures the average squared difference between predicted and actual values, heavily penalizing large errors.

---

## Formula
$$
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2
$$

---

## Intuition
- Errors are **squared before averaging**
- Large mistakes become disproportionately costly
- Encourages models to avoid extreme errors

---
## Visual Aid 
![[MSE INFOGRAPHIC.png]]

## Range
- $(0 \rightarrow \infty)$
- Lower is better

---

## Unit
- Squared unit of target variable  
  (e.g., sales², demand²)

---

## Strengths
- Strong penalty for large errors
- Smooth and differentiable
- Works well with gradient-based optimization
- Mathematically convenient

---

## Limitations
- Difficult to interpret (squared units)
- Highly sensitive to outliers
- Not aligned with business understanding

---

## Sensitive to Outliers?
- ✅ Very high sensitivity
- Large errors dominate the metric

---

## When to Use
- Model training and optimization
- Gradient descent–based algorithms
- When large errors are unacceptable
- Mathematical modeling

---

## When NOT to Use
- Business reporting
- Interpretability-focused evaluation
- Data with extreme outliers

---

## Business Interpretation
- Limited direct business meaning due to squared units

Example:
> MSE = 10,000 → average squared error = 10,000 units²  
(not interpretable directly)

---

## Relationship to Other Metrics
- RMSE = √MSE (restores original units)
- MAE uses absolute error instead of squared
- MSE is the most common **loss function**


---

## Related Metrics
- [[RMSE — Root Mean Squared Error]]

## Key Takeaway
> MSE is mathematically elegant and ideal for optimization, but poorly interpretable and highly sensitive to outliers.

---
