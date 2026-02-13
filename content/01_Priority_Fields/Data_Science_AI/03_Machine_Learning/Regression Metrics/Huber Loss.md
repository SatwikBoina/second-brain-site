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
> Combines MAE and MSE by penalizing small errors quadratically and large errors linearly.

---

## Formula


Let residual be:
$$
r = y - \hat{y}
$$
Huber loss with threshold $( \delta)$:
$$

L_\delta(r) =
\begin{cases}
\frac{1}{2}r^2 & \text{if } |r| \le \delta \\
\delta(|r| - \frac{1}{2}\delta) & \text{if } |r| > \delta
\end{cases}
$$
---

## Intuition
- Small errors → behave like **MSE**
- Large errors → behave like **MAE**
- Smooth transition between the two

---
## Visual Aid :
![[Huber loss.png]]
## Range
- $(0 \rightarrow \infty)$
- Lower is better

---

## Unit
- Same unit as target variable (after aggregation)

---

## Hyperparameter
### $( \delta)$(threshold)
- Controls sensitivity to outliers
- Smaller δ → closer to MAE
- Larger δ → closer to MSE

---

## Strengths
- Robust to outliers
- Differentiable everywhere
- Stable optimization
- Balanced error penalization

---

## Limitations
- Requires tuning δ
- Less interpretable than MAE
- Not scale-invariant
- Rarely used for reporting

---

## Sensitive to Outliers?
- ⚠️ Moderately
- Linear penalty beyond threshold

---

## When to Use
- Regression with outliers
- Noisy real-world datasets
- When RMSE is too sensitive
- Gradient-based optimization

---

## When NOT to Use
- Pure interpretability use cases
- Business reporting
- When error distribution is well-behaved

---

## Business Interpretation
- Limited direct interpretation
- Used mainly for **training**, not reporting

---

## Example
Let δ = 10

| Error | Loss |
|-----|-----|
| 5 | \(0.5 × 25 = 12.5\) |
| 20 | \(10(20 − 5) = 150\) |

Large errors grow linearly instead of quadratically.

---

## Relationship to Other Metrics
- MAE → linear penalty
- MSE → quadratic penalty
- Huber → quadratic + linear
- RMSE → √MSE

---

## Common Interview Questions
- Why Huber loss instead of MSE?
- How does Huber handle outliers?
- What does δ control?
- Is Huber convex?

---

## Related Metrics
- [[Quantile Loss]]

---


## Key Takeaway
> Huber loss offers a practical compromise between MAE and MSE, providing robustness without sacrificing optimization stability.

---
