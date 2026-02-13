---
type: concept
domain: machine-learning
category: optimization
status: evergreen
---

# Coordinate Descent

> Coordinate Descent is an optimization algorithm that minimizes a function by updating one parameter at a time while keeping others fixed.

---

# 1. One-Line Intuition

> Instead of moving in all directions at once, optimize one coordinate at a time.

---

# 2. General Idea

We want to minimize:

\[
J(w_1, w_2, ..., w_p)
\]

Instead of updating:

\[
w := w - \eta \nabla J(w)
\]

We:

1. Fix all parameters except \( w_1 \), optimize it.
2. Fix all except \( w_2 \), optimize it.
3. Repeat cyclically.

---

# 3. Basic Update Rule

For coordinate \( j \):

\[
w_j := \arg\min_{w_j} J(w_1, ..., w_j, ..., w_p)
\]

Other coordinates remain fixed.

---

# 4. Why It Works

If objective is:

- Convex
- Separable or partially separable

Coordinate updates:

- Reduce loss at each step.
- Converge to global minimum (if convex).

---

# 5. Example: Lasso Regression

Objective:

\[
\min \frac{1}{2n} ||y - Xw||^2 + \lambda \sum |w_j|
\]

Coordinate descent has:

Closed-form soft-thresholding update:

\[
w_j :=
S\left(\frac{1}{n} x_j^T (y - X_{-j} w_{-j}), \lambda\right)
\]

Where:

\[
S(z, \lambda) =
\begin{cases}
z - \lambda & z > \lambda \\
z + \lambda & z < -\lambda \\
0 & \text{otherwise}
\end{cases}
\]

This is why coordinate descent is perfect for L1 regularization.

🔗 Related:
- [[Lasso Regression]]
- [[Elastic Net]]
- [[Regularized Loss Functions]]

---

# 6. Coordinate Descent vs Gradient Descent

| Aspect | Coordinate Descent | Gradient Descent |
|----------|-------------------|------------------|
| Update | One parameter at a time | All parameters at once |
| Requires learning rate? | Often no | Yes |
| Good for L1? | Excellent | Harder |
| Parallelizable? | Limited | Yes |

---

# 7. When It Works Well

- Sparse high-dimensional data
- L1 regularization
- Convex problems
- Few non-zero features expected

Used in:

- Lasso
- Elastic Net
- Logistic regression with L1

---

# 8. When It Struggles

- Highly coupled parameters
- Non-convex surfaces
- Deep neural networks

Gradient-based methods dominate deep learning.

---

# 9. Geometric Interpretation

Imagine minimizing a bowl-shaped function:

Instead of moving diagonally:

- Move horizontally (optimize w1)
- Then vertically (optimize w2)

Like walking along axes in zig-zag fashion.

---

# 10. Convergence

For convex problems:

- Converges to global minimum.
- Often very fast in sparse problems.

For strongly convex functions:
- Linear convergence rate.

---

# 11. Coordinate Descent and Sparsity

L1 penalty:

- Creates non-differentiability.
- Gradient descent struggles at zero.
- Coordinate descent handles it naturally.

This makes it ideal for:

- Sparse modeling.

---

# 12. Cyclic vs Random Coordinate Descent

Cyclic:
- Update coordinates in order.

Random:
- Pick coordinate randomly.

Random sometimes:
- Converges faster.
- Avoids pathological cycles.

---

# 13. Computational Complexity

Per update:

\[
O(n)
\]

Full cycle:

\[
O(np)
\]

Often cheaper than full gradient in high-dimensional sparse data.

---

# 14. Relationship to Other Concepts

Coordinate Descent connects strongly to:

- [[Lasso Regression]]
- [[Elastic Net]]
- [[Regularized Loss Functions]]
- [[Gradient Descent]]
- [[Convex Optimization]]
- [[Bias–Variance Tradeoff]]

---

# 15. Why Coordinate Descent Matters

It teaches:

- Optimization by decomposition.
- Why L1 problems need special treatment.
- How sparsity emerges in practice.
- Why certain algorithms scale better for high dimensions.

It is the backbone of:
> Sparse linear modeling.
