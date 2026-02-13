---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: regression
model-family: kernel-methods
status: evergreen
---

# Support Vector Regression (SVR)

> A kernel-based regression algorithm that fits a function within a specified error margin while maximizing model flatness.

---

## 1. Core Idea

Support Vector Regression extends Support Vector Machines to regression by:

- Allowing a margin of error (ε) around predictions
- Penalizing predictions only when errors exceed this margin
- Maximizing model flatness instead of minimizing squared error

🔗 Model family:
- [[Kernel Methods — MOC]]

---

## 2. Intuition

SVR tries to fit a function such that:
- Most data points lie **inside a tolerance tube**
- Only points outside the tube influence the model
- The model remains as simple (flat) as possible

---

## 3. Analogy

Imagine fitting a **road** through a city:
- The road has a fixed width (ε)
- Buildings inside the road don’t matter
- Only buildings sticking out force the road to bend

---

## 4. Mathematical Perspective

SVR solves an optimization problem that:

- Minimizes model complexity (‖w‖²)
- Allows ε-insensitive errors
- Uses slack variables for violations

🔗 Concepts:
- [[Epsilon-Insensitive Loss]]
- [[Convex Optimization]]
- [[Lagrangian Duality]]

---

## 5. Loss Function

SVR uses **ε-insensitive loss**:

- Errors ≤ ε → ignored
- Errors > ε → penalized linearly

🔗 See:
- [[Loss Functions — MOC]]

---

## 6. Kernel Trick

SVR uses kernels to model non-linear relationships:

- Linear
- Polynomial
- RBF (Gaussian)
- Sigmoid

🔗 Concepts:
- [[Kernel Trick]]
- [[Reproducing Kernel Hilbert Space]]

---

## 7. Support Vectors

- Only a subset of points define the model
- Points outside the ε-tube become support vectors
- Sparse solution (depends on ε and C)

🔗 See:
- [[Support Vectors]]

---

## 8. Bias–Variance Tradeoff

- High bias with large ε
- High variance with small ε and large C
- Strongly controlled by hyperparameters

🔗 Links:
- [[Bias–Variance Tradeoff]]

---

## 9. Assumptions

SVR assumes:

- Data can be modeled in some feature space
- Kernel choice reflects similarity structure
- Sensitive to noise and scaling

🔗 Contrast:
- [[Tree-Based Models — MOC]]
- [[Linear Models — MOC]]

---

## 10. Hyperparameters (Critical)

Key hyperparameters include:

- C (regularization strength)
- ε (epsilon margin)
- Kernel type
- Kernel-specific parameters (gamma, degree)

🔗 See:
- [[Hyperparameter Tuning — MOC]]

---

## 11. Feature Scaling Requirement

SVR is **highly sensitive to feature scale**:

- Feature standardization is mandatory
- Kernel distances depend on scale

🔗 Links:
- [[Feature Scaling]]
- [[Standardization]]

---

## 12. Evaluation Metrics

Uses standard regression metrics:

- RMSE
- MAE
- R²

🔗 See:
- [[Regression Metrics — MOC]]

---

## 13. Interpretability

- Linear SVR → interpretable coefficients
- Kernel SVR → low interpretability
- Support vectors give limited insight

🔗 Links:
- [[Model Interpretability]]

---

## 14. Computational Characteristics

- Training scales poorly with dataset size
- Memory-intensive for large datasets
- Not ideal for very large tabular data

🔗 Concepts:
- [[Computational Complexity]]

---

## 15. When SVR Works Well

- Small to medium datasets
- Smooth non-linear relationships
- High-dimensional feature spaces
- When trees overfit

---

## 16. When It Fails

- Large datasets
- Noisy data
- Poor kernel choice
- Improper feature scaling

---

## 17. Relationship to Other Models

- Regression counterpart of SVM
- Kernel-based alternative to polynomial regression

🔗 Related:
- [[Support Vector Machine]]
- [[Polynomial Regression]]
- [[Kernel Ridge Regression]]

---

## 18. Position in the ML Landscape

- Powerful but computationally expensive
- Strong theoretical foundation
- Less common in large-scale production systems
