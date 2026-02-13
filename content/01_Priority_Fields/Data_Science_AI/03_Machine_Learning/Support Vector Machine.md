---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: classification
model-family: kernel-methods
status: evergreen
---

# Support Vector Machine (SVM)

> A supervised learning algorithm that finds the optimal separating hyperplane by maximizing the margin between classes, optionally using kernels to model non-linear boundaries.

---

## 1. Core Idea

Support Vector Machine classifies data by finding a **decision boundary with the maximum margin** between classes.

Only a subset of points — the **support vectors** — define this boundary.

🔗 Model family:
- [[Kernel Methods — MOC]]

---

## 2. Intuition

Instead of just separating classes, SVM asks:

> “What is the *most confident* separation I can make?”

A larger margin means better generalization.

---

## 3. Analogy

Imagine placing a **fence** between two groups:
- You want it as far as possible from both sides
- Only the closest people to the fence matter
- Everyone else is irrelevant

Those closest people are the *support vectors*.

---

## 4. Mathematical Perspective

SVM solves a constrained optimization problem:

- Maximizes margin (‖w‖⁻¹)
- Penalizes misclassification via slack variables
- Has a convex objective → global optimum guaranteed

🔗 Concepts:
- [[Margin Maximization]]
- [[Convex Optimization]]
- [[Lagrangian Duality]]

---

## 5. Loss Function

SVM uses **hinge loss**:

- Correct classification beyond margin → no loss
- Incorrect or weakly correct → linear penalty

🔗 See:
- [[Hinge Loss]]
- [[Loss Functions — MOC]]

---

## 6. Hard Margin vs Soft Margin

- **Hard Margin**  
  → No misclassification allowed  
  → Works only for perfectly separable data  

- **Soft Margin**  
  → Allows violations  
  → Controlled by regularization parameter `C`

🔗 Concepts:
- [[Soft Margin SVM]]
- [[Regularization — MOC]]

---

## 7. Kernel Trick

SVM uses kernels to create **non-linear decision boundaries**:

- Linear
- Polynomial
- RBF (Gaussian)
- Sigmoid

🔗 Concepts:
- [[Kernel Trick]]
- [[Reproducing Kernel Hilbert Space]]

---

## 8. Support Vectors

- Data points closest to the margin
- Define the decision boundary
- Model complexity depends on their number

🔗 See:
- [[Support Vectors]]

---

## 9. Bias–Variance Tradeoff

- Large margin → higher bias, lower variance
- Small margin → lower bias, higher variance
- Controlled by `C` and kernel parameters

🔗 Links:
- [[Bias–Variance Tradeoff]]

---

## 10. Assumptions

SVM assumes:

- Classes are separable in some feature space
- Kernel captures similarity correctly
- Sensitive to noise and overlapping classes

🔗 Contrast:
- [[Tree-Based Models — MOC]]
- [[Linear Models — MOC]]

---

## 11. Hyperparameters (Critical)

Key hyperparameters include:

- C (regularization strength)
- Kernel type
- Gamma (for RBF kernel)
- Degree (for polynomial kernel)

🔗 See:
- [[Hyperparameter Tuning — MOC]]

---

## 12. Feature Scaling Requirement

SVM is **extremely sensitive to feature scale**:

- Mandatory standardization
- Distance-based optimization depends on scale

🔗 Links:
- [[Feature Scaling]]
- [[Standardization]]

---

## 13. Evaluation Metrics

Uses standard classification metrics:

- Accuracy
- Precision / Recall
- F1-score
- ROC–AUC

🔗 See:
- [[Classification Metrics — MOC]]

---

## 14. Interpretability

- Linear SVM → interpretable coefficients
- Kernel SVM → low interpretability
- Support vectors offer limited insight

🔗 Links:
- [[Model Interpretability]]

---

## 15. Computational Characteristics

- Training complexity grows quickly with data size
- Memory intensive
- Not ideal for very large datasets

🔗 Concepts:
- [[Computational Complexity]]

---

## 16. When SVM Works Well

- Small to medium datasets
- Clear margin between classes
- High-dimensional feature spaces (e.g. text)

---

## 17. When It Fails

- Very large datasets
- Noisy, overlapping classes
- Poor kernel or hyperparameter choice

---

## 18. Relationship to Other Models

- Classification counterpart of SVR
- Kernel-based alternative to Logistic Regression

🔗 Related:
- [[Support Vector Regression]]
- [[Logistic Regression]]
- [[Kernel Ridge Regression]]

---

## 19. Position in the ML Landscape

- Strong theoretical foundations
- Geometry-based classifier
- Common in academia and niche production use
