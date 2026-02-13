---
type: concept
domain: machine-learning
category: probabilistic-models
status: evergreen
---

# Sigmoid Function (Logistic Function)

> The Sigmoid function maps any real-valued number to a probability between 0 and 1.

---

## 1. One-Line Intuition

> Sigmoid squashes any real number into a smooth probability between 0 and 1.

---

## 2. Mathematical Definition

\[
\sigma(z) = \frac{1}{1 + e^{-z}}
\]

Where:

- \(z\) = logit (raw model output)
- Output ∈ (0, 1)

---

## 3. Shape of Sigmoid

- S-shaped curve
- Smooth
- Monotonic increasing
- Asymptotes at 0 and 1

As:

\[
z \to +\infty \Rightarrow \sigma(z) \to 1
\]

\[
z \to -\infty \Rightarrow \sigma(z) \to 0
\]

---

## 4. Why Sigmoid Is Used

In binary classification:

- We want probabilities.
- Output must be between 0 and 1.
- Must be differentiable.

Sigmoid satisfies all three.

---

## 5. Sigmoid and Logistic Regression

Logistic Regression model:

\[
z = w^T x + b
\]

\[
P(y=1|x) = \sigma(z)
\]

Sigmoid converts linear score into probability.

🔗 Related:
- [[Logistic Regression]]

---

## 6. Odds and Log-Odds Interpretation

Odds:

\[
\text{odds} = \frac{p}{1-p}
\]

Log-odds (logit):

\[
\log\left(\frac{p}{1-p}\right) = z
\]

Sigmoid is inverse of logit.

This means:

> Logistic regression models log-odds linearly.

---

## 7. Decision Rule

Prediction:

\[
\hat{y} = 
\begin{cases}
1 & \text{if } \sigma(z) \ge 0.5 \\
0 & \text{otherwise}
\end{cases}
\]

Equivalent to:

\[
z \ge 0
\]

Sigmoid does not change decision boundary —
only probability interpretation.

---

## 8. Derivative of Sigmoid

\[
\sigma'(z) = \sigma(z)(1 - \sigma(z))
\]

Important because:

- Makes gradient computation simple.
- Used in neural network backpropagation.

🔗 Related:
- [[Optimization Methods — MOC]]

---

## 9. Sigmoid and Cross-Entropy Loss

Binary cross-entropy:

\[
Loss = -[y \log(\hat{y}) + (1-y)\log(1-\hat{y})]
\]

Where:

\[
\hat{y} = \sigma(z)
\]

Sigmoid + cross-entropy gives clean gradients.

🔗 Related:
- [[Classification Loss Functions — MOC]]
- [[Entropy]]

---

## 10. Sigmoid vs Softmax

| Aspect | Sigmoid | Softmax |
|----------|----------|----------|
| Classes | Binary | Multi-class |
| Output sum | Not constrained | Sums to 1 |
| Use case | Independent binary outputs | Mutually exclusive classes |

Softmax generalizes sigmoid to multiple classes.

🔗 Related:
- [[Softmax Function]]

---

## 11. Numerical Stability

For large negative z:

\[
e^{-z} \text{ can overflow}
\]

Stable implementations handle this carefully.

---

## 12. Sigmoid in Neural Networks

Used in:

- Binary classification output layer
- Hidden layers (historically)

But in deep networks:

- ReLU preferred for hidden layers
- Sigmoid causes vanishing gradient problem

---

## 13. Vanishing Gradient Problem

For large |z|:

\[
\sigma'(z) \approx 0
\]

Gradient becomes very small.

Leads to:

- Slow learning
- Training instability

---

## 14. Strengths

- Probabilistic interpretation
- Smooth and differentiable
- Works naturally with log-loss
- Simple and interpretable

---

## 15. Limitations

- Vanishing gradients
- Output not zero-centered
- Saturates at extremes
- Only suitable for binary output

---

## 16. Relationship to Other Concepts

Sigmoid connects strongly to:

- [[Logistic Regression]]
- [[Softmax Function]]
- [[Cross Entropy]]
- [[Neural Network Classifier]]
- [[Probabilistic Models — MOC]]
- [[Maximum Likelihood Estimation]]

---

## 17. Why Sigmoid Matters

Sigmoid teaches:

- How linear models produce probabilities
- Log-odds interpretation
- Binary classification foundations
- Why cross-entropy is natural

It is the backbone of:
> Logistic regression and binary neural networks.
