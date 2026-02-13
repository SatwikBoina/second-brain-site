# 📌 MOC — Linear Algebra for Machine Learning

> Central hub for **Linear Algebra concepts used in Machine Learning**.
> Linear algebra provides the mathematical framework for **data representation, model formulation, optimization, and geometric intuition** in ML.

---

## 1. Core Idea

Machine Learning is built on three abstractions:

- Data as vectors
- Models as transformations
- Learning as optimization

Linear algebra formalizes all three.

> If statistics explains *uncertainty*, linear algebra explains *structure*.

---

## 2. Why Linear Algebra Matters for ML

Linear algebra enables:
- Compact data representation
- Efficient computation
- Understanding model geometry
- Optimization via gradients
- Dimensionality reduction
- Representation learning

Most ML algorithms are **linear at their core**, even when they appear non-linear.

---

## 3. Fundamental Objects

---

### 3.1 Scalars, Vectors, Matrices

- Scalar → single value
- Vector → ordered list (features)
- Matrix → collection of vectors (dataset, parameters)

Where used:
- Datasets
- Model parameters
- Activations in neural networks

---

### 3.2 Tensors

- Generalization of vectors and matrices
- Used heavily in deep learning

🔗 Related:
- [[Neural Networks — MOC]]

---

## 4. Vector Operations

Core operations:
- Vector addition
- Scalar multiplication
- Dot product
- Norms (L1, L2)

Why they matter:
- Similarity (cosine similarity)
- Distance metrics
- Projection
- Loss functions

🔗 Related:
- [[Distance Based Models — MOC]]

---

## 5. Matrix Operations

---

### 5.1 Matrix Multiplication

Represents:
- Linear transformations
- Model predictions
- Layer computations

Core operation of:
- Linear regression
- Neural networks

---

### 5.2 Transpose

Used in:
- Normal equations
- Gradient computation
- Covariance matrices

---

### 5.3 Inverse and Pseudo-Inverse

Used in:
- Closed-form regression solutions
- Least squares problems

🔗 Related:
- [[Linear Regression]]

---

## 6. Systems of Linear Equations

Many ML problems reduce to solving:

\[
Ax = b
\]

Examples:
- Linear regression
- Least squares
- Optimization constraints

---

## 7. Vector Spaces and Subspaces

Key ideas:
- Span
- Basis
- Dimension
- Linear independence

Why they matter:
- Feature spaces
- Dimensionality reduction
- Rank and redundancy

---

## 8. Rank and Matrix Properties

Matrix rank tells you:
- How much information exists
- Whether features are redundant
- Whether solutions are unique

Low rank → redundancy → overfitting risk.

---

## 9. Eigenvalues and Eigenvectors

One of the most important ML concepts.

Used in:
- PCA
- Stability analysis
- Covariance structure
- Spectral methods

🔗 Related:
- [[Principal Component Analysis]]

---

## 10. Matrix Decompositions

---

### 10.1 Eigen Decomposition

Used in:
- PCA (covariance matrix)

---

### 10.2 Singular Value Decomposition (SVD)

Used in:
- PCA (data matrix)
- Low-rank approximation
- Recommender systems
- Latent semantic analysis

---

### 10.3 QR Decomposition

Used in:
- Numerical stability
- Least squares solutions

---

## 11. Geometry of Linear Algebra

Linear algebra provides geometric intuition:

- Projection onto subspaces
- Orthogonality
- Angles between vectors
- Distances in high dimensions

This geometry explains:
- Why PCA works
- Why regularization helps
- Why high dimensions are dangerous

🔗 Related:
- [[Dimensionality Reduction — MOC]]
- [[Curse of Dimensionality]]

---

## 12. Linear Algebra and Optimization

Optimization relies heavily on:
- Gradients (vectors)
- Hessians (matrices)
- Quadratic forms

Used in:
- Gradient descent
- Second-order methods

🔗 Related:
- [[Gradient Descent]]
- [[Optimization Algorithms]]

---

## 13. Linear Algebra and Regularization

Regularization adds structure:

- L2 → Euclidean geometry
- L1 → sparsity via geometry

Understanding regularization requires **geometric intuition**.

🔗 Related:
- [[Regularization — MOC]]

---

## 14. Linear Algebra in Neural Networks

Neural networks are:
- Compositions of linear transformations
- Interleaved with non-linearities

Without linear algebra, deep learning is opaque.

🔗 Related:
- [[Neural Networks — MOC]]

---

## 15. Numerical Linear Algebra (Practical ML)

Real-world ML depends on:
- Numerical stability
- Conditioning
- Approximate solutions

Exact math ≠ usable computation.

---

## 16. Common Pitfalls

- ❌ Treating matrices as tables, not transformations  
- ❌ Ignoring rank deficiency  
- ❌ Blind matrix inversion  
- ❌ No geometric intuition  

Linear algebra is about **structure**, not formulas.

---

## 17. How Linear Algebra Fits in ML

Linear Algebra  
↓  
Data Representation  
↓  
Models  
↓  
Optimization  
↓  
Predictions


It is the **structural foundation** of ML.

---

## Usage Rules

- This MOC is a math backbone
- Each concept should link to ML use-cases
- Avoid pure math notes without ML context
- Always ask: *what structure does this capture?*
