---
type: concept
domain: machine-learning
category: tree-based-models
status: evergreen
---

# Gini Impurity

> Gini Impurity measures how often a randomly chosen element from a node would be incorrectly classified if labeled according to the class distribution in that node.

---

## 1. One-Line Intuition

> Gini measures how “mixed” a node is.

Pure node → Gini = 0  
Mixed node → Gini increases  

---

## 2. Mathematical Definition

For a node with K classes:

\[
Gini = 1 - \sum_{k=1}^{K} p_k^2
\]

Where:
- \( p_k \) = proportion of class k in the node

---

## 3. Binary Classification Example

Suppose:

- 70% Class A
- 30% Class B

\[
Gini = 1 - (0.7^2 + 0.3^2)
= 1 - (0.49 + 0.09)
= 1 - 0.58
= 0.42
\]

If node is pure:

\[
Gini = 1 - (1^2) = 0
\]

Maximum impurity occurs at:

\[
p = 0.5
\]

\[
Gini = 1 - (0.5^2 + 0.5^2) = 0.5
\]

---

## 4. Interpretation

- Low Gini → node mostly one class
- High Gini → classes mixed
- Zero Gini → perfect purity

Range (binary):
- 0 to 0.5

---

## 5. Why Decision Trees Use Gini

When splitting a node:

1. Try possible splits.
2. Compute Gini impurity for each split.
3. Choose split that reduces impurity the most.

This is called:

> Gini Gain

---

## 6. Gini Gain

For a split:

\[
\text{Gain} = Gini_{parent} - \sum \left( \frac{n_i}{n} \times Gini_i \right)
\]

Where:
- \(n_i\) = size of child node
- \(n\) = size of parent

Tree chooses split that maximizes gain.

---

## 7. Geometric Interpretation

Gini measures:

- Probability of misclassification
- Degree of class mixing

It encourages splits that:

- Separate classes cleanly
- Reduce uncertainty

---

## 8. Gini vs Entropy

Entropy:

\[
Entropy = - \sum p_k \log(p_k)
\]

Comparison:

| Aspect | Gini | Entropy |
|----------|------|---------|
| Computational cost | Lower | Higher |
| Range (binary) | 0–0.5 | 0–1 |
| Behavior | Slightly favors larger classes | More sensitive to minority class |

In practice:
- Results are usually similar.

🔗 Related:
- [[Information Theory — MOC]]
- [[Decision Tree Classifier]]

---

## 9. Gini vs Misclassification Error

Misclassification Error:

\[
1 - \max(p_k)
\]

Less sensitive than Gini.

Trees rarely use it for splitting.

---

## 10. Why Gini Works Well

Gini:

- Is differentiable
- Penalizes impurity smoothly
- Encourages confident splits
- Computationally efficient

---

## 11. Gini in Random Forest

Random Forest:

- Uses Gini impurity at each split
- Combined with feature randomness
- Leads to strong classification performance

🔗 Related:
- [[Random Forest Classifier]]
- [[Bagging]]

---

## 12. Bias–Variance Perspective

Deep trees:

- Low Gini in leaves
- Low bias
- High variance

Pruning or ensemble methods:
- Reduce variance

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 13. Multi-Class Case

If K classes:

\[
Gini = 1 - \sum_{k=1}^{K} p_k^2
\]

Maximum impurity occurs when:

\[
p_k = \frac{1}{K}
\]

---

## 14. Strengths

- Fast to compute
- Works well in practice
- Stable
- Smooth impurity measure

---

## 15. Limitations

- Slight bias toward majority class
- Does not incorporate cost-sensitive weighting unless modified
- Only applicable to classification

---

## 16. Relationship to Other Concepts

Gini impurity connects strongly to:

- [[Decision Tree Classifier]]
- [[Random Forest Classifier]]
- [[Bagging]]
- [[Information Theory — MOC]]
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 17. Why Gini Impurity Matters

Gini impurity teaches:

- How trees measure split quality
- How impurity relates to probability
- How local decisions shape global model
- Why trees are greedy learners

It is the core impurity measure behind:
> Decision Trees and Random Forests.
