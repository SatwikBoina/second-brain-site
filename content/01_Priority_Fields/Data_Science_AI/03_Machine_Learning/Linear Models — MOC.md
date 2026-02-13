# 📌 MOC — Linear Models

> Central hub for all **linear-in-parameters** models used in supervised learning.
> These models assume the target is a linear combination of learned coefficients.

---

## 1. Core Idea

Linear models learn a function of the form:

> prediction = weighted sum of features (+ noise)

Linearity refers to **linearity in parameters**, not necessarily in input features.

---

## 2. Linear Regression Family

These models minimize squared error and differ mainly by **feature transformation** and **regularization**.

- [[Linear Regression]]
- [[Polynomial Regression]]
- [[Ridge Regression]]
- [[Lasso Regression]]
- [[Elastic Net]]
- [[Log-Log Regression ]]

---

## 3. Problem Types Covered

- [[Regression — MOC]]
- [[Classification — MOC]] (via Logistic Regression and extensions)

---

## 4. Shared Assumptions

Most linear models rely on:

- [[Linearity Assumption]]
- [[Independence of Errors]]
- [[Homoscedasticity]]
- [[Multicollinearity]]
- [[Gauss–Markov Assumptions]]

---

## 5. Shared Loss Functions

- [[Squared Error Loss]]
- [[Regularized Loss Functions]]

---

## 6. Optimization Methods

- [[Normal Equation]]
- [[Gradient Descent]]
- [[Coordinate Descent]]
- [[Convex Optimization]]

---

## 7. Bias–Variance Perspective

- Simple linear models → higher bias, lower variance
- Regularization increases bias but reduces variance
- Polynomial features increase variance

🔗 See:
- [[Bias–Variance Tradeoff]]

---

## 8. Feature Engineering for Linear Models

Linear models are highly sensitive to feature design:

- [[Feature Scaling]]
- [[Standardization]]
- [[Feature Interaction]]
- [[Polynomial Features]]
- [[Outliers]]

---

## 9. Evaluation Metrics

- [[Regression Metrics — MOC]]
- [[Classification Metrics — MOC]]

---

## 10. Interpretability & Diagnostics

- [[Coefficient Interpretation in Linear Models]]
- [[Statistical Significance]]
- [[Residual Analysis]]
- [[Model Interpretability]]

---

## 11. When to Use Linear Models

- Strong baseline model
- High interpretability requirement
- Limited data
- High-dimensional sparse data (with regularization)

---

## 12. Limitations

- Poor at capturing complex non-linear patterns
- Sensitive to outliers
- Require careful feature engineering

---

## 13. Extensions & Related Models

- [[Generalized Linear Models]]
- [[Support Vector Machines]]
- [[Kernel Methods]]
- [[Neural Network Regressor]]

---

## Usage Rules

- This note contains **no algorithm derivations**
- Algorithm notes must link here
- Shared concepts must live in separate atomic notes
- Extend by linking, not by adding explanations
