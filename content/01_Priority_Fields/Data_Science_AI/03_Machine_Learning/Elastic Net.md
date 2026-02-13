---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: regression
model-family: linear-models
regularization: L1 + L2
status: evergreen
tags:
  - "#ML"
  - "#regression"
  - "#fundamentals"
---

# Elastic Net Regression

> Linear Regression with combined L1 and L2 regularization, balancing sparsity and stability in high-dimensional data.

---

## 1. Core Idea

Elastic Net combines **L1 (Lasso)** and **L2 (Ridge)** penalties to overcome their individual limitations:
- Lasso’s instability with correlated features
- Ridge’s lack of feature selection

🔗 Parent models:
- [[Linear Regression]]
- [[Ridge Regression]]
- [[Lasso Regression]]

---

## 2. Intuition

Elastic Net allows the model to:
- **Select features** (L1 effect)
- **Share weight among correlated features** (L2 effect)

This produces sparse but stable solutions.

---

## 3. Analogy

Think of Elastic Net as a **team selection process**:
- Lasso fires weak players
- Ridge keeps everyone but limits ego
- Elastic Net keeps strong *groups* and removes noise

---

## 4. Mathematical Formulation

- Loss = squared error + L1 penalty + L2 penalty
- Controlled by two hyperparameters

🔗 Concepts:
- [[L1 Regularization]]
- [[L2 Regularization]]
- [[Regularized Loss Functions]]

---

## 5. Hyperparameters

Elastic Net introduces two key controls:

- **α (alpha)** → overall regularization strength  
- **l1_ratio** → balance between L1 and L2

Special cases:
- l1_ratio = 1 → Lasso
- l1_ratio = 0 → Ridge

🔗 See:
- [[Hyperparameter Tuning — MOC]]
- [[Cross Validation]]

---

## 6. Optimization Perspective

- Convex optimization problem
- Solved efficiently via:
  - Coordinate descent
  - Proximal gradient methods

🔗 Links:
- [[Convex Optimization]]
- [[Coordinate Descent]]

---

## 7. Effect on Bias–Variance Tradeoff

- Higher bias than Linear Regression
- Lower variance than both Ridge and Lasso
- Best tradeoff in correlated feature spaces

🔗 See:
- [[Bias–Variance Tradeoff]]
- [[Multicollinearity]]

---

## 8. Assumptions

Inherits Linear Regression assumptions, but:

- Assumes grouped feature relevance
- More robust than Lasso under correlation
- Less aggressive than pure sparsity

🔗 Concepts:
- [[Gauss–Markov Assumptions]]

---

## 9. Feature Scaling Requirement

Elastic Net is **scale-sensitive**:

- Mandatory feature standardization
- Ensures balanced regularization

🔗 Links:
- [[Feature Scaling]]
- [[Standardization]]

---

## 10. Evaluation Metrics

Same as standard regression models:

- MSE / RMSE
- MAE
- R² / Adjusted R²

🔗 See:
- [[Regression Metrics — MOC]]

---

## 11. Interpretability

- Sparse but not overly aggressive
- Better stability across folds
- Coefficients easier to trust than Lasso

🔗 Links:
- [[Model Interpretability]]

---

## 12. When Elastic Net Works Well

- High-dimensional data
- Correlated predictors
- Need for both selection and stability

---

## 13. When It Fails

- Very small datasets
- Strong non-linear relationships
- When feature engineering is poor

---

## 14. Relationship to Other Models

- Generalization of Ridge and Lasso
- Default choice for linear regularized regression
- Common in genomics, NLP, and finance

🔗 Related:
- [[Ridge Regression]]
- [[Lasso Regression]]
- [[Polynomial Regression]]

---

## 15. Position in the ML Landscape

- Most robust linear regularization model
- Practical default in high-dimensional regression
- Bridge to modern ML pipelines
