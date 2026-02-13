---
type: concept
domain: machine-learning
category: model-evaluation
status: evergreen
---

# Overfitting vs Underfitting

> The distinction between models that **fail to learn enough** from data (underfitting) and models that **learn too much noise** from data (overfitting).

---

## 1. Core Idea

A model can make errors because it is:

- **Too simple** → underfitting  
- **Too complex** → overfitting  

The goal is to learn the **true signal**, not noise.

---

## 2. Underfitting

**Underfitting** occurs when a model is unable to capture the underlying pattern in the data.

### Characteristics
- High training error
- High validation error
- Model too simple

### Common Causes
- Inadequate model complexity
- Poor feature engineering
- Excessive regularization
- Insufficient training time

### Examples
- Linear Regression on non-linear data
- k-NN with very large k

🔗 Related:
- [[High Bias]]
- [[Linear Models — MOC]]

---

## 3. Overfitting

**Overfitting** occurs when a model fits the training data too closely, including noise.

### Characteristics
- Very low training error
- High validation/test error
- Model too complex

### Common Causes
- Excessive model complexity
- Small training dataset
- No regularization
- Data leakage

### Examples
- Deep Decision Tree without pruning
- k-NN with very small k

🔗 Related:
- [[High Variance]]
- [[Tree-Based Models — MOC]]

---

## 4. Visual Intuition

| Model Type | Training Error | Validation Error |
|----------|---------------|------------------|
| Underfit | High | High |
| Good Fit | Low | Low |
| Overfit | Very Low | High |

🔗 Tool:
- [[Learning Curves]]

---

## 5. Relationship to Bias–Variance Tradeoff

- Underfitting ↔ **High Bias**
- Overfitting ↔ **High Variance**

🔗 Core concept:
- [[Bias–Variance Tradeoff]]

---

## 6. How to Detect

Common diagnostic signals:

- Large gap between training and validation error → overfitting
- Both errors high → underfitting

Tools:
- Cross-validation
- Learning curves

🔗 Related:
- [[Cross Validation]]
- [[Model Diagnostics]]

---

## 7. How to Fix Underfitting

- Increase model complexity
- Add better features
- Reduce regularization
- Train longer
- Use non-linear models

---

## 8. How to Fix Overfitting

- Simplify the model
- Add regularization
- Increase training data
- Use ensembling
- Early stopping
- Fix data leakage

🔗 Related:
- [[Regularization — MOC]]
- [[Early Stopping]]
- [[Ensemble Learning]]

---

## 9. Algorithm-Wise Intuition

| Algorithm | Common Risk |
|--------|-------------|
| Linear Regression | Underfitting |
| Polynomial Regression (high degree) | Overfitting |
| Decision Tree | Overfitting |
| Random Forest | Balanced |
| Gradient Boosting | Overfitting (if untuned) |
| k-NN (small k) | Overfitting |
| k-NN (large k) | Underfitting |
| Naive Bayes | Underfitting |

---

## 10. Role of Data Size

- Small datasets → overfitting risk
- Large datasets → underfitting risk if model is too simple

More data usually reduces overfitting, not underfitting.

---

## 11. Common Misconceptions

- ❌ High training accuracy means good model  
- ❌ Overfitting only happens in complex models  
- ❌ Regularization always improves performance  

Context always matters.

---

## 12. Why This Concept Matters

Overfitting vs underfitting explains:

- Why validation is critical
- Why regularization exists
- Why ensembles work
- Why model selection matters

This concept is **central to practical ML**.

---

## Usage Notes

- Link this note from all algorithms
- Do NOT duplicate explanations elsewhere
- Extend via backlinks, not by editing
