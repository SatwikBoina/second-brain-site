---
type: concept
domain: machine-learning
category: model-evaluation
status: evergreen
---

# Bias–Variance Tradeoff

> The fundamental tradeoff between a model’s ability to **fit training data** (bias) and its **sensitivity to data fluctuations** (variance).

---

## 1. Core Idea

Any supervised learning model makes errors due to:

- **Bias** → errors from incorrect assumptions
- **Variance** → errors from sensitivity to training data

Improving one often worsens the other.

---

## 2. Bias

**Bias** measures how much the model’s predictions differ from the true underlying function *on average*.

### Characteristics
- High bias → underfitting
- Model too simple
- Misses important patterns

### Examples
- Linear Regression on non-linear data
- Logistic Regression with poor features

🔗 Related:
- [[Underfitting]]
- [[Linear Models — MOC]]

---

## 3. Variance

**Variance** measures how much model predictions change when trained on different datasets.

### Characteristics
- High variance → overfitting
- Model too complex
- Fits noise instead of signal

### Examples
- Decision Trees without pruning
- k-NN with very small k

🔗 Related:
- [[Overfitting]]
- [[Tree-Based Models — MOC]]

---

## 4. The Tradeoff

- Decreasing bias usually increases variance
- Decreasing variance usually increases bias
- Goal is **optimal balance**, not zero error

There is no universally best model — only best *for a dataset*.

---

## 5. Error Decomposition (Intuition)

Expected prediction error can be decomposed into:

- Bias²
- Variance
- Irreducible noise

🔗 Concept:
- [[Irreducible Error]]

---

## 6. How Model Complexity Affects the Tradeoff

| Model Complexity | Bias | Variance |
|-----------------|------|----------|
| Very simple | High | Low |
| Moderate | Balanced | Balanced |
| Very complex | Low | High |

🔗 Related:
- [[Model Complexity]]

---

## 7. Algorithm-Wise Intuition

| Algorithm | Bias | Variance |
|--------|------|----------|
| Linear Regression | High | Low |
| Polynomial Regression (high degree) | Low | High |
| Decision Tree | Low | High |
| Random Forest | Medium | Low |
| Gradient Boosting | Low | Medium |
| k-NN (small k) | Low | High |
| k-NN (large k) | High | Low |
| Naive Bayes | High | Very Low |

---

## 8. Controlling Bias–Variance

### Increase Bias / Reduce Variance
- Simpler models
- Regularization
- Fewer features
- More data

### Reduce Bias / Increase Variance
- More complex models
- Feature engineering
- Deeper trees
- Non-linear kernels

🔗 Related:
- [[Regularization — MOC]]
- [[Feature Engineering]]

---

## 9. Role of Data Size

- Small datasets → variance dominates
- Large datasets → bias dominates

Adding data usually reduces variance, not bias.

---

## 10. Diagnostic Tools

- Learning curves
- Cross-validation
- Training vs validation error comparison

🔗 Related:
- [[Learning Curves]]
- [[Cross Validation]]

---

## 11. Common Misconceptions

- ❌ High accuracy means low bias & variance  
- ❌ Overfitting = bad model always  
- ❌ One model fits all datasets  

The tradeoff is **context-dependent**.

---

## 12. Why This Concept Matters

Bias–variance tradeoff explains:

- Why ensembles work
- Why regularization helps
- Why more data matters
- Why simpler models sometimes win

This is the **mental backbone of model selection**.

---

## Usage Notes

- This note should be linked by **every algorithm**
- Do NOT duplicate this explanation elsewhere
- Extend only via backlinks, not edits
