---
type: algorithm
domain: machine-learning
category: anomaly-detection
model_family: kernel-based
supervision: unsupervised
primary_use: novelty_detection
status: evergreen
---

# One-Class SVM

> One-Class SVM is an anomaly detection algorithm that learns a boundary around normal data and classifies points outside the boundary as anomalies.

---

## 1. One-Line Intuition

> Learn the smallest region in feature space that encloses most of the data; anything outside is an anomaly.

---

## 2. Why One-Class SVM Exists

Distance-based methods:
- Depend on neighborhood size
- Sensitive to scaling

Density-based methods:
- Struggle in high dimensions

Tree-based methods:
- Randomized structure

One-Class SVM:
- Uses margin maximization
- Works in high-dimensional feature spaces
- Uses kernels for flexibility

🔗 Related:
- [[Support Vector Machine]]
- [[Kernel Methods — MOC]]

---

## 3. Core Idea

Given only "normal" data:

- Map data to high-dimensional space (via kernel)
- Find a hyperplane that separates data from origin
- Maximize margin

Points outside boundary:
- Classified as anomalies

---

## 4. Mathematical Formulation

Solve:

\[
\min_{w, \rho, \xi} \frac{1}{2} ||w||^2 + \frac{1}{\nu n} \sum \xi_i - \rho
\]

Subject to:

\[
(w \cdot \phi(x_i)) \geq \rho - \xi_i
\]

Where:

- \( \nu \) controls fraction of outliers
- \( \phi(x) \) is feature mapping
- \( \rho \) defines decision boundary

---

## 5. Geometric Interpretation

In feature space:

- Find a hyperplane separating data from origin.
- Maximize margin.
- Some points may lie outside (controlled by ν).

Equivalent interpretation:
> Find a minimal enclosing boundary.

---

## 6. Role of Kernel

Kernel defines shape of boundary.

Common choices:

---

### 6.1 RBF Kernel (Most Common)

\[
K(x,y) = e^{-\gamma ||x-y||^2}
\]

Produces:
- Nonlinear boundary
- Flexible contour around data

---

### 6.2 Linear Kernel

Finds:
- Linear boundary

Less flexible.

---

## 7. Key Hyperparameters

---

### 7.1 ν (nu)

Controls:

- Upper bound on fraction of anomalies
- Lower bound on fraction of support vectors

Higher ν:
- More anomalies allowed
- Softer boundary

---

### 7.2 γ (RBF Kernel)

Controls:

- Boundary smoothness

Small γ:
- Smooth boundary
- High bias

Large γ:
- Tight boundary
- High variance

🔗 Related:
- [[Hyperparameter Tuning — MOC]]
- [[Bias–Variance Tradeoff]]

---

## 8. Decision Function

A point x is anomaly if:

\[
f(x) < 0
\]

Distance from boundary determines anomaly score.

---

## 9. Strengths

- Works well in high dimensions
- Kernel flexibility
- Theoretically grounded
- Margin-based robustness

---

## 10. Weaknesses

- Sensitive to hyperparameters
- Computationally expensive for large datasets
- Not ideal for very large n
- Hard to interpret

---

## 11. Failure Modes

- ❌ Poor γ choice → overfitting or underfitting
- ❌ Very large dataset → slow training
- ❌ Highly non-stationary data
- ❌ Highly clustered anomalies

---

## 12. One-Class SVM vs Isolation Forest

| Aspect | One-Class SVM | Isolation Forest |
|----------|---------------|-----------------|
| Basis | Margin maximization | Random isolation |
| Kernel-based | Yes | No |
| High-dim robustness | Strong | Strong |
| Scalability | Moderate | High |
| Hyperparameter sensitivity | High | Moderate |

One-Class SVM is more mathematically principled.

---

## 13. One-Class SVM vs LOF

| Aspect | One-Class SVM | LOF |
|----------|---------------|-----|
| Global vs Local | Global boundary | Local density |
| Kernel-based | Yes | No |
| Distance required | Indirect | Yes |
| Varying density handling | Limited | Better |

---

## 14. One-Class SVM and Support Vectors

Only a subset of points:

- Define the boundary
- Are called support vectors

Points far inside:
- Do not affect model

---

## 15. Computational Complexity

Training:

\[
O(n^2 \text{ to } n^3)
\]

Depends on:
- Kernel
- Implementation

Not ideal for very large datasets.

---

## 16. Applications

- Fraud detection
- Intrusion detection
- Manufacturing anomaly detection
- Medical anomaly detection
- Novelty detection

---

## 17. When One-Class SVM Works Well

- High-dimensional feature space
- Nonlinear structure
- Moderate dataset size
- Need principled boundary

---

## 18. When It’s a Bad Idea

- Very large datasets
- Poor hyperparameter tuning
- Varying-density clusters
- Highly noisy data

---

## 19. Relationship to Other Concepts

One-Class SVM connects strongly to:

- [[Support Vector Machine]]
- [[Kernel Methods — MOC]]
- [[Isolation Forest]]
- [[Local Outlier Factor]]
- [[Curse of Dimensionality]]
- [[Bias–Variance Tradeoff]]

---

## 20. Why One-Class SVM Matters

One-Class SVM teaches:

- Margin-based anomaly detection
- Kernel-based boundaries
- Geometry in feature space
- How classification ideas extend to unsupervised settings

It is the cleanest bridge between:
- SVM theory
- Kernel methods
- Anomaly detection
