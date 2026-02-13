---
type: concept
domain: machine-learning
category: tree-based-models
status: evergreen
---

# Cost-Complexity Pruning (CART)

> Cost-Complexity Pruning reduces overfitting in decision trees by penalizing tree size using a regularization parameter.

---

## 1. One-Line Intuition

> Balance training error and tree complexity using a penalty term.

---

## 2. Why Cost-Complexity Pruning Exists

Fully grown trees:

- Minimize training error
- Overfit noise
- Have high variance

Instead of just limiting depth arbitrarily, CART uses:

> A formal objective with complexity penalty.

🔗 Related:
- [[Pruning]]
- [[Tree Depth]]

---

## 3. Core Objective Function

\[
R_\alpha(T) = R(T) + \alpha |T|
\]

Where:

- \(R(T)\) = empirical error (impurity or misclassification error)
- \(|T|\) = number of leaf nodes
- \(\alpha\) = complexity penalty parameter

---

## 4. Interpretation of α (Alpha)

- α = 0 → no penalty → full tree
- Small α → slightly pruned tree
- Large α → aggressively pruned tree

Alpha controls:

> Tradeoff between fit and simplicity.

---

## 5. Bias–Variance Perspective

Small α:

- Low bias
- High variance

Large α:

- Higher bias
- Lower variance

Alpha tunes bias–variance balance.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 6. How the Algorithm Works

Step 1:
- Grow a full tree.

Step 2:
- Compute “weakest link” subtree.
- Identify branch whose removal increases error least per leaf removed.

Step 3:
- Remove that branch.

Step 4:
- Repeat until only root remains.

This produces:
> A sequence of nested subtrees.

---

## 7. Effective Alpha for a Node

For each internal node t:

\[
\alpha_t = \frac{R(t) - R(T_t)}{|T_t| - 1}
\]

Where:

- \(R(t)\) = error if node becomes leaf
- \(R(T_t)\) = error of subtree
- \(|T_t|\) = number of leaves in subtree

Smallest α_t gets pruned first.

---

## 8. Model Selection

Once sequence of pruned trees is created:

- Use cross-validation
- Select α giving lowest validation error

This avoids overfitting.

🔗 Related:
- [[Model Selection]]
- [[Cross Validation]]

---

## 9. Geometric Interpretation

Without pruning:
- Decision boundary highly fragmented.

With increasing α:
- Boundaries become smoother.
- Regions merge.
- Model simplifies.

---

## 10. Cost-Complexity vs Pre-Pruning

| Aspect | Pre-Pruning | Cost-Complexity |
|----------|--------------|----------------|
| When applied | During growth | After full growth |
| Flexibility | Limited | More principled |
| Risk | Underfitting | Better tradeoff control |
| Theoretical basis | Heuristic | Regularized objective |

Cost-complexity is more formal.

---

## 11. Regularization Perspective

Cost-Complexity is equivalent to:

\[
\text{Loss} + \lambda \times \text{Model Size}
\]

Similar to:

- L1 regularization
- L2 regularization
- AIC / BIC penalties

It penalizes structural complexity.

🔗 Related:
- [[Regularization — MOC]]
- [[AIC]]
- [[BIC]]

---

## 12. Computational Considerations

- Full tree must be built first.
- Pruning is relatively efficient.
- Cross-validation required for α selection.

---

## 13. When It Works Best

- Small to medium datasets
- Noisy data
- Deep trees
- Single decision tree models

---

## 14. When It’s Less Important

- Random Forest (variance reduced by bagging)
- Boosting (shallow trees used)
- Very large datasets

---

## 15. Relationship to Other Concepts

Cost-Complexity Pruning connects strongly to:

- [[Decision Tree Classifier]]
- [[Tree Depth]]
- [[Pruning]]
- [[Bias–Variance Tradeoff]]
- [[Model Selection]]
- [[Regularization — MOC]]

---

## 16. Why Cost-Complexity Pruning Matters

It teaches:

- Structural regularization
- Formal tradeoff control
- Model selection via penalty
- How tree size impacts generalization

It is the tree equivalent of:
> L2 regularization in linear models.
