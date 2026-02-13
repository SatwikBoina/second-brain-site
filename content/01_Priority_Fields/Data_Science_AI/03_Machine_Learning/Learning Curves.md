---
type: concept
domain: machine-learning
category: model-diagnostics
status: evergreen
---

# Learning Curves

> Learning curves show how a model’s performance changes as the **training set size increases**, helping diagnose underfitting, overfitting, and data sufficiency.

---

## 1. Core Idea

A learning curve plots:

- **Training error**
- **Validation (or test) error**

as a function of **number of training samples**.

They answer questions like:
- Is my model too simple?
- Is my model overfitting?
- Will more data help?

---

## 2. What Learning Curves Plot

### Axes
- **X-axis** → Training set size
- **Y-axis** → Error (or negative score)

### Curves
- Training error curve
- Validation error curve

---

## 3. Ideal Learning Curve Shape

- Training error decreases and stabilizes
- Validation error decreases and approaches training error
- Small gap between curves

This indicates **good generalization**.

---

## 4. Underfitting Pattern (High Bias)

### Characteristics
- Training error: high
- Validation error: high
- Curves converge early
- Small gap, but poor performance

### Interpretation
- Model is too simple
- More data will NOT help

🔗 Related:
- [[Underfitting]]
- [[Model Complexity]]
- [[Bias–Variance Tradeoff]]

---

## 5. Overfitting Pattern (High Variance)

### Characteristics
- Training error: very low
- Validation error: high
- Large gap between curves
- Gap shrinks slowly with more data

### Interpretation
- Model too complex
- More data MAY help
- Regularization or simplification needed

🔗 Related:
- [[Overfitting]]
- [[Regularization — MOC]]

---

## 6. Effect of More Data

| Scenario | More Data Helps? |
|-------|----------------|
| High variance | ✅ Yes |
| High bias | ❌ No |
| Balanced model | ⚠️ Marginal |

More data mainly reduces **variance**, not bias.

---

## 7. Learning Curves vs Model Complexity

- Simple model → curves converge early (high error)
- Complex model → curves converge late (low training error)

Learning curves reveal whether complexity is appropriate.

🔗 See:
- [[Model Complexity]]

---

## 8. Algorithm-Wise Intuition

| Algorithm | Typical Curve Behavior |
|--------|------------------------|
| Linear Regression | Underfitting if features weak |
| Decision Tree | Overfitting without pruning |
| Random Forest | Smaller gap, stable |
| Gradient Boosting | Risk of overfitting |
| k-NN (small k) | Overfitting |
| k-NN (large k) | Underfitting |
| Naive Bayes | High bias, fast convergence |

---

## 9. How Learning Curves Are Used

Learning curves help decide:

- Add more data?
- Increase model complexity?
- Apply regularization?
- Engineer better features?

They guide **next actions**, not just diagnosis.

---

## 10. Relationship to Cross Validation

- Learning curves vary **data size**
- Cross-validation varies **data splits**

Both are complementary diagnostics.

🔗 Related:
- [[Cross Validation]]
- [[Model Diagnostics]]

---

## 11. Common Mistakes

- ❌ Interpreting curves with too few data points
- ❌ Using accuracy instead of error consistently
- ❌ Ignoring variance across folds

Learning curves should be **averaged across splits**.

---

## 12. Why Learning Curves Matter

Learning curves explain:

- Why adding data sometimes doesn’t help
- Why simple models plateau early
- Why complex models need regularization
- How to debug model behavior systematically

They turn **guesswork into diagnosis**.

---

## Usage Notes

- Link this note from:
  - Bias–Variance Tradeoff
  - Overfitting vs Underfitting
  - Model Complexity
  - Model Selection
- Do NOT duplicate explanations elsewhere
- Extend via backlinks, not edits
