---
type: zettel
domain: machine-learning
category: deep-learning
topic: activation-functions
status: evergreen
---

# Activation Functions

> An activation function introduces non-linearity into a neural network, enabling it to model complex patterns.

---

## 1. One-Line Intuition

> Activation functions allow neural networks to learn nonlinear relationships.

---

## 2. Why Activation Functions Are Necessary

Without activation:

$$
a^{(l)} = W^{(l)} a^{(l-1)}
$$
Stacking multiple linear layers:

$$
W_3 W_2 W_1 x
$$

Is still linear.

Therefore:

No matter how deep, the network behaves like a single linear model.

Activation functions break this linearity.

🔗 Related:
- [[Multilayer Perceptron]]

---

## 3. Desirable Properties

Good activation functions should:

- Be nonlinear
- Be differentiable (for gradient descent)
- Avoid vanishing gradients
- Be computationally efficient

🔗 Related:
- [[Gradient Descent]]

---

## 4. Common Activation Functions

---

### 4.1 Sigmoid

$$
\sigma(x) = \frac{1}{1 + e^{-x}}
$$

Range:
(0,1)

Pros:
- Probabilistic interpretation

Cons:
- Vanishing gradient
- Not zero-centered

Used in:
- Binary classification output layer

🔗 Related:
- [[Sigmoid Function]]

---

### 4.2 Tanh

$$
\tanh(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}
$$

Range:
(-1,1)

Pros:
- Zero-centered

Cons:
- Still suffers vanishing gradient

---

### 4.3 ReLU (Rectified Linear Unit)

$$
ReLU(x) = \max(0, x)
$$

Pros:
- Simple
- Computationally efficient
- Reduces vanishing gradient

Cons:
- Dying ReLU problem (gradient = 0 for x < 0)

Most widely used activation.

---

### 4.4 Leaky ReLU

$$
LeakyReLU(x) =
\begin{cases}
x & x > 0 \\
\alpha x & x \le 0
\end{cases}
$$

Fixes dying ReLU issue.

---

### 4.5 Softmax

$$
Softmax(z_i) =
\frac{e^{z_i}}{\sum_j e^{z_j}}
$$
Used in:
- Multi-class classification output.

Converts logits to probabilities.

🔗 Related:
- [[Softmax Function]]
- [[Cross-Entropy]]

---

## 5. Activation Functions and Gradient Flow

Sigmoid / Tanh:

- Gradients shrink in deep networks.
- Cause vanishing gradient problem.

ReLU:

- Gradient is 1 for positive values.
- Enables deep networks to train effectively.

🔗 Related:
- [[Vanishing Gradient Problem]]

---

## 6. Output Layer Activations

Regression:
- No activation (linear output)

Binary classification:
- Sigmoid

Multi-class classification:
- Softmax

---

## 7. Bias–Variance Perspective

Choice of activation affects:

- Model expressiveness
- Optimization stability
- Generalization

Deep nonlinear activations:

- Lower bias
- Higher variance risk

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 8. Geometric Interpretation

Activation functions:

- Bend linear hyperplanes.
- Create curved decision boundaries.
- Allow hierarchical feature composition.

---

## 9. Advanced Activations

- ELU
- GELU (used in Transformers)
- Swish

GELU is popular in modern LLMs.

---

## 10. Relationship to Other Concepts

Activation Functions connect strongly to:

- [[Multilayer Perceptron]]
- [[Convolutional Neural Networks]]
- [[Recurrent Neural Networks]]
- [[Long Short-Term Memory (LSTM)]]
- [[Transformers]]
- [[Gradient Descent]]
- [[Cross-Entropy]]

---

## 11. Why Activation Functions Matter

Activation functions teach:

- Why deep networks can model nonlinear systems.
- How gradients flow.
- Why architecture matters.
- Why deep learning became practical after ReLU.

They are the mathematical key to:
> Nonlinear representation learning.
