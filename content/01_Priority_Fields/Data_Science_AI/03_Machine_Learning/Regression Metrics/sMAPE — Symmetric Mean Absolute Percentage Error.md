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
> Measures prediction error as a percentage while reducing the asymmetry problem of MAPE.

---

## Formula
Most commonly used form:

$$
sMAPE =
\frac{1}{n}\sum_{i=1}^{n}
\frac{|y_i - \hat{y}_i|}
{\frac{|y_i| + |\hat{y}_i|}{2}}
\times 100
$$

---

## Intuition
- Uses **average of actual and prediction** in the denominator
- Prevents error explosion when actual values are small
- Treats over- and under-prediction more symmetrically than MAPE

---
## Visual Aid 

## Range
- $(0 \rightarrow 200\% )$
- Lower is better

---

## Unit
- Percentage (%)

---

## Strengths
- More symmetric than MAPE
- Bounded metric
- Handles small actual values better
- Scale-independent

---

## Limitations
- Still unstable near zero
- Multiple formula variants exist
- Less intuitive than MAPE
- Not perfectly symmetric mathematically

---

## Sensitive to Outliers?
- ⚠️ Moderate sensitivity
- Large relative deviations still increase error

---

## When to Use
- Forecast accuracy comparison
- Time-series competitions
- When relative error matters
- When MAPE is unstable

---

## When NOT to Use
- When business interpretability is critical
- When hierarchy-level weighting is required
- When zero values dominate the data

---

## Business Interpretation
- sMAPE = 15%

👉 Average relative forecast error is **15%**, accounting for both actual and predicted scale.

---

## Relationship to Other Metrics
- MAPE → uses actual only
- sMAPE → uses actual and prediction
- WMAPE → weighted MAE
- MAE → absolute error

---
## Related Metrics
- [[MAPE — Mean Absolute Percentage Error]]

---

## Key Takeaway
> sMAPE reduces MAPE’s asymmetry by normalizing error using both actual and predicted values, but it still struggles near zero.

---
