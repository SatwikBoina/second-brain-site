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

> Measures total absolute error as a percentage of total actual demand.

---

## Formula

$$

WMAPE = 

\frac{\sum |y_i - \hat{y}_i|}

{\sum y_i}

\times 100

$$

---
## Visual Aid :
![[WMAPE.png]]

![[wmape vs mape.png]]

## Intuition

- Aggregates absolute error across all observations

- Weights error by actual demand

- High-volume SKUs influence metric more

  

---

## Range

- 0 → ∞

- Lower is better

---

## Unit

- Percentage (%)

---
## Strengths

- Handles zero actual values

- Robust to low-volume noise

- Business-aligned metric

- Stable across SKU hierarchies

---
## Limitations

- Still asymmetric

- Does not penalize large individual errors

- Can hide poor performance on small SKUs

---

## Sensitive to Outliers?

- Moderately

- Large-volume SKUs dominate metric

---

## When to Use

- FMCG demand forecasting

- Sales prediction

- Promotion modeling

- Supply chain accuracy reporting

  

---

  

## When NOT to Use

- When fairness across SKUs matters

- When tail SKUs are critical

- When distribution-level accuracy is required

---

## Business Interpretation

- WMAPE = 8%

👉 Model’s total forecast error equals **8% of total demand**.

---

## Key Takeaway

> WMAPE reflects **business impact**, not statistical purity.

  

---