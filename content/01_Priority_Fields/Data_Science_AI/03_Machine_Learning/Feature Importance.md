---
type: concept
domain: machine-learning
category: interpretability
status: evergreen
---

# Feature Importance

> Feature Importance measures how much each input feature contributes to a model’s predictive performance.

---

## 1. One-Line Intuition

> Feature importance tells us which variables the model relies on most.

---

## 2. Why Feature Importance Matters

Helps with:

- Model interpretability
- Feature selection
- Debugging models
- Detecting data leakage
- Fairness auditing

🔗 Related:
- [[Model Interpretability]]
- [[Data Leakage]]
- [[Feature Selection]]

---

# 3. Types of Feature Importance

There is no single definition.

Feature importance depends on:

- Model type
- Calculation method
- Local vs global explanation

---

# 4. Tree-Based Feature Importance

---

## 4.1 Impurity-Based Importance (Gini Importance)

In decision trees:

- Each split reduces impurity.
- Importance = total impurity reduction caused by feature.

\[
Importance_j = \sum (\text{Impurity decrease from splits on feature } j)
\]

Used in:

- [[Decision Tree Classifier]]
- [[Random Forest Classifier]]

---

### Strengths

- Fast
- Built into training

---

### Weaknesses

- Biased toward high-cardinality features
- Not reliable with correlated features

🔗 Related:
- [[Gini Impurity]]
- [[Information Gain]]

---

# 5. Permutation Feature Importance

---

## 5.1 Core Idea

1. Measure model performance.
2. Shuffle one feature.
3. Measure performance drop.
4. Importance = drop in performance.

If shuffling hurts performance a lot:
→ Feature is important.

---

### Advantages

- Model-agnostic
- More reliable than impurity importance
- Captures real predictive dependence

---

### Weaknesses

- Expensive
- Struggles with correlated features

🔗 Related:
- [[Cross Validation]]

---

# 6. SHAP-Based Importance

Global SHAP importance:

\[
Importance_j = \mathbb{E}(|\phi_j|)
\]

Average absolute SHAP value.

Captures:

- Consistent contribution magnitude
- Local + global interpretation

🔗 Related:
- [[SHAP Values]]

---

# 7. Coefficient-Based Importance

For linear models:

\[
y = \beta_0 + \sum \beta_j x_j
\]

Importance inferred from:

- Magnitude of coefficients
- Standardized coefficients

Works when:

- Features are scaled
- Model is linear

🔗 Related:
- [[Linear Regression]]
- [[Logistic Regression]]

---

# 8. Feature Importance vs Feature Effect

Feature importance:
- Measures influence magnitude.

Feature effect:
- Measures direction of influence.

PDP and SHAP show effects.
Importance measures magnitude only.

🔗 Related:
- [[Partial Dependence Plots]]

---

# 9. Global vs Local Importance

Global:
- Average impact across dataset.

Local:
- Importance for one prediction.

SHAP provides both.

---

# 10. Correlated Feature Problem

If features are correlated:

- Importance may be split.
- One feature may mask another.
- Importance becomes unstable.

Common in:
- Financial data
- Demographic features

---

# 11. Feature Importance in Ensembles

Random Forest:
- Impurity importance
- Permutation importance

Boosting:
- Gain-based importance
- SHAP importance preferred

---

# 12. Bias–Variance Perspective

High-variance models:

- Feature importance unstable.

Ensembles:

- More stable importance estimates.

🔗 Related:
- [[Variance Reduction]]
- [[Bagging]]

---

# 13. Strengths

- Improves interpretability
- Helps feature selection
- Identifies leakage
- Detects fairness issues

---

# 14. Limitations

- Not causal
- Can be unstable
- Correlation-sensitive
- Depends on model

Importance ≠ causality.

---

# 15. Relationship to Other Concepts

Feature Importance connects strongly to:

- [[Model Interpretability]]
- [[SHAP Values]]
- [[Partial Dependence Plots]]
- [[Decision Tree Classifier]]
- [[Random Forest Classifier]]
- [[Boosting]]
- [[Feature Selection]]

---

# 16. Why Feature Importance Matters

Feature Importance teaches:

- How models use input signals
- Where predictive power comes from
- Why interpretability is model-dependent
- Why correlated features complicate explanation

It is the foundation of:
> Practical model explainability.
