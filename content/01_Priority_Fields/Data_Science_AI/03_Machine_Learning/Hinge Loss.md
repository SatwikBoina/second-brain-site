---
type: concept
domain: machine-learning
category: margin-based-learning
status: evergreen
---

# Hinge Loss

> Hinge Loss is a loss function used in Support Vector Machines that penalizes predictions that are not only wrong, but also not confidently correct.

---

## 1. One-Line Intuition

> Correct predictions are not enough — they must also be confidently correct.

---

## 2. Mathematical Definition

For binary classification with labels:

\[
y \in \{-1, +1\}
\]

Prediction:

\[
f(x) = w^T x + b
\]

Hinge loss:

\[
L(y, f(x)) = \max(0, 1 - y f(x))
\]

---

## 3. Interpretation

Case 1: Correct and confident

\[
y f(x) \ge 1
\]

Loss = 0

Case 2: Correct but not confident

\[
0 < y f(x) < 1
\]

Loss > 0

Case 3: Wrong prediction

\[
y f(x) < 0
\]

Large loss

---

## 4. Geometric Interpretation

Hinge loss enforces a **margin**:

- Correct classification is not enough.
- Points must lie outside the margin boundary.

This leads to:

> Maximum margin decision boundary.

🔗 Related:
- [[Support Vector Machine]]

---

## 5. Visual Shape of Hinge Loss

Piecewise function:

- Linear penalty when margin violated
- Zero loss beyond margin

Unlike logistic loss:
- No smooth probability interpretation.

---

## 6. SVM Optimization Objective

Soft-margin SVM solves:

\[
\min_{w,b} \frac{1}{2} ||w||^2 + C \sum \max(0, 1 - y_i f(x_i))
\]

Where:

- First term = regularization (margin maximization)
- Second term = hinge loss
- C controls tradeoff

---

## 7. Role of Margin

Margin = distance from decision boundary.

Larger margin:

- Better generalization
- Lower variance
- More robust classifier

Hinge loss enforces margin.

---

## 8. Hinge Loss vs Logistic Loss

| Aspect | Hinge Loss | Logistic Loss |
|----------|------------|---------------|
| Used in | SVM | Logistic Regression |
| Probabilistic output | No | Yes |
| Margin-based | Yes | No |
| Smooth | No | Yes |
| Optimization | Quadratic programming | Gradient descent |

Hinge focuses on margin.
Logistic focuses on probabilities.

🔗 Related:
- [[Logistic Regression]]
- [[Sigmoid Function]]

---

## 9. Subgradient

Hinge loss is not differentiable at margin.

Subgradient:

If \( y f(x) < 1 \):

\[
\frac{\partial L}{\partial w} = -y x
\]

If \( y f(x) \ge 1 \):

\[
\frac{\partial L}{\partial w} = 0
\]

Used in subgradient descent.

---

## 10. Hinge Loss Variants

### Squared Hinge Loss

\[
L = \max(0, 1 - y f(x))^2
\]

- Smoother
- Penalizes violations more strongly

---

### Multiclass Hinge Loss

Used in multi-class SVM:

\[
L = \max_{j \ne y} (0, 1 + f_j(x) - f_y(x))
\]

---

## 11. Bias–Variance Perspective

Hard-margin SVM:

- Low bias
- High variance (if noisy data)

Soft-margin SVM:

- Controlled by C
- Balances bias–variance

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 12. Strengths

- Strong theoretical foundation
- Maximizes margin
- Robust to overfitting (with regularization)
- Works well in high dimensions

---

## 13. Limitations

- Not probabilistic
- Not smooth everywhere
- Less interpretable
- Requires careful C tuning

---

## 14. When Hinge Loss Works Well

- High-dimensional sparse data
- Text classification
- Linearly separable data
- Margin-based problems

---

## 15. Relationship to Other Concepts

Hinge Loss connects strongly to:

- [[Support Vector Machine]]
- [[Margin-Based Losses]]
- [[Regularization — MOC]]
- [[Kernel Methods — MOC]]
- [[Bias–Variance Tradeoff]]
- [[Softmax Function]]

---

## 16. Why Hinge Loss Matters

Hinge loss teaches:

- Importance of margin
- Difference between probability and confidence
- Why maximum margin improves generalization
- Structural risk minimization

It is the backbone of:
> Support Vector Machines.
