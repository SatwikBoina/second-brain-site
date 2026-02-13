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
> Adjusted R² measures the proportion of variance explained by the model while penalizing unnecessary features.

---

## Formula
$$

\text{Adjusted } R^2 =
1 -
\left(
\frac{1 - R^2}{n - p - 1}
\right)
(n - 1)
 

Where:

- (n) = number of observations  
- (p) = number of predictors  
$$
---

## Intuition
- R² always increases when features are added
- Adjusted R² increases **only if a new feature truly improves the model**
- Penalizes model complexity

---

## Range
- $( -\infty \rightarrow 1 )$

---

## Unit
- Unitless

---

## Strengths
- Controls overfitting
- Fair comparison between models
- Useful for feature selection
- Better indicator than R² for linear regression

---

## Limitations
- Still variance-based
- Does not measure prediction accuracy
- Assumes linear relationships
- Not applicable to non-linear ML models

---

## Sensitive to Outliers?
- ✅ Yes
- Uses squared residuals

---

## When to Use
- Multiple linear regression
- Feature selection
- Econometric modeling
- Comparing nested models

---

## When NOT to Use
- Forecast accuracy evaluation
- Time series models
- Tree-based models
- Neural networks

---

## Business Interpretation
- Adjusted R² = 0.78

👉 After accounting for number of predictors,  
the model explains **78% of variance**.

---

## Relationship to Other Metrics
- R² ignores model complexity
- Adjusted R² penalizes complexity
- RMSE measures prediction error
- AIC / BIC are likelihood-based alternatives

---

## Key Takeaway
> Adjusted R² improves upon R² by rewarding only meaningful predictors and penalizing unnecessary complexity.

---
