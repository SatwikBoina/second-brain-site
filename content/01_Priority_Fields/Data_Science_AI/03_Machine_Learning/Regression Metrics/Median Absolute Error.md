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

> Measures the typical prediction error by taking the median of absolute errors, making it highly robust to outliers.


---
## Formula

$$

\text{MedianAE} = \text{median}(|y_i - \hat{y}_i|)

$$
---
## Intuition

- Compute absolute error for each observation

- Take the **median instead of the mean**

- Represents the “middle” prediction error

---
## Range

- $(0 \rightarrow \infty)$
- Lower is better

---
## Unit

- Same unit as target variable  

  (e.g., units sold, revenue, demand)

---
## Strengths

- Extremely robust to outliers

- Not influenced by extreme prediction errors

- Represents typical model behavior

- Stable under noisy data

---
## Limitations

- Ignores magnitude of large errors

- Not smooth or differentiable

- Not sensitive to tail risk

- Less common in business reporting

---
## Sensitive to Outliers?

- ❌ No

- Outliers have minimal impact

---
## When to Use

- Data with heavy-tailed noise

- Presence of extreme outliers

- Intermittent demand

- Sensor data

- Early model benchmarking

---
## When NOT to Use

- When large errors are costly

- When tail performance matters

- When business cares about worst-case scenarios

---
## Business Interpretation

- Median AE = 50
👉 Half of predictions have an error **≤ 50 units**.

---
## Related Metrics
- [[MAE - Mean Absolute Error]]
---
## Key Takeaway
> Median Absolute Error reflects the typical prediction error while completely ignoring extreme mistakes.

---
