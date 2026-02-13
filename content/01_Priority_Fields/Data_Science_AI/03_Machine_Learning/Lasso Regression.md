---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: regression
model-family: linear-models
regularization: L1
status: evergreen
tags:
  - "#ML"
  - "#fundamentals"
  - "#regression"
---

# Lasso Regression

> Linear Regression with L1 regularization that enforces sparsity by driving some coefficients exactly to zero.

---

## 1. Core Idea

Lasso Regression extends Linear Regression by adding an **L1 penalty** to the loss function, encouraging sparse solutions where irrelevant features are removed.

🔗 Parent models:
- [[Linear Regression]]
- [[Polynomial Regression]]

---

## 2. Intuition

By penalizing the absolute values of coefficients, Lasso **forces less important features to drop out entirely**, simplifying the model.

---

## 3. Analogy

Imagine packing for a trip with **strict baggage limits**:
- You can’t take everything
- Only the most essential items survive

---

## 4. Mathematical Formulation

- Loss = squared error + L1 penalty
- Produces sparse coefficient vectors
- No closed-form solution in general

🔗 Concepts:
- [[L1 Regularization]]
- [[Regularized Loss Functions]]
- [[Coordinate Descent]]

---

## 5. Optimization Perspective

- Convex but non-differentiable at zero
- Typically solved using:
  - Coordinate descent
  - Proximal gradient methods

🔗 Links:
- [[Convex Optimization]]
- [[Subgradient Methods]]

---

## 6. Effect on Bias–Variance Tradeoff

- Increases bias more than Ridge
- Reduces variance strongly
- Improves interpretability through sparsity

🔗 See:
- [[Bias–Variance Tradeoff]]

---

## 7. Assumptions

Inherits Linear Regression assumptions, but:

- Assumes feature sparsity exists
- Unstable when features are highly correlated
- Arbitrarily selects one feature from correlated groups

🔗 Concepts:
- [[Multicollinearity]]

---

## 8. Hyperparameter: Regularization Strength (λ)

- Controls sparsity level
- Small λ → many features kept
- Large λ → aggressive feature elimination

🔗 Links:
- [[Hyperparameter Tuning — MOC]]
- [[Cross Validation]]

---

## 9. Feature Scaling Requirement

Lasso is **highly sensitive to feature scale**:

- Mandatory feature standardization
- Otherwise coefficient shrinkage is biased

🔗 Links:
- [[Feature Scaling]]
- [[Standardization]]

---

## 10. Evaluation Metrics

Same regression metrics as Linear models:

- MSE / RMSE
- MAE
- R² / Adjusted R²

🔗 See:
- [[Regression Metrics — MOC]]

---

## 11. Interpretability

- Produces sparse models
- Easy to explain selected features
- Often used for feature selection

🔗 Links:
- [[Model Interpretability]]
- [[Feature Selection]]

---

## 12. When Lasso Works Well

- High-dimensional datasets
- True sparsity in features
- Need for automatic feature selection

---

## 13. When It Fails

- Highly correlated predictors
- When all features contribute moderately
- Small datasets with unstable selection

---

## 14. Relationship to Other Models

- Complementary to Ridge
- Special case of Elastic Net
- Related to compressed sensing

🔗 Related:
- [[Ridge Regression]]
- [[Elastic Net]]

---

## 15. Position in the ML Landscape

- Sparse linear model
- Embedded feature selection method
- Bridge between statistics and ML
