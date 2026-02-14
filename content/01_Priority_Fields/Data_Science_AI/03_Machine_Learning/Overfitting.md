
**Type:** Concept  
**Domain:** Machine Learning  
**Status:** Evergreen  

---

## 1. Core Definition

**Overfitting** occurs when a model learns the **noise in the training data** instead of the true signal.

It is mainly caused by **high variance**.

---

## 2. Why Overfitting Happens

Overfitting happens when the model:

- Is overly complex
- Memorizes training data
- Becomes sensitive to small data fluctuations

This results in **poor generalization**.

---

## 3. Variance Perspective

| Aspect | Overfitting |
|------|------------|
| Bias | Low |
| Variance | High |
| Model complexity | Too high |
| Error type | Noise sensitivity |
| Learning behavior | Learns noise |

---

## 4. Common Examples

- Deep decision trees without pruning
- High-degree polynomial regression
- k-NN with very small *k*
- Models trained on very small datasets

---

## 5. How to Fix Overfitting

| Action | Effect |
|------|-------|
| Collect more data | Reduce variance |
| Apply regularization | Constrain model |
| Simplify model | Reduce complexity |
| Use cross-validation | Detect overfitting |

---

### Related Notes
- [[Bias–Variance Tradeoff]]
- [[Variance]]
- [[Model Complexity]]
