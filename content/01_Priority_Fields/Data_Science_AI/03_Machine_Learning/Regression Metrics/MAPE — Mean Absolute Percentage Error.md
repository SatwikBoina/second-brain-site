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

> Measures the average absolute prediction error expressed as a percentage of the actual value.

---
## Formula

$$

MAPE = \frac{1}{n}\sum_{i=1}^{n}

\left|

\frac{y_i - \hat{y}_i}{y_i}

\right| \times 100

$$


---
## Visual Aid :
![[MAPE.png]]

## Intuition

- Calculates **how wrong the prediction is in percentage terms**

- Treats every error **relative to actual demand**

- Scale-independent metric

  

Example:  

If actual sales = 100 and prediction = 90  
→ error = **10%**


## Range

- $(0 \rightarrow \infty)$
- Lower is better
  

---
## Unit

- Percentage (%)

---

## Strengths

- Easy to understand for business users

- Scale-independent

- Allows comparison across products or regions

- Widely used in forecasting

---

## Limitations

- Undefined when actual value = 0

- Explodes for very small actual values

- Biased toward low-volume SKUs

- Penalizes under-forecasting more than over-forecasting

---

## Sensitive to Outliers?

- **Yes**

- Small actual values can create extremely large percentage errors

---

## When to Use

- Demand forecasting

- Sales prediction

- High-volume stable SKUs

- Business reporting dashboards

---

## When NOT to Use

- When actual values can be zero

- Sparse or intermittent demand

- Long-tail SKU forecasting

- Highly volatile sales series


---

## Business Interpretation

- MAPE = 12%

👉 On average, predictions deviate by **12% from actual sales**.


## Related Metrics

- [[WMAPE — Weighted Mean Absolute Percentage Error]]
- [[sMAPE]]

## Key Takeaway

> MAPE is intuitive but statistically flawed.  

> It should be used for **reporting**, not **model optimization**.

  

---