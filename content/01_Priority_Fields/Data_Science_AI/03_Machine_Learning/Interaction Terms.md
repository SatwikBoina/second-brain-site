---
type: concept
domain: machine-learning
category: feature-engineering
status: evergreen
---

# Interaction Terms

> Interaction terms capture situations where the effect of one feature on the target **depends on the value of another feature**.

---

## 1. Core Idea

In many real-world problems:

> The effect of Feature A is not independent of Feature B.

Interaction terms explicitly model this dependency by **combining features**.

---

## 2. What Interaction Means (Intuition)

Without interactions:
- Each feature contributes independently

With interactions:
- Features influence each other’s impact

The relationship becomes **context-dependent**, not additive.

---

## 3. Simple Example

Suppose:
- `study_hours`
- `sleep_hours`

Individually:
- More study → better score
- More sleep → better score

But together:
- Studying a lot **without sleep** hurts performance
- Studying a lot **with enough sleep** helps more

This dependency is an **interaction**.

---

## 4. Mathematical Form

For two features \(x_1\) and \(x_2\):

- Linear model (no interaction):
  \[
  y = \beta_0 + \beta_1 x_1 + \beta_2 x_2
  \]

- With interaction term:
  \[
  y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \beta_3 (x_1 \cdot x_2)
  \]

The product term captures interaction.

---

## 5. Interaction Terms vs Non-Linearity

Important distinction:

- Interaction ≠ non-linearity
- Linear models with interaction terms are still **linear in parameters**

🔗 Related:
- [[Linear Models — MOC]]
- [[Polynomial Features]]

---

## 6. Where Interaction Terms Are Commonly Used

- Linear Regression
- Logistic Regression
- Generalized Linear Models
- Statistical modeling

🔗 Related:
- [[Logistic Regression]]
- [[Linear Regression]]

---

## 7. Algorithms That Learn Interactions Automatically

Some models **do not require explicit interaction terms**:

- Decision Trees
- Random Forests
- Gradient Boosting
- XGBoost / LightGBM / CatBoost

These models learn interactions implicitly via splits.

🔗 Related:
- [[Tree-Based Models — MOC]]

---

## 8. Interaction Terms and Feature Engineering

Interaction terms are a form of **manual feature engineering**.

Pros:
- Increase model expressiveness
- Preserve interpretability (in linear models)

Cons:
- Increase dimensionality
- Increase overfitting risk

🔗 Related:
- [[Feature Engineering]]
- [[Model Complexity]]

---

## 9. Interaction Terms and Bias–Variance

- Adding interactions → ↓ bias
- Adds parameters → ↑ variance

Must be controlled via:
- Regularization
- Feature selection
- Cross-validation

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Regularization — MOC]]

---

## 10. Interaction Terms and Regularization

Regularization is often necessary when interactions are added:

- L1 → selects useful interactions
- L2 → stabilizes coefficients

🔗 Related:
- [[Lasso Regression]]
- [[Ridge Regression]]

---

## 11. Interaction Terms in Logistic Regression

In classification:
- Interaction terms affect **log-odds**
- Allow class boundaries to bend

Useful when:
- Feature effects differ across subgroups

🔗 Related:
- [[Logistic Regression]]

---

## 12. When Interaction Terms Help Most

- Linear or logistic models
- Domain knowledge suggests dependency
- Small to medium feature sets
- Need for interpretability

---

## 13. When Interaction Terms Hurt

- High-dimensional data
- Weak regularization
- No domain justification
- Tree or boosting models already used

---

## 14. Common Mistakes

- ❌ Adding all pairwise interactions blindly  
- ❌ Ignoring regularization  
- ❌ Assuming interactions are always needed  
- ❌ Using interactions with k-NN (rarely useful)

Interaction terms should be **intentional**, not automatic.

---

## 15. Why Interaction Terms Matter

Interaction terms explain:

- Why linear models sometimes underperform
- How simple models can capture richer patterns
- Why trees outperform linear models without feature engineering

They are the **bridge between linearity and complexity**.

---

## Usage Notes

- Link this note from:
  - Feature Engineering
  - Linear Models
  - Logistic Regression
  - Model Complexity
- Do NOT duplicate interaction explanations in algorithm notes
