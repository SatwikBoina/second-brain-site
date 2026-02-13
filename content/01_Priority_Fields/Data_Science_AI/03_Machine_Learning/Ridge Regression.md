---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: regression
model-family: linear-models
regularization: L2
status: evergreen
tags:
  - "#ML"
  - "#regression"
  - "#fundamentals"
---

# Ridge Regression

> Linear Regression with L2 regularization that penalizes large coefficients to reduce variance and improve generalization.

---

## 1. Core Idea

Ridge Regression modifies Linear Regression by **adding a penalty on the squared magnitude of coefficients**, discouraging overly complex models.

🔗 Parent models:
- [[Linear Regression]]
- [[Polynomial Regression]]

---

## 2. Intuition

Instead of allowing the model to fit the data perfectly, Ridge Regression **pulls coefficients toward zero**, trading a small increase in bias for a large reduction in variance.

---

## 3. Analogy

Think of coefficients connected by **rubber bands**:
- They can move to fit the data
- But stretching too far becomes costly

---

## 4. Mathematical Formulation

- Loss = squared error + L2 penalty
- Penalizes large weights uniformly
- Closed-form solution exists

🔗 Concepts:
- [[L2 Regularization]]
- [[Regularized Loss Functions]]
- [[Normal Equation]]

---

## 5. Optimization Perspective

Ridge Regression remains a **convex optimization problem**:

- Unique global minimum
- Solvable via:
  - Closed-form
  - Gradient-based methods

🔗 Links:
- [[Convex Optimization]]
- [[Gradient Descent]]

---

## 6. Effect on Bias–Variance Tradeoff

- Increases bias slightly
- Significantly reduces variance
- Improves stability with correlated features

🔗 See:
- [[Bias–Variance Tradeoff]]
- [[Multicollinearity]]

---

## 7. Assumptions

Inherits Linear Regression assumptions, but:

- More robust to multicollinearity
- Does NOT perform feature selection
- Assumes all features contribute somewhat

🔗 Concepts:
- [[Gauss–Markov Assumptions]]

---

## 8. Hyperparameter: Regularization Strength (λ)

- Controls penalty strength
- λ = 0 → Linear Regression
- Large λ → coefficients shrink toward zero

🔗 See:
- [[Hyperparameter Tuning — MOC]]
- [[Cross Validation]]

---

## 9. Feature Scaling Requirement

Ridge Regression is **scale-sensitive**:

- Features must be standardized
- Otherwise penalty is uneven

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

- Coefficients remain non-zero
- Relative importance preserved
- Less sparse, more stable than Lasso

🔗 Links:
- [[Model Interpretability]]

---

## 12. When Ridge Regression Works Well

- Many correlated features
- High-dimensional but low-noise data
- When all features are believed to matter

---

## 13. When It Fails

- When true feature sparsity exists
- When feature selection is needed
- Highly non-linear relationships

---

## 14. Relationship to Other Models

- L2-regularized Linear Regression
- Complements Lasso
- Component of Elastic Net

🔗 Related:
- [[Lasso Regression]]
- [[Elastic Net]]

---

## 15. Position in the ML Landscape

- Core regularized linear model
- Benchmark for high-dimensional regression
- Foundation for modern ML regularization
