---
type: zettel
domain: machine-learning
category: deep-learning
topic: recurrent-neural-networks
status: evergreen
---

# Recurrent Neural Networks (RNN)

> A Recurrent Neural Network (RNN) is a neural network designed for sequential data, where information from previous steps influences the current output.

---

## 1. One-Line Intuition

> Unlike feedforward networks, RNNs remember past information while processing sequences.

---

## 2. Why RNNs Exist

Standard MLP:

- Assumes inputs are independent.
- Cannot handle sequences naturally.

But many real-world problems involve sequences:

- Sentences
- Time series
- Audio signals
- Stock prices

RNNs handle dependencies across time.

---

## 3. Core Architecture

At time step t:

\[
h_t = f(W_x x_t + W_h h_{t-1} + b)
\]

\[
y_t = g(W_y h_t)
\]

Where:

- \(x_t\) = input at time t
- \(h_t\) = hidden state (memory)
- \(y_t\) = output
- \(W_x, W_h, W_y\) = weight matrices

The hidden state carries information forward.

---

## 4. Recurrent Structure

Key idea:

\[
h_t \text{ depends on } h_{t-1}
\]

The network is:

- Unrolled across time.
- Same weights reused at each step.

This is weight sharing across time.

---

## 5. Types of RNN Architectures

- One-to-One (standard NN)
- One-to-Many (image captioning)
- Many-to-One (sentiment analysis)
- Many-to-Many (translation)

---

## 6. Backpropagation Through Time (BPTT)

Training involves:

- Unrolling network across time.
- Applying backpropagation.
- Updating shared weights.

Gradient accumulates over time steps.

🔗 Related:
- [[Gradient Descent]]
- [[Multilayer Perceptron]]

---

## 7. Vanishing & Exploding Gradients

Major problem in RNNs:

Repeated multiplication:

\[
W_h^t
\]

If eigenvalues:

- < 1 → gradients vanish.
- > 1 → gradients explode.

This makes long-term dependencies hard to learn.

---

## 8. Long Short-Term Memory (LSTM)

LSTM introduces:

- Memory cell
- Input gate
- Forget gate
- Output gate

Solves vanishing gradient problem.

Allows long-term memory retention.

---

## 9. Gated Recurrent Unit (GRU)

Simplified version of LSTM:

- Fewer gates
- Fewer parameters
- Similar performance

---

## 10. Loss Functions

For sequence tasks:

- Cross-Entropy (language modeling)
- MSE (time series regression)

🔗 Related:
- [[Cross-Entropy]]
- [[Squared Error Loss]]

---

## 11. Applications

- Language modeling
- Machine translation
- Speech recognition
- Time series forecasting
- Sequence tagging

---

## 12. Bias–Variance Perspective

Simple RNN:
- High bias for long sequences.

LSTM/GRU:
- Lower bias
- Higher capacity
- Risk of overfitting

---

## 13. Comparison to CNN

| Aspect | CNN | RNN |
|--------|-----|-----|
| Structure | Spatial | Temporal |
| Weight sharing | Across space | Across time |
| Memory | No | Yes |
| Typical use | Images | Sequences |

---

## 14. Limitations

- Hard to train for long sequences.
- Sequential computation (slow).
- Gradients unstable.
- Replaced in many tasks by Transformers.

---

## 15. Relationship to Other Concepts

RNN connects strongly to:

- [[Multilayer Perceptron]]
- [[Convolutional Neural Networks]]
- [[Gradient Descent]]
- [[Cross-Entropy]]
- [[Time Series MOC]]
- [[Vanishing Gradient Problem]]

---

## 16. Why RNNs Matter

RNNs teach:

- Sequential modeling.
- Weight sharing across time.
- Memory in neural networks.
- Why gradient stability is critical.

They were foundational for:
> NLP and time-series modeling before Transformers.
