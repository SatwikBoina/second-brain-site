---
type: concept
domain: machine-learning
category: optimization
status: evergreen
---

# Normal Equation (Closed-Form Optimization)

> The Normal Equation is the analytical solution for minimizing squared error in linear regression.

---

# 1. One-Line Intuition

> Instead of iteratively searching for the best weights, solve for them directly using linear algebra.

---

# 2. Objective Being Minimized

Linear regression minimizes squared error:

\[
J(w) = \sum (y - Xw)^2
\]

Or in matrix form:

\[
J(w) = (y - Xw)^T (y - Xw)
\]

---

# 3. Derivation

Take gradient with respect to w:

\[
\nabla J(w) = -2X^T(y - Xw)
\]

Set gradient to zero:

\[
X^T(y - Xw) = 0
\]

Rearrange:

\[
X^T X w = X^T y
\]

Solve:

\[
\hat{w} = (X^T X)^{-1} X^T y
\]

This is the Normal Equation.

---

# 4. Why It Works

Because:

- Squared error is convex.
- Quadratic objective.
- Global minimum exists.
- Setting gradient = 0 gives exact solution.

---

# 5. Requirements

Normal equation requires:

- \(X^T X\) invertible.
- No perfect multicollinearity.

If not invertible:
- Use pseudo-inverse.

🔗 Related:
- [[Multicollinearity]]

---

# 6. Geometric Interpretation

OLS solution:

- Projects y onto column space of X.
- Finds closest point in subspace spanned by features.

Equivalent to:

Orthogonal projection.

---

# 7. Computational Complexity

Matrix inversion:

\[
O(p^3)
\]

Where:

- p = number of features.

Good for:

- Small feature count.

Not good for:

- High-dimensional datasets.

---

# 8. Normal Equation vs Gradient Descent

| Aspect | Normal Equation | Gradient Descent |
|----------|----------------|----------------|
| Iterative? | No | Yes |
| Speed (small p) | Fast | Slower |
| Speed (large p) | Slow | Better |
| Memory | High | Lower |
| Exact solution | Yes | Approximate |

---

# 9. Regularized Normal Equation

For Ridge regression:

\[
\hat{w} = (X^T X + \lambda I)^{-1} X^T y
\]

Regularization makes matrix invertible.

🔗 Related:
- [[Ridge Regression]]
- [[Regularized Loss Functions]]

---

# 10. Pseudo-Inverse Solution

If not invertible:

\[
\hat{w} = X^+ y
\]

Where:

- \(X^+\) = Moore–Penrose pseudo-inverse.

Computed using SVD.

---

# 11. Relationship to Gauss–Markov

Normal equation gives:

- BLUE estimator
- Under Gauss–Markov assumptions.

🔗 Related:
- [[Gauss–Markov Assumptions]]

---

# 12. Limitations

- Poor scaling for high dimensions.
- Numerically unstable if features correlated.
- Requires full batch data.
- Cannot easily extend to huge datasets.

---

# 13. When to Use It

- Small datasets
- Few features
- Educational purposes
- When exact solution preferred

---

# 14. When Not to Use It

- Large feature space
- Streaming data
- Deep learning
- Sparse high-dimensional data

Use:

- Gradient descent
- SGD
- Coordinate descent

---

# 15. Relationship to Other Concepts

Normal Equation connects strongly to:

- [[Linear Regression]]
- [[Squared Error Loss]]
- [[Gradient Descent]]
- [[Ridge Regression]]
- [[Multicollinearity]]
- [[Gauss–Markov Assumptions]]
- [[Optimization Methods MOC]]

---

# 16. Why Normal Equation Matters

It teaches:

- Closed-form optimization
- Linear algebra foundations of regression
- Projection interpretation
- Why multicollinearity breaks inversion

It is the classical solution to:
> Ordinary Least Squares.
