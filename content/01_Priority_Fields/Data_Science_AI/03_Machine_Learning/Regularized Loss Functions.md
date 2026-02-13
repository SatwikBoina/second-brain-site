---
type: concept
domain: machine-learning
category: optimization
status: evergreen
---

# Regularized Loss Functions

> A regularized loss function combines prediction error with a penalty on model complexity.

---

# 1. One-Line Intuition

> Fit the data well — but don’t let the model become too complex.

---

# 2. General Form

$$
\text{Objective} = \text{Loss} + \lambda \times \text{Regularization Term}
$$
Where:

- Loss → measures prediction error
- Regularization → penalizes complexity
- $ \lambda$ → controls tradeoff

---

# 3. Why Regularization Is Needed

Without regularization:

- Model may overfit.
- High variance.
- Poor generalization.

Regularization:

- Controls model capacity.
- Reduces variance.
- Improves stability.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Overfitting vs Underfitting]]

---

# 4. L2 Regularization (Ridge)

$$
\min \sum (y - \hat{y})^2 + \lambda ||w||^2
$$
Penalty:

$$
||w||^2 = \sum w_j^2
$$

Effect:

- Shrinks coefficients.
- Keeps all features.
- Reduces variance.

🔗 Related:
- [[Ridge Regression]]

---

# 5. L1 Regularization (Lasso)

$$
\min \sum (y - \hat{y})^2 + \lambda ||w||_1
$$
Penalty:

$$
||w||_1 = \sum |w_j|
$$

Effect:

- Shrinks some coefficients to zero.
- Performs feature selection.

🔗 Related:
- [[Lasso Regression]]

---

# 6. Elastic Net

$$
\min \sum (y - \hat{y})^2 + \lambda_1 ||w||_1 + \lambda_2 ||w||^2
$$

Combines:

- L1 sparsity
- L2 stability

🔗 Related:
- [[Elastic Net]]

---

# 7. Regularization in Classification

---

## Logistic Regression

$$
\min \text{CrossEntropy} + \lambda ||w||^2
$$
---

## SVM

$$
\min \frac{1}{2}||w||^2 + C \sum \text{Hinge Loss}
$$

Here:

- \(C = 1/\lambda\)
- Regularization controls margin softness.

🔗 Related:
- [[Hinge Loss]]
- [[Cross Entropy]]

---

# 8. Regularization in Neural Networks

Common types:

- L2 weight decay
- Dropout
- Early stopping
- Batch normalization (implicit effect)

All reduce overfitting.

---

# 9. Geometric Interpretation

Without regularization:

- Solution may lie anywhere minimizing loss.

With L2:
- Solution constrained inside sphere.

With L1:
- Solution constrained inside diamond.
- Corners promote sparsity.

---

# 10. Bias–Variance Perspective

Increasing λ:

- Increases bias
- Decreases variance

Small λ:
- Low bias
- High variance

Large λ:
- High bias
- Low variance

🔗 Related:
- [[Model Complexity]]

---

# 11. Regularization and Optimization

Regularized objective:

\[
\min_w L(w) + \lambda R(w)
\]

Gradient becomes:

\[
\nabla L(w) + \lambda \nabla R(w)
\]

Regularization changes gradient direction.

---

# 12. Regularization and Bayesian View

L2 regularization:

- Equivalent to Gaussian prior on weights.

L1 regularization:

- Equivalent to Laplace prior.

Thus:

Regularization = Prior belief about parameters.

---

# 13. Structural Risk Minimization

Regularization implements:

\[
\text{Empirical Risk} + \text{Model Complexity Penalty}
\]

Core idea of:

- Structural Risk Minimization

🔗 Related:
- [[Structural Risk Minimization]]

---

# 14. When Regularization Is Crucial

- High-dimensional data
- Small datasets
- Correlated features
- Complex models

---

# 15. When Less Important

- Large datasets
- Simple models
- Strong signal-to-noise ratio

---

# 16. Relationship to Other Concepts

Regularized Loss connects strongly to:

- [[Ridge Regression]]
- [[Lasso Regression]]
- [[Elastic Net]]
- [[Support Vector Machine]]
- [[Cross Entropy]]
- [[Squared Error Loss]]
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]
- [[Overfitting vs Underfitting]]

---

# 17. Why Regularized Loss Functions Matter

They teach:

- How to control complexity formally.
- Why shrinkage stabilizes models.
- How bias–variance tradeoff is operationalized.
- Why overfitting is mathematically preventable.

They are the backbone of:
> Modern machine learning optimization.
