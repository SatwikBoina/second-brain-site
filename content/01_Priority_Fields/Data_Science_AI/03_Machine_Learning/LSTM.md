---
type: zettel
domain: machine-learning
category: deep-learning
topic: long-short-term-memory
status: evergreen
---

# Long Short-Term Memory (LSTM)

> LSTM is a special type of Recurrent Neural Network (RNN) designed to capture long-term dependencies by controlling information flow using gating mechanisms.

---

## 1. One-Line Intuition

> LSTM remembers what is important and forgets what is not.

---

## 2. Why LSTM Was Created

Standard RNN:

\[
h_t = \tanh(W_x x_t + W_h h_{t-1})
\]

Problem:
- Repeated multiplication of weights
- Gradients vanish or explode
- Hard to learn long-term dependencies

LSTM introduces controlled memory.

🔗 Related:
- [[Recurrent Neural Networks]]
- [[Vanishing Gradient Problem]]

---

## 3. Core Components

An LSTM cell has:

1. Cell state \(C_t\) (long-term memory)
2. Hidden state \(h_t\)
3. Three gates:
   - Forget gate
   - Input gate
   - Output gate

---

## 4. LSTM Equations

### 4.1 Forget Gate

\[
f_t = \sigma(W_f [h_{t-1}, x_t] + b_f)
\]

Decides what to forget from previous memory.

---

### 4.2 Input Gate

\[
i_t = \sigma(W_i [h_{t-1}, x_t] + b_i)
\]

\[
\tilde{C}_t = \tanh(W_c [h_{t-1}, x_t] + b_c)
\]

Decides what new information to store.

---

### 4.3 Cell State Update

\[
C_t = f_t \odot C_{t-1} + i_t \odot \tilde{C}_t
\]

Key idea:
- Additive memory update
- Prevents vanishing gradient

---

### 4.4 Output Gate

\[
o_t = \sigma(W_o [h_{t-1}, x_t] + b_o)
\]

\[
h_t = o_t \odot \tanh(C_t)
\]

Controls what to expose as output.

---

## 5. Why LSTM Solves Vanishing Gradient

Key difference:

Vanilla RNN:
- Multiplicative memory updates

LSTM:
- Additive cell state updates

This preserves gradient flow over long sequences.

---

## 6. Intuition Behind the Gates

Forget gate:
- Remove irrelevant past information.

Input gate:
- Decide what new info matters.

Output gate:
- Decide what to reveal externally.

Memory cell:
- Acts like a conveyor belt.

---

## 7. Applications

- Language modeling
- Machine translation
- Speech recognition
- Time-series forecasting
- Text generation

---

## 8. Bias–Variance Perspective

Vanilla RNN:
- High bias for long sequences.

LSTM:
- Lower bias (captures long dependencies)
- Higher capacity → risk of overfitting

Requires regularization.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 9. Comparison: RNN vs LSTM

| Aspect | Vanilla RNN | LSTM |
|--------|-------------|------|
| Long-term memory | Poor | Strong |
| Vanishing gradients | Severe | Reduced |
| Complexity | Simple | More complex |
| Parameters | Fewer | More |

---

## 10. LSTM vs GRU

GRU:
- Fewer gates
- Simpler
- Often similar performance

LSTM:
- More expressive
- More control over memory

---

## 11. Training

Uses:

- Backpropagation Through Time (BPTT)
- Gradient descent
- Cross-entropy or MSE loss

🔗 Related:
- [[Gradient Descent]]
- [[Cross-Entropy]]

---

## 12. Limitations

- Sequential computation (slow)
- Computationally heavy
- Struggles with very long sequences
- Replaced in many NLP tasks by Transformers

---

## 13. Relationship to Other Concepts

LSTM connects strongly to:

- [[Recurrent Neural Networks]]
- [[Vanishing Gradient Problem]]
- [[Gradient Descent]]
- [[Time Series MOC]]
- [[Cross-Entropy]]
- [[Multilayer Perceptron]]

---

## 14. Why LSTM Matters

LSTM teaches:

- Controlled information flow
- Gating mechanisms
- Long-term memory modeling
- How architecture fixes optimization problems

It was the backbone of:
> Deep NLP and sequence modeling before Transformers.
