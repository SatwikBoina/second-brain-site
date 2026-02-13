# 📌 MOC — Kernel Methods

> Central hub for all **kernel-based learning algorithms**.
> Kernel methods implicitly map data into high-dimensional feature spaces to model non-linear relationships using linear algorithms.

---

## 1. Core Idea

Kernel methods replace explicit feature transformation with a **kernel function** that computes similarity directly in an implicit feature space.

> “Compute inner products without computing features.”

---

## 2. Why Kernels Work

- Enable non-linear modeling using linear algorithms
- Avoid explicit high-dimensional feature expansion
- Rely on similarity rather than explicit representation

🔗 Core concept:
- [[Kernel Trick]]

---

## 3. Common Kernel Functions

- [[Linear Kernel]]
- [[Polynomial Kernel]]
- [[RBF Kernel]]
- [[Sigmoid Kernel]]

---

## 4. Supervised Algorithms Using Kernels

### Classification

- [[Support Vector Machine]]

### Regression

- [[Support Vector Regression]]
- [[Kernel Ridge Regression]]

---

## 5. Loss Functions in Kernel Methods

- [[Hinge Loss]]
- [[Epsilon-Insensitive Loss]]
- [[Squared Error Loss]]

---

## 6. Optimization Foundations

Kernel methods rely heavily on convex optimization:

- [[Convex Optimization]]
- [[Lagrangian Duality]]
- [[Quadratic Programming]]
- [[KKT Conditions]]

---

## 7. Bias–Variance Perspective

- Kernel choice controls model flexibility
- Regularization controls overfitting
- Overly complex kernels → high variance

🔗 See:
- [[Bias–Variance Tradeoff]]

---

## 8. Hyperparameters in Kernel Methods

- Kernel type
- Kernel parameters (gamma, degree)
- Regularization strength (C, λ)

🔗 See:
- [[Hyperparameter Tuning — MOC]]

---

## 9. Feature Scaling Requirement

Kernel methods are **scale-sensitive**:

- Feature standardization is mandatory
- Distance-based similarity depends on scale

🔗 Links:
- [[Feature Scaling]]
- [[Standardization]]

---

## 10. Computational Characteristics

- Memory intensive
- Training scales poorly with dataset size
- Kernel matrix size grows quadratically

🔗 Concepts:
- [[Computational Complexity]]
- [[Kernel Matrix]]

---

## 11. Interpretability

- Linear kernels → interpretable
- Non-linear kernels → low interpretability
- Support vectors provide limited insight

🔗 Links:
- [[Model Interpretability]]

---

## 12. When to Use Kernel Methods

- Small to medium datasets
- Non-linear decision boundaries
- High-dimensional feature spaces

---

## 13. When to Avoid Kernel Methods

- Very large datasets
- Real-time or low-latency systems
- When simpler models perform similarly

---

## 14. Relationship to Other Model Families

- Generalizes [[Linear Models — MOC]]
- Alternative to explicit feature engineering
- Contrast with [[Tree-Based Models — MOC]]

---

## Usage Rules

- No algorithm derivations here
- Algorithms must live in separate notes
- Concepts must remain atomic
- Extend only via links
