---
type: zettel
domain: machine-learning
category: linear-models
topic: ordinary-least-squares
status: evergreen
---

# Ordinary Least Squares (OLS)

> Ordinary Least Squares (OLS) estimates regression coefficients by minimizing the sum of squared residuals.

---

## 1. Model Setup

We assume a linear model:

$$
y = X\beta + \epsilon
$$

Where:

- \(y\) = target vector (n × 1)
- \(X\) = design matrix (n × p)
- \(\beta\) = coefficient vector (p × 1)
- \(\epsilon\) = error vector

---

## 2. Objective Function

OLS solves:

$$
\min_{\beta} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
$$

Matrix form:

$$
\min_{\beta} ||y - X\beta||^2
$$

This is the squared error loss.

🔗 Related:
- [[Squared Error Loss]]

---

## 3. Closed-Form Solution (Normal Equation)

Set gradient to zero:

$$
X^T X \hat{\beta} = X^T y
$$

Solution:

$$
\hat{\beta} = (X^T X)^{-1} X^T y
$$

Requires:

- No perfect multicollinearity.
- \(X^T X\) invertible.

🔗 Related:
- [[Normal Equation (Closed-Form Optimization)]]
- [[Multicollinearity]]

---

## 4. Geometric Interpretation

OLS finds:

> The orthogonal projection of y onto the column space of X.

Residual vector:


$$
e = y - X\hat{\beta}
$$

is orthogonal to X:

\[
X^T e = 0
\]

---

## 5. Statistical Properties

Under Gauss–Markov assumptions:

- OLS is unbiased:
  $$
  E[\hat{\beta}] = \beta
  $$
- OLS is BLUE:
  Minimum variance among linear unbiased estimators.

🔗 Related:
- [[Gauss–Markov Assumptions]]

---

## 6. Variance of OLS Estimator

If:

$$
Var(\epsilon) = \sigma^2 I
$$

Then:

$$
Var(\hat{\beta}) = \sigma^2 (X^T X)^{-1}
$$

Multicollinearity inflates variance.

---

## 7. OLS and Maximum Likelihood

If errors are Gaussian:

$$
\epsilon \sim \mathcal{N}(0, \sigma^2)
$$

Then:

- OLS = Maximum Likelihood Estimator (MLE).

Without normality:
- OLS still BLUE, but not necessarily MLE.

🔗 Related:
- [[Maximum Likelihood Estimation]]

---

## 8. Assumptions Required

OLS relies on:

1. Linearity in parameters
2. Independence of errors
3. Homoscedasticity
4. No perfect multicollinearity
5. Zero conditional mean

🔗 Related:
- [[Linearity Assumption]]
- [[Independence of Errors]]
- [[Homoscedasticity]]
- [[Multicollinearity]]

---

## 9. Bias–Variance Perspective

OLS:

- Low bias (if model correctly specified)
- Potentially high variance (if many predictors)

Regularization trades bias for lower variance.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Ridge Regression]]

---

## 10. Limitations

- Sensitive to outliers.
- Assumes linear structure.
- Assumes constant variance.
- Coefficients unstable under multicollinearity.

---

## 11. OLS vs Regularized Regression

| Model | Objective |
|--------|----------|
| OLS | Minimize squared error |
| Ridge | Squared error + L2 penalty |
| Lasso | Squared error + L1 penalty |

OLS is unregularized baseline.

---

## 12. Why OLS Matters

OLS teaches:

- Linear algebra foundation of regression.
- Projection geometry.
- Variance minimization.
- Connection between optimization and statistics.

It is the backbone of:
> Classical linear regression theory.
