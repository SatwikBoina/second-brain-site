---
type: zettel
domain: machine-learning
category: deep-learning
topic: transformers
status: evergreen
---

# Transformers

> Transformers are neural network architectures that model relationships in sequential data using self-attention instead of recurrence or convolution.

---

## 1. One-Line Intuition

> Instead of processing tokens one by one, let every token directly attend to every other token.

---

## 2. Why Transformers Were Created

Problems with RNNs / LSTMs:

- Sequential computation (slow).
- Hard to parallelize.
- Difficulty modeling very long-range dependencies.
- Vanishing gradients.

Transformers solve this using:

- Self-attention
- Parallel computation
- Direct long-range interaction

🔗 Related:
- [[Recurrent Neural Networks]]
- [[Long Short-Term Memory (LSTM)]]

---

## 3. Core Idea: Self-Attention

For each token:

- Compute how much attention to give to every other token.

Mathematically:

\[
Attention(Q, K, V) =
\text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V
\]

Where:

- Q = Query
- K = Key
- V = Value
- \(d_k\) = dimension scaling factor

Each token produces:
- A weighted sum of all other tokens.

---

## 4. Transformer Architecture

Each Transformer block contains:

1. Multi-Head Self-Attention
2. Add & Layer Normalization
3. Feedforward Neural Network
4. Add & Layer Normalization

Stack multiple blocks.

---

## 5. Multi-Head Attention

Instead of one attention mechanism:

- Use multiple attention heads.
- Each head learns different relationships.

This increases representation power.

---

## 6. Positional Encoding

Since Transformers do not use recurrence:

- They need positional information.

Positional encodings:

- Added to embeddings.
- Encode token order.

---

## 7. Encoder vs Decoder

Original Transformer has:

Encoder:
- Processes input sequence.

Decoder:
- Generates output sequence.
- Uses masked attention.

Used in:
- Machine translation.

---

## 8. Why Transformers Are Powerful

- Parallel computation.
- Direct long-range dependency modeling.
- Scales extremely well.
- Works well with massive data.

---

## 9. Loss Functions

For language modeling:

- Cross-Entropy Loss
- Softmax output

🔗 Related:
- [[Cross-Entropy]]
- [[Softmax Function]]

---

## 10. Bias–Variance Perspective

Transformers:

- Extremely low bias (high capacity).
- Very high variance risk.
- Require huge data.
- Regularization and scaling critical.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 11. Computational Complexity

Self-attention:

\[
O(n^2)
\]

Where n = sequence length.

Limitation:
- Expensive for long sequences.

Many efficient variants proposed.

---

## 12. Applications

- Large Language Models (GPT)
- BERT
- Vision Transformers (ViT)
- Speech recognition
- Multimodal models

---

## 13. Comparison: RNN vs Transformer

| Aspect | RNN/LSTM | Transformer |
|--------|----------|------------|
| Sequential | Yes | No |
| Parallelizable | No | Yes |
| Long-range modeling | Indirect | Direct |
| Training speed | Slower | Faster |

---

## 14. Relationship to Other Concepts

Transformers connect strongly to:

- [[Attention Mechanism]]
- [[Multilayer Perceptron]]
- [[Cross-Entropy]]
- [[Gradient Descent]]
- [[Bias–Variance Tradeoff]]
- [[Natural Language Processing MOC]]

---

## 15. Why Transformers Matter

Transformers teach:

- Attention-based modeling.
- Parallel sequence learning.
- Scalability in deep learning.
- Architecture-driven breakthroughs.

They are the foundation of:
> Modern AI systems and Large Language Models.
