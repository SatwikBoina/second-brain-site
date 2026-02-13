---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: regression
model-family: linear-models
status: evergreen
tags:
  - "#regression"
  - "#ML"
  - "#fundamentals"
---
---

# Polynomial Regression

> Extends Linear Regression by modeling non-linear relationships using polynomial feature transformations.

---

## 1. Core Idea

Polynomial Regression is **linear in parameters but non-linear in features**.  
The model remains a linear regression after transforming inputs into polynomial terms.

🔗 Parent model:
- [[Linear Regression]]

---

## 2. Intuition

When a straight line is too simple, polynomial features allow the model to **bend** and fit curved patterns while still using a linear learning framework.

---

## 3. Analogy

Imagine fitting a **flexible metal strip** instead of a rigid ruler:
- Degree 1 → rigid
- Higher degree → more bends
- Too many bends → overfitting

---

## 4. Mathematical Perspective

- Input features are expanded into polynomial terms  
- The hypothesis remains a linear combination of transformed features  

🔗 Concepts:
- [[Feature Engineering]]
- [[Design Matrix]]
- [[Vandermonde Matrix]]

---

## 5. Model Complexity & Degree Selection

- Degree controls model flexibility
- Higher degree → lower bias, higher variance
- Degree selection is a **model selection problem**

🔗 Links:
- [[Bias–Variance Tradeoff]]
- [[Learning Curves]]
- [[Cross Validation]]

---

## 6. Assumptions

Inherits most assumptions from Linear Regression, but:

- Linearity applies **after feature transformation**
- Strongly sensitive to outliers
- Multicollinearity increases rapidly with degree

🔗 See:
- [[Gauss–Markov Assumptions]]
- [[Multicollinearity]]

---

## 7. Overfitting Risks

Polynomial Regression is especially prone to:

- High variance
- Poor extrapolation
- Numerical instability

🔗 Concepts:
- [[Overfitting vs Underfitting]]
- [[Regularization — MOC]]

---

## 8. Evaluation Metrics

Uses standard regression metrics:

- MSE / RMSE
- MAE
- R² / Adjusted R²

🔗 See:
- [[Regression Metrics — MOC]]

---

## 9. Feature Scaling & Preprocessing

Polynomial terms magnify feature magnitudes:

- Feature scaling is critical
- Centering improves numerical stability

🔗 Links:
- [[Feature Scaling]]
- [[Numerical Stability]]

---

## 10. Hyperparameters

Key tunable parameters:

- Polynomial degree
- Interaction terms inclusion
- Regularization strength (when combined)

🔗 See:
- [[Ridge Regression]]
- [[Lasso Regression]]

---

## 11. Interpretability

- Coefficients lose direct interpretability
- Still explainable with feature plots
- Partial dependence can help

🔗 Links:
- [[Model Interpretability]]
- [[Partial Dependence Plots]]

---

## 12. When Polynomial Regression Works Well

- Smooth non-linear relationships
- Low-dimensional feature space
- Controlled degree with validation

---

## 13. When It Fails

- High-dimensional data
- Noisy data
- Extrapolation beyond training range

---

## 14. Relationship to Other Models

- Special case of Linear Regression
- Basis function expansion
- Bridge to kernel methods

🔗 Related:
- [[Spline Regression]]
- [[Support Vector Regression]]
- [[Kernel Trick]]

---

## 15. Position in the ML Landscape

- Non-linear modeling via feature engineering
- Demonstrates bias–variance tradeoff clearly
- Educationally important baseline
