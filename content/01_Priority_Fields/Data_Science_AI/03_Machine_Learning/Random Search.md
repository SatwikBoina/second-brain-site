---
type: concept
domain: machine-learning
category: hyperparameter-tuning
status: evergreen
---

# Random Search

> Random Search is a hyperparameter optimization technique that samples **random combinations** of hyperparameters from predefined distributions.

---

## 1. Core Idea

Instead of exhaustively trying every combination (Grid Search), Random Search:

- Randomly samples configurations
- Explores the search space more efficiently
- Focuses on important dimensions faster

---

## 2. Why Random Search Works Better Than Grid Search

Key insight:

> Only a few hyperparameters usually matter.

Grid Search wastes effort on unimportant dimensions.  
Random Search spreads trials across the space.

---

## 3. How Random Search Works (Methodology)

1. Define hyperparameter distributions  
2. Randomly sample combinations  
3. Train model using CV or validation set  
4. Track best-performing configuration  
5. Stop after fixed budget

---

## 4. Search Space Definition

Random Search requires:
- Ranges for continuous parameters
- Discrete sets for categorical parameters

Examples:
- Learning rate ~ log-uniform
- Regularization ~ log-uniform
- Tree depth ~ integer range

🔗 Related:
- [[Hyperparameter Tuning — MOC]]

---

## 5. Random Search + Cross Validation

Random Search is usually combined with:

- k-fold CV
- Stratified k-fold (classification)

🔗 Related:
- [[Cross Validation]]
- [[Stratified Sampling]]

---

## 6. Bias–Variance Perspective

Random Search helps:
- Tune regularization
- Control model complexity
- Balance bias and variance

But it does **not prevent overfitting** by itself.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 7. Computational Characteristics

| Aspect | Random Search |
|-----|---------------|
| Parallelizable | Yes |
| Anytime algorithm | Yes |
| Scales to many params | Yes |
| Guarantees optimal | No |

---

## 8. Random Search vs Grid Search

| Aspect | Random Search | Grid Search |
|-----|--------------|-------------|
| Coverage | Stochastic | Exhaustive |
| Efficiency | High | Low |
| Scaling | Good | Poor |
| Early stopping | Easy | Hard |

🔗 Related:
- [[Grid Search]]

---

## 9. When Random Search Works Best

- Large hyperparameter spaces
- Continuous parameters
- Expensive models
- Boosting models
- Neural networks

---

## 10. When Random Search Is Less Ideal

- Very small search spaces
- Final fine-grained tuning
- When strict reproducibility is required

---

## 11. Random Search and Data Leakage ⚠️

❌ Wrong:
- Using test set during search

✅ Correct:
1. Use CV or validation set
2. Select best configuration
3. Evaluate once on test set

🔗 Related:
- [[Data Leakage]]
- [[Train–Test Split]]

---

## 12. Random Search and Early Stopping

Random Search pairs well with:
- Early stopping
- Budget-based termination
- Adaptive stopping rules

🔗 Related:
- [[Early Stopping]]

---

## 13. Common Mistakes

- ❌ Sampling from poor distributions  
- ❌ Too few iterations  
- ❌ Ignoring scale (linear vs log)  
- ❌ Tuning everything at once  

Random Search needs **thoughtful bounds**.

---

## 14. Why Random Search Matters

Random Search explains:
- Why simple tuning beats brute force
- Why boosting models benefit from randomness
- Why tuning strategy matters as much as model choice

It is the **default choice for practical hyperparameter tuning**.

---

## Usage Notes

- Prefer Random Search over Grid Search for:
  - Large spaces
  - Continuous parameters
- Link this note from:
  - Hyperparameter Tuning — MOC
  - Model Selection
