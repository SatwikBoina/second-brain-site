---
type: concept
domain: machine-learning
category: optimization-theory
status: evergreen
---

# Convex Optimization

> Convex optimization studies optimization problems where the objective function is convex, guaranteeing that any local minimum is also a global minimum.

---

# 1. One-Line Intuition

> If the surface looks like a bowl, any downhill path leads to the global minimum.

---

# 2. What is a Convex Set?

A set \( C \) is convex if:

For any two points \( x_1, x_2 \in C \),

\[
\lambda x_1 + (1-\lambda)x_2 \in C
\]

for all \( \lambda \in [0,1] \).

Meaning:
- Line segment between any two points lies inside the set.

---

# 3. What is a Convex Function?

A function \( f(x) \) is convex if:

\[
f(\lambda x_1 + (1-\lambda)x_2)
\le
\lambda f(x_1) + (1-\lambda)f(x_2)
\]

Geometrically:
- Function lies below line connecting two points.
- Looks like a bowl.

---

# 4. First-Order Condition

If \( f \) is convex and differentiable:

\[
f(y) \ge f(x) + \nabla f(x)^T (y-x)
\]

Gradient forms a global lower bound.

---

# 5. Second-Order Condition

If twice differentiable:

\[
\nabla^2 f(x) \succeq 0
\]

Hessian matrix must be positive semidefinite.

If positive definite:
- Strongly convex
- Unique minimum

---

# 6. Why Convexity Is Important

In convex optimization:

- No local minima (only global).
- Gradient descent converges.
- Stable solutions.
- Theoretical guarantees.

---

# 7. Examples in Machine Learning

---

## 7.1 Linear Regression

Squared error:

\[
J(w) = ||y - Xw||^2
\]

Convex quadratic function.

🔗 Related:
- [[Squared Error Loss]]
- [[Normal Equation (Closed-Form Optimization)]]

---

## 7.2 Logistic Regression

Cross-entropy loss:

\[
J(w) = -\sum y \log(\sigma(Xw))
\]

Convex in parameters.

🔗 Related:
- [[Cross-Entropy]]
- [[Sigmoid Function]]

---

## 7.3 Support Vector Machine

Hinge loss + L2 penalty:

Convex objective.

🔗 Related:
- [[Hinge Loss]]

---

# 8. Non-Convex Problems

Deep Neural Networks:

- Multiple local minima.
- Saddle points.
- Harder optimization.

Loss surface is not convex.

---

# 9. Convex Optimization Problem Form

\[
\min_x f(x)
\]

Subject to:

\[
g_i(x) \le 0
\]

If:

- f is convex
- g_i are convex

Then problem is convex.

---

# 10. Strong Convexity

Function is strongly convex if:

\[
f(x) - \frac{m}{2}||x||^2
\]

is convex for some \( m > 0 \).

Implication:
- Faster convergence.
- Unique minimizer.

---

# 11. Convergence of Gradient Descent

If:

- Convex → converges to global minimum.
- Strongly convex → linear convergence rate.
- Smooth → predictable step size behavior.

🔗 Related:
- [[Gradient Descent]]

---

# 12. Convex vs Non-Convex Summary

| Aspect | Convex | Non-Convex |
|----------|--------|------------|
| Local minima | Global | Many |
| Guarantees | Strong | Weak |
| Optimization difficulty | Easier | Harder |
| Examples | Linear models | Neural networks |

---

# 13. Duality in Convex Optimization

Convex problems allow:

- Strong duality.
- KKT conditions.
- Efficient primal-dual methods.

Important for:

- SVM dual formulation.

---

# 14. Why Most Classical ML Is Convex

Because convexity gives:

- Stability
- Interpretability
- Theoretical guarantees
- Reliable optimization

Deep learning sacrifices convexity for flexibility.

---

# 15. Relationship to Other Concepts

Convex Optimization connects strongly to:

- [[Gradient Descent]]
- [[Coordinate Descent]]
- [[Normal Equation (Closed-Form Optimization)]]
- [[Squared Error Loss]]
- [[Cross-Entropy]]
- [[Hinge Loss]]
- [[Support Vector Machine]]
- [[Bias–Variance Tradeoff]]

---

# 16. Why Convex Optimization Matters

Convex optimization teaches:

- Why some problems are easy.
- Why linear models are stable.
- Why deep learning is hard.
- Why optimization theory matters in ML.

It is the mathematical backbone of:
> Classical machine learning.
