

**Type:** Concept  
**Domain:** Machine Learning  
**Status:** Evergreen  

---

## 1. Core Definition

**Underfitting** occurs when a model is **too simple** to capture the true relationship in the data.
It is mainly caused by **high bias**.

---

## 2. Why Underfitting Happens

Underfitting happens when the model:

- Makes strong assumptions about the data
- Ignores important patterns

This results in **systematic error**.

---

## 3. Bias Perspective

| Aspect | Underfitting |
|------|-------------|
| Bias | High |
| Variance | Low |
| Model complexity | Too low |
| Error type | Assumption error |
| Learning behavior | Misses signal |

---

## 4. Common Examples

- Linear Regression on non-linear data
- Logistic Regression with poor features
- k-NN with very large *k*
- Shallow decision trees

---

## 5. How to Fix Underfitting

| Action | Effect |
|------|-------|
| Increase model complexity | Reduce bias |
| Add better features | Capture true patterns |
| Reduce regularization | Allow flexibility |
| Use non-linear models | Improve fit |

---

### Related Notes
- [[Bias–Variance Tradeoff]]
- [[Bias]]
- [[Model Complexity]]
