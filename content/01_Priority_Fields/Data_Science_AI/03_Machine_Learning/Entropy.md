---
type: concept
domain: machine-learning
category: information-theory
status: evergreen
---

# Entropy

> Entropy measures the amount of uncertainty or disorder in a probability distribution.

---

## 1. One-Line Intuition

> Entropy tells us how uncertain we are about the class label.

More mixed → higher entropy  
Pure → zero entropy  

---

## 2. Mathematical Definition

For a discrete distribution:

\[
H(X) = - \sum_{k=1}^{K} p_k \log_2(p_k)
\]

Where:
- \(p_k\) = probability of class k
- Log base 2 → entropy measured in bits

---

## 3. Binary Classification Example

Suppose:

- 70% Class A
- 30% Class B

\[
H = - (0.7 \log_2 0.7 + 0.3 \log_2 0.3)
\approx 0.88
\]

If node is pure:

\[
H = - (1 \log_2 1) = 0
\]

Maximum entropy occurs at:

\[
p = 0.5
\]

\[
H = 1
\]

---

## 4. Interpretation

- H = 0 → No uncertainty (pure node)
- H is maximal → Maximum disorder
- Higher entropy → More class mixing

Binary entropy range:
- 0 to 1

---

## 5. Entropy in Decision Trees

Decision trees use:

> Information Gain

Information Gain:

\[
IG = H(parent) - \sum \left( \frac{n_i}{n} H(child_i) \right)
\]

Choose split that maximizes IG.

🔗 Related:
- [[Decision Tree Classifier]]
- [[Gini Impurity]]

---

## 6. Entropy vs Gini

| Aspect | Entropy | Gini |
|----------|----------|-------|
| Formula | -Σ p log p | 1 - Σ p² |
| Range (binary) | 0–1 | 0–0.5 |
| Theoretical basis | Information Theory | Probability |
| Computational cost | Higher | Lower |

In practice:
- Often similar results.

Entropy is slightly more sensitive to class imbalance.

---

## 7. Why Logarithm?

Logarithm gives entropy properties:

- Additivity
- Sensitivity to rare events
- Theoretical consistency

Entropy measures:
> Expected information content.

---

## 8. Information-Theoretic Interpretation

Entropy measures:

- Expected number of bits needed to encode outcome.
- Average surprise.

If event probability is low:
- Surprise is high.

\[
Surprise = -\log(p)
\]

Entropy is average surprise.

---

## 9. Entropy and Cross-Entropy

Cross-Entropy loss:

\[
-\sum y \log(\hat{y})
\]

Used in:

- Logistic Regression
- Neural Networks
- Softmax classifiers

Entropy connects directly to classification loss.

🔗 Related:
- [[Loss Functions — MOC]]
- [[Logistic Regression]]
- [[Neural Network Classifier]]

---

## 10. Entropy and KL Divergence

KL Divergence:

\[
D_{KL}(P||Q) = \sum P(x) \log \frac{P(x)}{Q(x)}
\]

Measures difference between distributions.

Entropy is part of KL formulation.

🔗 Related:
- [[Information Theory — MOC]]

---

## 11. Multi-Class Entropy

For K classes:

Maximum entropy when:

\[
p_k = \frac{1}{K}
\]

Then:

\[
H = \log_2(K)
\]

More classes → higher maximum entropy.

---

## 12. Entropy and Bias–Variance

Pure nodes:
- Low entropy
- Low bias

Deep trees:
- Reduce entropy aggressively
- Risk high variance

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 13. Geometric Interpretation

Entropy encourages splits that:

- Reduce uncertainty fastest
- Separate classes cleanly
- Improve information gain

It measures class distribution disorder.

---

## 14. Strengths

- Strong theoretical foundation
- Sensitive to minority class
- Information-theoretic meaning
- Widely used in ML

---

## 15. Limitations

- Slightly slower than Gini
- Can favor splits with many small partitions
- Requires log computation

---

## 16. Relationship to Other Concepts

Entropy connects strongly to:

- [[Information Theory — MOC]]
- [[Decision Tree Classifier]]
- [[Gini Impurity]]
- [[Loss Functions — MOC]]
- [[Cross Entropy]]
- [[Logistic Regression]]

---

## 17. Why Entropy Matters

Entropy teaches:

- How uncertainty is measured
- Why splits reduce disorder
- Why log-loss is natural for classification
- Why information theory underpins ML

It is the foundation of:
> Information Gain and Cross-Entropy Loss.
