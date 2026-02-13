---
type: concept
domain: machine-learning
category: optimization
status: evergreen
---

# Gradient Descent

> Gradient Descent is an iterative optimization algorithm that minimizes a loss function by moving in the direction of steepest descent.

---

# 1. One-Line Intuition

> Move downhill in the direction where the loss decreases the fastest.

---

# 2. Mathematical Idea

We want to minimize:

\[
J(w)
\]

Gradient:

\[
\nabla J(w)
\]

Update rule:

\[
w := w - \eta \nabla J(w)
\]

Where:

- \( \eta \) = learning rate
- \( \nabla J(w) \) = gradient (direction of steepest ascent)
- We subtract it to go downhill.

---

# 3. Why It Works

The gradient points toward:

- Steepest increase.

So:

\[
- \nabla J(w)
\]

Points toward steepest decrease.

For small step sizes:

- Loss decreases at each iteration.

---

# 4. Example: Linear Regression

Squared error:

\[
J(w) = \frac{1}{n} \sum (y - Xw)^2
\]

Gradient:

\[
\nabla J(w) = -\frac{2}{n} X^T (y - Xw)
\]

Update:

\[
w := w + \frac{2\eta}{n} X^T (y - Xw)
\]

Iteratively approaches normal equation solution.

🔗 Related:
- [[Normal Equation (Closed-Form Optimization)]]
- [[Squared Error Loss]]

---

# 5. Learning Rate (η)

Controls step size.

Too small:
- Slow convergence.

Too large:
- Divergence.
- Oscillation.

Choosing η is critical.

---

# 6. Convergence Properties

If loss is:

- Convex → converges to global minimum.
- Strongly convex → faster convergence.
- Non-convex → may converge to local minima.

🔗 Related:
- [[Convex Optimization]]

---

# 7. Batch Gradient Descent

Uses:

- Entire dataset per update.

Pros:
- Stable updates.

Cons:
- Expensive for large datasets.

---

# 8. Stochastic Gradient Descent (SGD)

Uses:

- One sample per update.

Pros:
- Fast
- Scales well
- Escapes shallow local minima

Cons:
- Noisy updates

---

# 9. Mini-Batch Gradient Descent

Compromise:

- Small batch per update.

Used in:
- Deep learning.

---

# 10. Geometric Interpretation

Think of:

- Loss surface as landscape.
- Parameters as coordinates.
- Gradient descent walks downhill.

---

# 11. First-Order Optimization

Gradient Descent uses:

- First derivatives only.

Does NOT use:
- Second derivatives (like Newton’s method).

Cheaper but slower.

---

# 12. Relation to Maximum Likelihood

For many models:

Minimizing loss = maximizing log-likelihood.

Gradient descent optimizes MLE numerically.

🔗 Related:
- [[Maximum Likelihood Estimation]]
- [[Cross-Entropy]]

---

# 13. Bias–Variance Perspective

Gradient descent itself:

- Does not change bias/variance.

But:

- Learning rate
- Early stopping
- Regularization

Affect model complexity.

🔗 Related:
- [[Regularized Loss Functions]]

---

# 14. Common Problems

---

## 14.1 Local Minima

In non-convex problems.

---

## 14.2 Saddle Points

Gradient ≈ 0 but not minimum.

Common in high dimensions.

---

## 14.3 Vanishing / Exploding Gradients

Especially in deep networks.

🔗 Related:
- [[Sigmoid Function]]

---

# 15. Enhancements

Advanced optimizers:

- Momentum
- Nesterov
- AdaGrad
- RMSProp
- Adam

All modify update rule.

---

# 16. When Gradient Descent Is Preferred

- Large datasets
- High-dimensional data
- Neural networks
- Streaming data

---

# 17. When Not Ideal

- Small dataset with few features
- Closed-form solution available
- Ill-conditioned matrix

Use:

- Normal equation
- Second-order methods

---

# 18. Relationship to Other Concepts

Gradient Descent connects strongly to:

- [[Normal Equation (Closed-Form Optimization)]]
- [[Squared Error Loss]]
- [[Cross-Entropy]]
- [[Maximum Likelihood Estimation]]
- [[Regularized Loss Functions]]
- [[Optimization Methods MOC]]
- [[Bias–Variance Tradeoff]]

---

# 19. Why Gradient Descent Matters

It teaches:

- Iterative optimization
- Role of derivatives in ML
- Why learning rate matters
- How deep learning is trained

It is the engine behind:
> Modern machine learning.
