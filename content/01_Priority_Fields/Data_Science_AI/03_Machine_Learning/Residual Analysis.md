---
type: concept
domain: machine-learning
category: model-diagnostics
status: evergreen
---

# Residual Analysis

> Residual analysis examines the errors of a model to diagnose assumption violations and model inadequacies.

---

# 1. One-Line Intuition

> If the model is correct, residuals should look like random noise.

---

# 2. What is a Residual?

For observation i:

\[
e_i = y_i - \hat{y}_i
\]

Residual = observed − predicted.

Residuals approximate true errors.

---

# 3. Why Residuals Matter

Residuals reveal:

- Whether model assumptions hold.
- Whether important structure is missing.
- Whether variance is constant.
- Whether errors are independent.

---

# 4. Key Residual Plots

---

## 4.1 Residuals vs Fitted Values

Purpose:
- Check linearity.
- Check homoscedasticity.

Ideal:
- Random scatter.
- No pattern.

Bad signs:
- Curve → Nonlinearity.
- Funnel shape → Heteroscedasticity.

🔗 Related:
- [[Linearity Assumption]]
- [[Homoscedasticity]]

---

## 4.2 Residuals vs Time (Order)

Purpose:
- Check independence.

Ideal:
- No pattern over time.

Bad signs:
- Cycles.
- Trends.
- Autocorrelation.

🔗 Related:
- [[Independence of Errors]]

---

## 4.3 Q–Q Plot

Purpose:
- Check normality of residuals.

Ideal:
- Points lie on straight line.

Bad signs:
- Heavy tails.
- Skewness.

🔗 Related:
- [[Normality of Errors]]

---

# 5. Standardized Residuals

Standardized residual:

\[
r_i = \frac{e_i}{\hat{\sigma}}
\]

Used to detect:

- Outliers.
- Extreme deviations.

Rule of thumb:
- |r_i| > 2 or 3 → possible outlier.

---

# 6. Leverage

Leverage measures:

- How far a point's feature values are from mean of X.

High leverage:
- Can strongly influence model.

Computed from hat matrix:

\[
H = X(X^T X)^{-1}X^T
\]

Diagonal elements \(h_{ii}\) measure leverage.

---

# 7. Cook’s Distance

Measures influence of observation:

\[
D_i = \frac{e_i^2}{p \cdot MSE} \frac{h_{ii}}{(1 - h_{ii})^2}
\]

Large Cook’s distance:
- Influential observation.
- Removing it changes model significantly.

---

# 8. What Residual Patterns Mean

---

## Curved Pattern

→ Nonlinear relationship.  
Solution:
- Add polynomial terms.
- Transform features.

🔗 Related:
- [[Polynomial Regression]]

---

## Funnel Shape

→ Heteroscedasticity.  
Solution:
- Log transform target.
- Weighted least squares.

---

## Clusters

→ Missing categorical variable.

---

## Cycles

→ Time dependence.
- Consider time-series model.

---

# 9. Residual Analysis and Bias–Variance

Systematic patterns:

- Indicate bias (underfitting).

Random noise with large spread:

- High variance.

Residual analysis helps identify bias/variance issues.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

# 10. Residuals in ML vs Statistics

In classical statistics:

- Crucial for inference validity.

In ML:

- Often ignored if only prediction matters.
- Still useful for debugging model quality.

---

# 11. Limitations

- Visual interpretation subjective.
- Hard in high-dimensional models.
- Less meaningful for tree ensembles or deep nets.

For complex models:
- Use SHAP.
- Use PDP.
- Use permutation importance.

🔗 Related:
- [[SHAP Values]]
- [[Partial Dependence Plots]]

---

# 12. When Residual Analysis Is Most Important

- Linear regression
- Logistic regression
- Small datasets
- Research studies
- Causal modeling

---

# 13. Relationship to Other Concepts

Residual Analysis connects strongly to:

- [[Linear Regression]]
- [[Linearity Assumption]]
- [[Homoscedasticity]]
- [[Independence of Errors]]
- [[Normality of Errors]]
- [[Bias–Variance Tradeoff]]
- [[Outliers]]
- [[Multicollinearity]]

---

# 14. Why Residual Analysis Matters

Residual analysis teaches:

- How to validate modeling assumptions.
- How to detect model misspecification.
- How to identify influential observations.
- How theory connects to real data.

It is the practical diagnostic tool for:
> Regression modeling.
