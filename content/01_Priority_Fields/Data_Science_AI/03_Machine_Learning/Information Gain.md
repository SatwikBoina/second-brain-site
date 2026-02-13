---
type: concept
domain: machine-learning
category: information-theory
status: evergreen
---

# Information Gain

> Information Gain measures how much uncertainty (entropy) is reduced after splitting a dataset based on a feature.

---

## 1. One-Line Intuition

> A good split is one that reduces uncertainty the most.

---

## 2. Core Formula

\[
IG = H(\text{parent}) - \sum_{i=1}^{k} \frac{n_i}{n} H(\text{child}_i)
\]

Where:

- \(H\) = entropy
- \(n_i\) = number of samples in child node
- \(n\) = total samples

Information Gain = reduction in entropy.

---

## 3. Step-by-Step Example (Binary Case)

Suppose parent node:

- 50% Class A
- 50% Class B

\[
H_{parent} = 1
\]

Now split into:

Left child:
- 80% A
- 20% B
Entropy ≈ 0.72

Right child:
- 20% A
- 80% B
Entropy ≈ 0.72

Weighted entropy:

\[
0.5(0.72) + 0.5(0.72) = 0.72
\]

Information Gain:

\[
IG = 1 - 0.72 = 0.28
\]

The split reduced uncertainty by 0.28 bits.

---

## 4. Interpretation

- High IG → strong class separation
- Low IG → weak split
- IG = 0 → no improvement

Information Gain quantifies split quality.

---

## 5. Why It Works

Entropy measures disorder.

Information Gain measures:
> How much order is introduced by the split.

The tree greedily selects:
- The split with maximum IG.

🔗 Related:
- [[Decision Tree Classifier]]
- [[Entropy]]

---

## 6. Information Gain vs Gini Gain

Information Gain:
- Based on entropy

Gini Gain:
- Based on Gini impurity

In practice:
- Similar performance
- Gini is slightly faster
- Entropy has stronger theoretical grounding

🔗 Related:
- [[Gini Impurity]]

---

## 7. Connection to Mutual Information

Information Gain is equivalent to:

\[
IG = I(Y; X)
\]

Mutual Information between:
- Target variable Y
- Feature X

It measures how much knowing X reduces uncertainty in Y.

🔗 Related:
- [[Information Theory — MOC]]

---

## 8. Information Gain Bias

Problem:

Information Gain favors:
- Features with many unique values.

Example:
- ID number feature (unique per sample)
→ Very high IG
→ Overfitting

---

## 9. Gain Ratio (C4.5)

Gain Ratio corrects bias:

\[
Gain\ Ratio = \frac{IG}{Split\ Information}
\]

Split Information measures entropy of split itself.

Used in:
- C4.5 algorithm

---

## 10. Information Gain in Feature Selection

IG can be used to:

- Rank features
- Select important predictors
- Reduce dimensionality

Common in:
- Text classification
- NLP

🔗 Related:
- [[Feature Selection]]
- [[Natural Language Processing MOC]]

---

## 11. Multi-Class Case

If K classes:

Maximum entropy:

\[
H = \log_2(K)
\]

Information Gain generalizes naturally.

---

## 12. Geometric Interpretation

Information Gain:

- Encourages splits that separate classes cleanly.
- Prefers partitions that create pure nodes.

It reduces uncertainty at each node.

---

## 13. Bias–Variance Perspective

High IG splits:

- Create purer nodes
- Reduce bias
- Risk deeper trees
- Increase variance

Pruning controls variance.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 14. Strengths

- Theoretically grounded
- Interpretable
- Effective for classification
- Based on solid information theory

---

## 15. Limitations

- Biased toward many-valued features
- Requires entropy computation
- Greedy (local optimum)

---

## 16. Relationship to Other Concepts

Information Gain connects strongly to:

- [[Entropy]]
- [[Gini Impurity]]
- [[Decision Tree Classifier]]
- [[Feature Selection]]
- [[Information Theory — MOC]]
- [[Bias–Variance Tradeoff]]

---

## 17. Why Information Gain Matters

Information Gain teaches:

- How trees measure split usefulness
- How entropy connects to learning
- Why feature splits reduce uncertainty
- Why decision trees are greedy information optimizers

It is the operational bridge between:
> Information theory and decision tree learning.
