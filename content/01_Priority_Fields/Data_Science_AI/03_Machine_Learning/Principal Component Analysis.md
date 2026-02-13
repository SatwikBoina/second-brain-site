---
type: algorithm
domain: machine-learning
category: dimensionality-reduction
model_family: linear
status: evergreen
---

# Principal Component Analysis (PCA)

> Principal Component Analysis (PCA) is a **linear dimensionality reduction technique** that transforms data into a new coordinate system such that the directions (components) with **maximum variance** are retained.

---

## 1. One-Line Intuition

> PCA finds **new axes** that capture the **most important variation** in the data and discards directions that mostly contain noise.

---

## 2. Why PCA Exists

High-dimensional data causes problems:

- Noise accumulation
- Redundant features
- Overfitting
- Computational inefficiency

PCA addresses this by:
- Compressing data
- Removing redundancy
- Preserving maximum information (variance)

🔗 Related:
- [[Curse of Dimensionality]]
- [[Dimensionality Reduction — MOC]]

---

## 3. Geometric Intuition

Think of data as a cloud of points.

PCA:
- Rotates the coordinate system
- Aligns axes with directions of maximum spread
- Projects data onto top axes

Low-variance directions are often **noise**.

---

## 4. Statistical Intuition

PCA finds directions where:
- Data variance is maximized
- Correlation between features is removed

After PCA:
- Components are **uncorrelated**
- Each component explains decreasing variance

---

## 5. Mathematical Foundation

PCA is based on **linear algebra**.

Two equivalent views:

---

### 5.1 Covariance Matrix View

1. Center the data
2. Compute covariance matrix
3. Find eigenvectors and eigenvalues
4. Sort eigenvectors by eigenvalues

- Eigenvectors → principal components
- Eigenvalues → variance explained

---

### 5.2 SVD View (Preferred in Practice)

Apply Singular Value Decomposition directly to data matrix:

\[
X = U \Sigma V^T
\]

- Columns of \(V\) → principal directions
- Singular values → variance magnitude

🔗 Related:
- [[Linear Algebra for Machine Learning — MOC]]

---

## 6. Assumptions Behind PCA

PCA assumes:

- Linearity
- Large variance = important signal
- Orthogonal components
- Mean-centered data

If these assumptions fail, PCA may mislead.

---

## 7. What PCA Does NOT Do

- ❌ It does NOT use labels
- ❌ It does NOT find nonlinear structure
- ❌ It does NOT guarantee better predictive performance
- ❌ It does NOT preserve interpretability

PCA optimizes **variance**, not task performance.

---

## 8. Choosing Number of Components

Common strategies:

- Explained variance threshold (e.g. 95%)
- Scree plot (elbow method)
- Downstream model performance

This is a **model selection decision**.

🔗 Related:
- [[Model Selection]]

---

## 9. PCA and Feature Scaling (Critical)

PCA is **scale-sensitive**.

Always consider:
- Standardization before PCA
- Variance dominance by large-scale features

Failure to scale can invalidate PCA.

🔗 Related:
- [[Feature Scaling]]

---

## 10. PCA and Bias–Variance Tradeoff

Effect of PCA:
- Reduces variance (simpler model)
- May increase bias (information loss)

Used as:
> A variance-reduction technique

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 11. PCA in Machine Learning Pipelines

Common uses:

- Preprocessing before regression
- Noise reduction
- Visualization
- Speeding up training

PCA should live **inside pipelines**.

🔗 Related:
- [[Model Pipelines]]

---

## 12. PCA and Interpretability

Trade-off:
- Fewer features
- Less semantic meaning

Principal components are:
- Linear combinations
- Often hard to interpret

Interpretability is sacrificed for robustness.

---

## 13. PCA vs Feature Selection

| Aspect | PCA | Feature Selection |
|---|---|---|
| Uses original features | ❌ | ✅ |
| Creates new features | ✅ | ❌ |
| Removes redundancy | ✅ | Sometimes |
| Interpretability | Low | High |

🔗 Related:
- [[Feature Selection]]

---

## 14. PCA and Information Theory View

PCA can be seen as:
- Information compression
- Variance-preserving encoding

But variance ≠ information in all tasks.

🔗 Related:
- [[Information Theory — MOC]]

---

## 15. PCA Failure Modes

- ❌ Nonlinear structure
- ❌ Task-relevant low-variance features
- ❌ Heavy outliers
- ❌ Improper scaling

Always validate PCA downstream.

---

## 16. When PCA Works Well

- High-dimensional continuous data
- Correlated features
- Noise-dominated dimensions
- Visualization (2D / 3D)

---

## 17. When PCA Is a Bad Idea

- Strongly nonlinear data
- When interpretability is critical
- When variance ≠ signal
- Sparse categorical features

---

## 18. Relationship to Other Concepts

PCA connects strongly to:

- [[Dimensionality Reduction — MOC]]
- [[Linear Algebra for Machine Learning — MOC]]
- [[Curse of Dimensionality]]
- [[Bias–Variance Tradeoff]]
- [[Feature Scaling]]
- [[Model Selection]]

---

## 19. Why PCA Matters

PCA explains:

- Why dimensionality reduction works
- Why correlated features hurt models
- Why noise dominates in high dimensions
- Why linear algebra is essential in ML

It is the **gateway algorithm** to representation learning.

---

## Usage Notes

- Treat PCA as part of preprocessing, not magic
- Always validate with downstream task
- Keep PCA inside pipelines
- Ask: *what information is being discarded?*
