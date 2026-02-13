---
type: concept
domain: machine-learning
category: probabilistic-models
status: evergreen
---

# Softmax Function

> The Softmax function converts a vector of real numbers into a probability distribution over multiple classes.

---

## 1. One-Line Intuition

> Softmax turns raw scores into probabilities that sum to 1.

---

## 2. Mathematical Definition

For a vector \( z = [z_1, z_2, ..., z_K] \):

\[
Softmax(z_i) = \frac{e^{z_i}}{\sum_{j=1}^{K} e^{z_j}}
\]

Where:

- \(z_i\) = raw model score (logit)
- Output is between 0 and 1
- Sum of outputs = 1

---

## 3. Why We Need Softmax

In multi-class classification:

- Model outputs raw scores (logits).
- We need probabilities.
- Probabilities must:
  - Be non-negative
  - Sum to 1

Softmax ensures this.

---

## 4. Example

Suppose logits:

\[
z = [2, 1, 0]
\]

Exponentials:

\[
[e^2, e^1, e^0] ≈ [7.39, 2.72, 1]
\]

Normalize:

\[
[0.67, 0.24, 0.09]
\]

Interpretation:
- Class 1 has 67% probability.

---

## 5. Geometric Interpretation

Softmax:

- Amplifies large scores
- Suppresses small scores
- Creates competition between classes

If one logit increases:
- Other probabilities decrease.

---

## 6. Softmax vs Sigmoid

| Aspect | Sigmoid | Softmax |
|----------|----------|----------|
| Output type | Binary probability | Multi-class probabilities |
| Sum to 1? | No | Yes |
| Use case | Binary classification | Multi-class classification |

Softmax generalizes sigmoid to multiple classes.

---

## 7. Logits

Before softmax:

\[
z_i = w_i^T x + b_i
\]

These are called:

- Logits
- Unnormalized log probabilities

Softmax converts logits to probabilities.

🔗 Related:
- [[Logistic Regression]]
- [[Neural Network Classifier]]

---

## 8. Softmax and Cross-Entropy Loss

In classification:

\[
Loss = -\sum y_i \log(\hat{y}_i)
\]

Where:
- \(\hat{y}_i\) = softmax output

Softmax + Cross-Entropy simplifies gradient computation.

🔗 Related:
- [[Classification Loss Functions — MOC]]
- [[Entropy]]

---

## 9. Numerical Stability Trick

Exponentials can overflow.

To stabilize:

\[
Softmax(z_i) = \frac{e^{z_i - max(z)}}{\sum e^{z_j - max(z)}}
\]

Subtracting max does not change probabilities.

---

## 10. Temperature Scaling

Softmax with temperature T:

\[
Softmax(z_i) = \frac{e^{z_i/T}}{\sum e^{z_j/T}}
\]

Small T:
- Sharper distribution
- More confident

Large T:
- Smoother distribution
- More uncertain

Used in:
- Knowledge distillation
- Calibration

---

## 11. Properties of Softmax

- Differentiable
- Smooth
- Competitive normalization
- Translation invariant

---

## 12. Softmax and Decision Boundary

Decision rule:

\[
\hat{y} = \arg\max_i Softmax(z_i)
\]

Equivalent to:

\[
\arg\max_i z_i
\]

Softmax does not change decision boundary —
it only changes interpretation.

---

## 13. Softmax in Neural Networks

Final layer in multi-class NN:

1. Linear transformation
2. Softmax activation

Produces probability distribution.

🔗 Related:
- [[Neural Networks — MOC]]

---

## 14. Strengths

- Converts logits to valid probabilities
- Works naturally with cross-entropy
- Smooth and differentiable
- Widely used

---

## 15. Limitations

- Can produce overconfident probabilities
- Sensitive to large logits
- Assumes mutually exclusive classes

---

## 16. Relationship to Other Concepts

Softmax connects strongly to:

- [[Logistic Regression]]
- [[Neural Network Classifier]]
- [[Entropy]]
- [[Cross Entropy]]
- [[Classification Loss Functions — MOC]]
- [[Probabilistic Models — MOC]]

---

## 17. Why Softmax Matters

Softmax teaches:

- How scores become probabilities
- Why exponentials amplify differences
- How multi-class classification works
- Why cross-entropy is natural

It is the backbone of:
> Modern multi-class classification.
