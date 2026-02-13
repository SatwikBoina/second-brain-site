---
type: concept
domain: machine-learning
category: theory
status: evergreen
---

# Variance Reduction

> Variance reduction refers to techniques that decrease the sensitivity of a model to fluctuations in the training data, leading to more stable predictions.

---

## 1. One-Line Intuition

> If a model changes drastically with small changes in data, it has high variance. Variance reduction stabilizes predictions.

---

## 2. Where Variance Comes From

Variance arises when:

- Model is very flexible
- Small data changes lead to different decision boundaries
- Dataset is noisy
- Model is overparameterized

Example:
- Deep decision trees
- k-NN with small k
- High-degree polynomials

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 3. Mathematical Definition

For prediction function \( \hat{f}(x) \):

\[
Var(\hat{f}(x)) = E[(\hat{f}(x) - E[\hat{f}(x)])^2]
\]

High variance:
- Model output fluctuates across datasets.

---

## 4. Bias–Variance Decomposition

Expected error:

\[
\text{Error} = \text{Bias}^2 + \text{Variance} + \text{Noise}
\]

Variance reduction lowers:

- Overfitting
- Instability
- Sensitivity to noise

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 5. Core Idea of Variance Reduction

If we average multiple independent estimators:

\[
\hat{f}_{avg} = \frac{1}{T} \sum_{t=1}^{T} \hat{f}_t
\]

Then:

\[
Var(\hat{f}_{avg}) = \frac{1}{T^2} \sum Cov(\hat{f}_i, \hat{f}_j)
\]

If models are independent:

\[
Var(\hat{f}_{avg}) = \frac{Var(\hat{f})}{T}
\]

Variance decreases with more models.

---

## 6. Correlation Matters

In practice, models are correlated.

Variance becomes:

\[
Var = \rho Var_{single}
\]

Where:
- \( \rho \) = average correlation between models

Lower correlation → stronger variance reduction.

This is why Random Forest adds feature randomness.

🔗 Related:
- [[Bagging]]
- [[Random Forest Classifier]]

---

## 7. Methods for Variance Reduction

---

## 7.1 Bagging

- Bootstrap sampling
- Independent models
- Average predictions

Primary variance-reduction method.

---

## 7.2 Random Forest

- Bagging + feature randomness
- Reduces correlation further

---

## 7.3 Model Averaging

- Train multiple models
- Average outputs

---

## 7.4 Regularization

Reducing model flexibility also reduces variance:

- L2 regularization
- Early stopping
- Dropout (in neural networks)

🔗 Related:
- [[Regularization — MOC]]
- [[Early Stopping]]

---

## 8. Variance vs Overfitting

High variance leads to:

- Low training error
- High test error
- Overfitting

Variance reduction improves generalization.

---

## 9. Variance Reduction in Different Models

| Model | Variance Level | Reduction Strategy |
|--------|----------------|-------------------|
| Decision Trees | High | Bagging |
| k-NN (small k) | High | Increase k |
| Neural Networks | High | Regularization, Dropout |
| Linear Regression | Low | Usually not needed |

---

## 10. Variance in High Dimensions

High dimensions increase variance because:

- Sparse data
- Distance instability
- Large parameter space

Dimensionality reduction helps.

🔗 Related:
- [[Curse of Dimensionality]]
- [[Principal Component Analysis]]

---

## 11. Tradeoff: Bias vs Variance

Reducing variance may:

- Increase bias
- Simplify model
- Reduce flexibility

Goal:
> Balance both.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 12. Geometric Intuition

Imagine:

- Many wiggly decision boundaries
- Averaging smooths the wiggles

Ensembles act as:
> Noise cancelers.

---

## 13. When Variance Reduction Works Best

- High-variance models
- Large datasets
- Noisy data
- Complex decision boundaries

---

## 14. When It’s Less Useful

- Already low-variance models
- Small datasets
- High bias problems

---

## 15. Relationship to Other Concepts

Variance reduction connects strongly to:

- [[Bagging]]
- [[Random Forest Classifier]]
- [[Ensemble Learning — MOC]]
- [[Bias–Variance Tradeoff]]
- [[Regularization — MOC]]
- [[Model Complexity]]

---

## 16. Why Variance Reduction Matters

Variance reduction explains:

- Why ensembles outperform single models
- Why averaging helps
- Why model diversity is powerful
- Why randomness improves stability

It is the theoretical foundation of:
> Bagging and Random Forest.
