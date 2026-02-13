---
type: concept
domain: machine-learning
category: interpretability
status: evergreen
---

# SHAP Values (SHapley Additive exPlanations)

> SHAP values assign each feature a contribution value for a particular prediction using principles from cooperative game theory.

---

## 1. One-Line Intuition

> SHAP tells you how much each feature contributed to pushing a prediction up or down.

---

## 2. Why SHAP Exists

Many ML models are:

- Complex
- Nonlinear
- Black-box

We want:

- Local explanations (per prediction)
- Global explanations (overall feature importance)
- Fair and consistent attribution

SHAP provides a unified framework.

🔗 Related:
- [[Model Interpretability]]
- [[Feature Importance in Trees]]

---

## 3. Game-Theoretic Foundation

SHAP is based on:

> Shapley values from cooperative game theory.

In game theory:

- Players cooperate to achieve a payoff.
- Shapley value assigns fair credit to each player.

In ML:

- Players = features
- Payoff = model prediction

---

## 4. Core Idea

For a prediction \( f(x) \):

\[
f(x) = \phi_0 + \sum_{i=1}^{M} \phi_i
\]

Where:

- \( \phi_0 \) = base value (expected prediction)
- \( \phi_i \) = contribution of feature i

SHAP decomposes prediction into additive contributions.

---

## 5. Shapley Value Formula

\[
\phi_i = \sum_{S \subseteq F \setminus \{i\}} 
\frac{|S|!(M-|S|-1)!}{M!}
\left[f(S \cup \{i\}) - f(S)\right]
\]

Where:

- S = subset of features
- M = total features

It averages marginal contributions across all feature subsets.

---

## 6. Key Properties

SHAP satisfies:

### 6.1 Efficiency
Contributions sum to total prediction.

### 6.2 Symmetry
Identical features get equal attribution.

### 6.3 Dummy
Unused features get zero contribution.

### 6.4 Additivity
Attributions combine across models.

These properties guarantee fairness.

---

## 7. Local vs Global Explanation

### Local Explanation
- SHAP explains one prediction.
- Shows why this specific prediction happened.

### Global Explanation
- Average absolute SHAP values.
- Shows overall feature importance.

---

## 8. SHAP vs Traditional Feature Importance

Traditional importance (e.g., Gini importance):

- Global only
- Biased toward high-cardinality features

SHAP:

- Local and global
- More consistent
- Theoretically grounded

🔗 Related:
- [[Gini Impurity]]
- [[Information Gain]]

---

## 9. Types of SHAP

---

### 9.1 TreeSHAP

- Efficient algorithm for tree models
- Exact Shapley values
- Used in XGBoost, LightGBM

---

### 9.2 KernelSHAP

- Model-agnostic
- Approximation-based
- Works for any model

---

### 9.3 DeepSHAP

- For neural networks

---

## 10. Interpretation of SHAP Values

- Positive SHAP → pushes prediction higher
- Negative SHAP → pushes prediction lower
- Magnitude → strength of impact

Example:

Loan approval:
- High income → positive SHAP
- High debt → negative SHAP

---

## 11. Visualization Tools

Common SHAP plots:

- Summary plot
- Force plot
- Dependence plot
- Waterfall plot

These help interpret complex models.

---

## 12. SHAP and Bias–Variance

Complex models:

- High variance
- Hard to interpret

SHAP does not reduce variance,
but improves transparency.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 13. Computational Complexity

Exact Shapley:

\[
O(2^M)
\]

Very expensive.

TreeSHAP reduces complexity dramatically for trees.

---

## 14. Strengths

- Theoretically sound
- Fair attribution
- Works locally and globally
- Model-agnostic versions available
- Widely adopted in industry

---

## 15. Weaknesses

- Computationally expensive (general case)
- Assumes feature independence (often)
- Interpretation can be misused
- Correlated features complicate attribution

---

## 16. SHAP vs LIME

| Aspect | SHAP | LIME |
|----------|-------|-------|
| Theoretical basis | Game theory | Local linear approximation |
| Consistency | Yes | No |
| Stability | Higher | Lower |
| Computational cost | Higher | Lower |

SHAP is more principled.

---

## 17. Relationship to Other Concepts

SHAP connects strongly to:

- [[Model Interpretability]]
- [[Feature Importance]]
- [[Random Forest Classifier]]
- [[XGBoost Classifier]]
- [[Neural Network Classifier]]
- [[Fairness in ML]]

---

## 18. When SHAP Works Well

- Tree-based models
- Complex nonlinear models
- Regulated industries
- Model auditing
- Feature debugging

---

## 19. When SHAP Can Be Misleading

- Highly correlated features
- Poorly calibrated models
- Causal misinterpretation

SHAP explains model behavior,
not real-world causality.

---

## 20. Why SHAP Matters

SHAP teaches:

- Fair feature attribution
- Local explanation of complex models
- Bridge between game theory and ML
- How interpretability can be formalized

It is one of the most important modern tools in explainable AI.
