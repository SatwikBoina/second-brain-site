---
type: concept
domain: machine-learning
category: interpretability
status: evergreen
---

# Partial Dependence Plots (PDP)

> Partial Dependence Plots show the average effect of one (or more) features on the predicted outcome of a machine learning model.

---

## 1. One-Line Intuition

> Vary one feature while averaging out all others to see its marginal effect on prediction.

---

## 2. Why PDP Exists

Complex models (e.g., Random Forest, XGBoost, Neural Networks):

- Capture nonlinear interactions
- Hard to interpret directly

PDP helps visualize:

- Feature influence
- Nonlinearity
- Threshold effects
- Saturation behavior

🔗 Related:
- [[Model Interpretability]]
- [[SHAP Values]]

---

## 3. Mathematical Definition

For feature \( x_s \):

\[
PD(x_s) = \mathbb{E}_{x_c}[f(x_s, x_c)]
\]

Where:

- \( x_s \) = feature(s) of interest
- \( x_c \) = all other features
- \( f(\cdot) \) = model

We average predictions over the joint distribution of other features.

---

## 4. How PDP Is Computed

For each value of feature \( x_s \):

1. Replace feature with fixed value.
2. Keep all other features as observed.
3. Compute predictions.
4. Average predictions.

Repeat across range of feature values.

---

## 5. Interpretation

PDP curve shows:

- Positive slope → increasing feature increases prediction.
- Negative slope → increasing feature decreases prediction.
- Flat line → feature has little effect.
- Nonlinear shape → nonlinear influence.

---

## 6. Example (Loan Approval)

Feature: Income

PDP might show:

- Low income → low approval probability
- Medium income → rapid increase
- High income → plateau

Reveals:
- Threshold effect
- Diminishing returns

---

## 7. PDP vs SHAP

| Aspect | PDP | SHAP |
|----------|------|------|
| Local explanation | No | Yes |
| Global explanation | Yes | Yes |
| Interaction handling | Limited | Better |
| Theoretical basis | Averaging | Game theory |
| Computational cost | Lower | Higher |

PDP gives average effect.
SHAP gives per-instance contribution.

---

## 8. PDP and Feature Interactions

Problem:

If features are highly correlated:

- PDP may show unrealistic combinations.
- Averaging may distort effect.

Example:
- Age and Years of Experience correlated.
- PDP may generate impossible pairs.

---

## 9. Individual Conditional Expectation (ICE)

ICE plots:

- Show PDP for each instance separately.
- Reveal heterogeneity.
- Show interactions visually.

PDP = average of ICE curves.

---

## 10. 2D Partial Dependence

Can analyze two features together:

\[
PD(x_1, x_2)
\]

Produces:

- Surface plots
- Contour plots

Useful for:
- Interaction visualization

---

## 11. When PDP Works Well

- Weak feature correlations
- Tree-based models
- Tabular data
- Nonlinear models

---

## 12. When PDP Is Misleading

- Strongly correlated features
- Causal interpretation required
- Highly interacting variables
- Sparse regions of feature space

PDP assumes independence when marginalizing.

---

## 13. PDP and Model Type

Works especially well for:

- [[Random Forest Classifier]]
- [[XGBoost Classifier]]
- [[Decision Tree Classifier]]
- [[Neural Network Classifier]]

---

## 14. Bias–Variance Perspective

Complex models:

- Capture nonlinear patterns
- Hard to interpret

PDP helps interpret without changing bias/variance.

It does NOT improve model performance,
only explain behavior.

---

## 15. Strengths

- Simple
- Model-agnostic
- Visual and intuitive
- Reveals nonlinearities

---

## 16. Weaknesses

- Assumes feature independence
- Can hide heterogeneity
- Averages away local effects
- Not causal

---

## 17. Relationship to Other Concepts

PDP connects strongly to:

- [[Model Interpretability]]
- [[SHAP Values]]
- [[Feature Importance]]
- [[Random Forest Classifier]]
- [[Boosting]]
- [[Neural Network Classifier]]

---

## 18. Why PDP Matters

PDP teaches:

- Marginal feature effects
- Model behavior visualization
- How nonlinear models respond to inputs
- Difference between local and global explanations

It is one of the most practical tools for:
> Understanding black-box models.
