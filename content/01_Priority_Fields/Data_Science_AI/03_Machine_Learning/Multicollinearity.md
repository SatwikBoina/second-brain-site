---
type: concept
domain: machine-learning
category: modeling-assumptions
status: evergreen
---

# Homoscedasticity

> Homoscedasticity means that the variance of the error terms is constant across all levels of the independent variables.

---

## 1. One-Line Intuition

> The spread of residuals should stay roughly the same across all predicted values.

---

## 2. Mathematical Formulation

For regression model:

\[
y_i = w^T x_i + \epsilon_i
\]

Homoscedasticity requires:

\[
Var(\epsilon_i | x_i) = \sigma^2
\]

for all i.

Variance is constant — does not depend on x.

---

## 3. What It Means Practically

If we plot:

- Residuals vs predicted values

We should see:

- Random scatter
- No funnel shape
- No increasing/decreasing spread

---

## 4. Heteroscedasticity (Violation)

If variance changes with x:

\[
Var(\epsilon_i | x_i) \neq \text{constant}
\]

Example patterns:

- Funnel shape
- Increasing variance for large predictions
- Volatility clustering

---

## 5. Visual Diagnosis

Residual plot:

Good case:
- Uniform spread.

Bad case:
- Cone or fan shape.
- Spread increasing with prediction.

---

## 6. Why Homoscedasticity Matters

If violated:

- Coefficient estimates remain unbiased.
- But standard errors are wrong.
- Confidence intervals unreliable.
- Hypothesis tests invalid.

Prediction may still work fine.

---

## 7. Where It Commonly Fails

---

### 7.1 Income vs Spending

High-income individuals:
- Higher variability in spending.

---

### 7.2 Financial Data

Stock returns:
- Volatility changes over time.

---

### 7.3 Count Data

Variance increases with mean.

---

## 8. Detecting Heteroscedasticity

---

### 8.1 Residual Plots

Plot residuals vs fitted values.

---

### 8.2 Breusch–Pagan Test

Statistical test for non-constant variance.

---

### 8.3 White’s Test

More general heteroscedasticity test.

---

## 9. Handling Heteroscedasticity

---

### 9.1 Transform Target Variable

Common transformations:

- Log transform
- Square root transform

---

### 9.2 Weighted Least Squares

Give less weight to high-variance observations.

---

### 9.3 Robust Standard Errors

Adjust standard errors without changing coefficients.

---

### 9.4 Use Generalized Linear Models (GLMs)

When variance structure depends on mean.

---

## 10. Homoscedasticity vs Independence

Independence:
- Errors uncorrelated across observations.

Homoscedasticity:
- Errors have constant variance.

Different assumptions.

🔗 Related:
- [[Independence of Errors]]

---

## 11. Homoscedasticity and Bias–Variance

Non-constant variance:

- Makes model less reliable.
- Increases uncertainty in some regions.
- Leads to unstable inference.

---

## 12. ML vs Classical Statistics

In ML:

- Homoscedasticity often ignored.
- Focus is on prediction, not inference.

In statistics:

- Crucial for valid confidence intervals.

---

## 13. Geometric Interpretation

If homoscedastic:

- Data points equally dispersed around regression line.

If heteroscedastic:

- Dispersion changes with x.

The model assumes uniform noise structure.

---

## 14. When Homoscedasticity Holds

- Controlled experiments
- Randomized trials
- Simple cross-sectional datasets

---

## 15. When It Rarely Holds

- Economic data
- Financial markets
- Growth processes
- Real-world behavioral data

---

## 16. Relationship to Other Concepts

Homoscedasticity connects strongly to:

- [[Linear Regression]]
- [[Independence of Errors]]
- [[Linearity Assumption]]
- [[Maximum Likelihood Estimation]]
- [[Time Series MOC]]
- [[Bias–Variance Tradeoff]]

---

## 17. Why Homoscedasticity Matters

Homoscedasticity teaches:

- The difference between prediction and inference.
- Why residual diagnostics matter.
- How variance structure affects uncertainty.
- Why classical regression assumptions exist.

It is one of the pillars of:
> Classical linear regression theory.
