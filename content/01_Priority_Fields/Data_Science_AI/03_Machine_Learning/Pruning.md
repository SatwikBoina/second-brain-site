---
type: concept
domain: machine-learning
category: tree-based-models
status: evergreen
---

# Pruning (Decision Trees)

> Pruning is the process of reducing the size of a decision tree by removing branches that contribute little to predictive performance.

---

## 1. One-Line Intuition

> Cut off branches that memorize noise.

---

## 2. Why Pruning Is Needed

Fully grown trees:

- Achieve near-zero training error
- Overfit noise
- Have high variance
- Generalize poorly

Pruning simplifies the tree to improve test performance.

🔗 Related:
- [[Tree Depth]]
- [[Bias–Variance Tradeoff]]

---

## 3. Two Types of Pruning

---

## 3.1 Pre-Pruning (Early Stopping)

Stop tree growth early using constraints such as:

- Maximum depth
- Minimum samples per split
- Minimum samples per leaf
- Minimum impurity decrease

Advantages:
- Faster
- Simpler

Risk:
- May stop too early (high bias)

---

## 3.2 Post-Pruning (Cost-Complexity Pruning)

Grow full tree first.
Then remove branches based on evaluation.

More principled approach.

---

## 4. Cost-Complexity Pruning (CART)

Objective:

\[
R_\alpha(T) = R(T) + \alpha |T|
\]

Where:

- \(R(T)\) = training error
- \(|T|\) = number of leaves
- \(\alpha\) = complexity penalty

Higher α:
- Stronger penalty
- Smaller tree

---

## 5. Geometric Interpretation

Unpruned tree:

- Many small partitions
- Jagged decision boundary

Pruned tree:

- Larger regions
- Smoother boundary
- Better generalization

---

## 6. Bias–Variance Perspective

Unpruned tree:

- Low bias
- High variance

Pruned tree:

- Slightly higher bias
- Lower variance
- Often lower total error

Pruning balances bias–variance.

🔗 Related:
- [[Variance Reduction]]

---

## 7. Validation-Based Pruning

Common approach:

1. Split data into train + validation.
2. Grow full tree.
3. Iteratively remove branches.
4. Keep structure with lowest validation error.

---

## 8. Reduced Error Pruning

Procedure:

- Replace subtree with leaf.
- Check if validation error improves.
- Keep change if performance improves.

Simple but effective.

---

## 9. When Pruning Helps Most

- Small datasets
- Noisy labels
- Deep trees
- High feature count

---

## 10. When Pruning Is Less Important

- Random Forest (bagging reduces variance)
- Boosting (uses shallow trees)
- Large datasets

Ensembles often reduce need for pruning.

🔗 Related:
- [[Random Forest Classifier]]
- [[Boosting]]

---

## 11. Pruning vs Limiting Depth

| Aspect | Limiting Depth | Post-Pruning |
|----------|---------------|--------------|
| When applied | Before growth | After growth |
| Risk | Underfitting | More controlled |
| Flexibility | Less | More |
| Computation | Faster | Slightly higher |

Post-pruning is more adaptive.

---

## 12. Computational Impact

Pruning:

- Reduces model size
- Reduces prediction time
- Improves interpretability

---

## 13. Interpretability Benefit

Smaller tree:

- Fewer rules
- Easier to visualize
- Easier to explain

Pruning improves explainability.

---

## 14. Failure Modes

- ❌ Too aggressive pruning → underfitting
- ❌ Poor validation split
- ❌ Noisy validation set
- ❌ Over-penalizing complexity

Proper tuning of α is critical.

---

## 15. Relationship to Other Concepts

Pruning connects strongly to:

- [[Decision Tree Classifier]]
- [[Tree Depth]]
- [[Gini Impurity]]
- [[Information Gain]]
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 16. Why Pruning Matters

Pruning teaches:

- Overfitting control
- Structural regularization
- Complexity penalization
- Tradeoff between fit and simplicity

It is the tree equivalent of:
> Regularization in linear models.
