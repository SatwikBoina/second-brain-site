---
type: concept
domain: machine-learning
category: loss-functions
status: evergreen
---

# Squared Error Loss (L2 Loss)

> Squared Error Loss penalizes the square of the difference between predicted and true values.

---

# 1. One-Line Intuition

> Large errors are punished much more heavily than small errors.

---

# 2. Mathematical Definition

For a single observation:

$$
L(y, \hat{y}) = (y - \hat{y})^2
$$

For a dataset:

$$
MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
$$

---

# 3. Why Square the Error?

Squaring ensures:

- Non-negative loss
- Larger penalties for larger errors
- Smooth differentiable function
- Convex optimization

---

# 4. Geometric Interpretation

Squared error measures:

- Vertical distance from prediction to true value.
- Parabolic penalty curve.

The loss curve is a parabola centered at zero error.

---

# 5. Squared Error and Linear Regression

Linear Regression solves:

$$
\min_\beta \sum (y - X\beta)^2
$$

Closed-form solution:

$$
\hat{\beta} = (X^T X)^{-1} X^T y
$$
Squared error makes OLS solvable analytically.

🔗 Related:
- [[Linear Regression]]
- [[Gauss–Markov Assumptions]]

---

# 6. Connection to Maximum Likelihood

If errors are Gaussian:

$$
\epsilon \sim \mathcal{N}(0, \sigma^2)
$$

Maximizing likelihood is equivalent to minimizing squared error.

Thus:

Squared Error = Negative Log-Likelihood of Gaussian model.

🔗 Related:
- [[Maximum Likelihood Estimation]]

---

# 7. Gradient Behavior

Gradient:

$$
\frac{\partial L}{\partial \hat{y}} = -2(y - \hat{y})
$$

Properties:

- Gradient increases linearly with error.
- Large errors produce large gradients.
- Encourages strong correction of big mistakes.

---

# 8. Bias–Variance Perspective

Squared error is sensitive to:

- Large outliers.
- Noise with heavy tails.

High sensitivity → high variance risk.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

# 9. Squared Error vs Absolute Error

| Aspect | Squared Error | Absolute Error |
|----------|----------------|----------------|
| Penalty growth | Quadratic | Linear |
| Outlier sensitivity | High | Lower |
| Differentiable | Yes | Not everywhere |
| Optimal for Gaussian noise | Yes | No |

Squared error emphasizes large deviations.

---

# 10. Strengths

- Convex
- Smooth
- Easy to optimize
- Closed-form solution in linear regression
- Strong theoretical grounding

---

# 11. Limitations

- Very sensitive to outliers
- Assumes symmetric error distribution
- Not robust to heavy-tailed noise

---

# 12. When It Works Well

- Gaussian noise
- Moderate outliers
- Regression problems
- Well-behaved residuals

---

# 13. When It’s a Bad Idea

- Heavy-tailed distributions
- Robust regression needed
- Extreme outliers present

Alternative:
- Huber Loss
- MAE

---

# 14. Squared Error in Neural Networks

Used for:

- Regression outputs
- Continuous prediction

Rarely used for classification.

---

# 15. Relationship to Other Concepts

Squared Error Loss connects strongly to:

- [[Linear Regression]]
- [[Ridge Regression]]
- [[Elastic Net]]
- [[Maximum Likelihood Estimation]]
- [[Gauss–Markov Assumptions]]
- [[Bias–Variance Tradeoff]]
- [[Regression Loss Functions - MOC]]

---

# 16. Why Squared Error Matters

Squared Error teaches:

- How regression connects to geometry.
- Why Gaussian noise leads to L2 loss.
- Why large errors dominate optimization.
- How variance is controlled in regression.

It is the backbone of:
> Classical regression modeling.
