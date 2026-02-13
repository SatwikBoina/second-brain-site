---
type: zettel
domain: machine-learning
category: neural-networks
topic: multilayer-perceptron
status: evergreen
---

# Multilayer Perceptron (MLP)

> A Multilayer Perceptron (MLP) is a feedforward neural network composed of multiple layers of fully connected neurons with nonlinear activation functions.

---

## 1. One-Line Intuition

> Stack linear models with nonlinear activations to model complex patterns.

---

## 2. Architecture

An MLP consists of:

1. Input layer
2. One or more hidden layers
3. Output layer

Each layer performs:

\[
z^{(l)} = W^{(l)} a^{(l-1)} + b^{(l)}
\]

\[
a^{(l)} = \phi(z^{(l)})
\]

Where:

- \(W^{(l)}\) = weight matrix
- \(b^{(l)}\) = bias vector
- \(a^{(l)}\) = activations
- \(\phi\) = activation function

---

## 3. Why Multiple Layers Matter

Without nonlinearity:

- Stacking linear layers = single linear model.

With nonlinear activations:

- Model becomes highly expressive.
- Can approximate complex functions.

---

## 4. Activation Functions

Common choices:

- ReLU
- Sigmoid
- Tanh
- Softmax (output layer for classification)

🔗 Related:
- [[Sigmoid Function]]
- [[Softmax Function]]

---

## 5. Forward Pass

Data flows:

Input → Hidden layers → Output

Each layer:

- Applies linear transformation
- Applies nonlinear activation

Produces final prediction.

---

## 6. Loss Functions

For regression:
- Squared Error

For classification:
- Cross-Entropy

🔗 Related:
- [[Squared Error Loss]]
- [[Cross-Entropy]]

---

## 7. Backpropagation

Training uses:

- Gradient descent
- Chain rule to compute gradients
- Weight updates:

\[
W := W - \eta \frac{\partial L}{\partial W}
\]

🔗 Related:
- [[Gradient Descent]]

---

## 8. Universal Approximation Theorem

A single hidden layer MLP with enough neurons can approximate:

> Any continuous function on a compact domain.

Depth often improves:

- Efficiency
- Generalization

---

## 9. Bias–Variance Perspective

Small MLP:
- High bias
- Low variance

Deep large MLP:
- Low bias
- High variance
- Risk of overfitting

Regularization helps.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Regularized Loss Functions]]

---

## 10. Optimization Characteristics

Unlike linear regression:

- Loss surface is non-convex.
- Many local minima.
- Saddle points common.

🔗 Related:
- [[Convex Optimization]]

---

## 11. Strengths

- Flexible function approximator.
- Handles nonlinear interactions.
- Works for regression and classification.
- Foundation for deep learning.

---

## 12. Limitations

- Requires large data.
- Sensitive to hyperparameters.
- Harder to interpret.
- Computationally expensive.

---

## 13. Comparison to Linear Models

| Aspect | Linear Model | MLP |
|--------|-------------|-----|
| Decision boundary | Linear | Nonlinear |
| Convex optimization | Yes | No |
| Interpretability | High | Low |
| Expressiveness | Limited | High |

---

## 14. Relationship to Other Concepts

MLP connects strongly to:

- [[Neural Network Classifier]]
- [[Gradient Descent]]
- [[Backpropagation]]
- [[Sigmoid Function]]
- [[Softmax Function]]
- [[Cross-Entropy]]
- [[Regularized Loss Functions]]
- [[Bias–Variance Tradeoff]]

---

## 15. Why MLP Matters

The Multilayer Perceptron teaches:

- How depth creates nonlinearity.
- How gradients train complex models.
- Why optimization becomes hard.
- The foundation of deep learning.

It is the basic building block of:
> Modern neural networks.
