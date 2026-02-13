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
> Measures the proportion of variance in the target variable explained by the regression model.

---

## Formula

$$
R^2 =
1 -
\frac{SS_{res}}{SS_{tot}}


Where:


SS_{res} = \sum (y_i - \hat{y}_i)^2

SS_{tot} = \sum (y_i - \bar{y})^2

$$

---

## Intuition
- Compares model error with a **naive baseline model**
- Baseline model always predicts the **mean**
- R² tells how much better the model is than predicting the mean

---

## Range
- $( -\infty \rightarrow 1)$

### Interpretation:
- **1** → perfect model  
- **0** → same as predicting mean  
- **< 0** → worse than mean prediction  

---

## Unit
- Unitless (percentage of variance)

---

## Strengths
- Easy to interpret
- Scale-independent
- Useful for linear models
- Explains variance captured

---

## Limitations
- Does not measure prediction accuracy
- Sensitive to outliers
- Always increases when features are added
- Misleading for non-linear models
- Not suitable for model comparison alone

---

## Sensitive to Outliers?
- ✅ Yes
- Uses squared errors internally

---

## When to Use
- Linear regression diagnostics
- Explaining model performance
- Statistical reporting
- Comparing against baseline model

---

## When NOT to Use
- Forecast accuracy evaluation
- Time series forecasting
- Comparing models with different targets
- Non-linear ML models

---

## Business Interpretation
- R² = 0.82

👉 Model explains **82% of variability** in the target variable.


---

## Relationship to Other Metrics
- R² is variance-based
- RMSE / MAE are error-based
- Adjusted R² penalizes feature count
- High R² ≠ good predictions

---

## Related Metrics
- [[Adjusted R-squared]]
---

## Key Takeaway
> R² explains variance captured by the model — not how accurate the predictions are.

