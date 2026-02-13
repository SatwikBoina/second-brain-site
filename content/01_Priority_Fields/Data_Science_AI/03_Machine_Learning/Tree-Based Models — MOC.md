# 📌 MOC — Tree-Based Models

> Central hub for all decision-tree–based models used in supervised learning.
> These models learn hierarchical decision rules via recursive partitioning.

---

## 1. Core Idea

Tree-based models:
- Partition the feature space into regions
- Learn decision rules in a hierarchical manner
- Are **non-parametric** and **non-linear by construction**

They do not assume any functional form of the data.

---

## 2. Base Tree Models

Foundational building blocks.

- [[Decision Tree Regressor]]
- [[Decision Tree Classifier]]

---

## 3. Ensemble Methods Using Trees

Tree-based ensembles improve performance by combining many trees.

### Bagging-Based

- [[Random Forest Regressor]]
- [[Random Forest Classifier]]

🔗 Concept:
- [[Bagging]]

---

### Boosting-Based

- [[Gradient Boosting Regressor]]
- [[Gradient Boosting Classifier]]
- [[XGBoost Regressor]]
- [[LightGBM Regressor]]
- [[CatBoost Regressor]]

🔗 Concept:
- [[Boosting]]

---

## 4. Split Criteria & Tree Learning Concepts

Core mechanisms used by trees.

- [[Variance Reduction]]
- [[MSE — Mean Squared Error]]
- [[Gini Impurity]]
- [[Entropy]]
- [[Information Gain]]

---

## 5. Bias–Variance Perspective

- Single trees → low bias, high variance
- Bagging → variance reduction
- Boosting → bias reduction

🔗 See:
- [[Bias–Variance Tradeoff]]
- [[Overfitting vs Underfitting]]

---

## 6. Regularization & Control

Tree complexity is controlled via:

- [[Tree Depth]]
- [[Pruning]]
- [[Cost Complexity Pruning]]
- [[Early Stopping]]

---

## 7. Feature Handling Characteristics

Tree-based models:

- Do NOT require feature scaling
- Handle non-linear interactions automatically
- Are sensitive to small data perturbations

🔗 Related:
- [[Feature Importance]]
- [[Handling Categorical Features]]
- [[Handling Missing Data]]

---

## 8. Evaluation Metrics

Evaluation depends on task type:

- [[Regression Metrics — MOC]]
- [[Classification Metrics — MOC]]

---

## 9. Interpretability & Explainability

- Single trees → highly interpretable
- Ensembles → require post-hoc explanation

🔗 Tools:
- [[Model Interpretability]]
- [[SHAP Values]]
- [[Partial Dependence Plots]]

---

## 10. When to Use Tree-Based Models

- Complex non-linear relationships
- Mixed feature types
- Strong tabular data baselines
- When feature interactions matter

---

## 11. Limitations

- High variance (single trees)
- Poor extrapolation
- Large ensembles can be slow
- Less stable than linear models

---

## 12. Relationship to Other Model Families

- Contrast with [[Linear Models — MOC]]
- Complement [[Distance-Based Models — MOC]]
- Foundation of modern ensemble learning

---

## Usage Rules

- Do NOT add derivations here
- Algorithms must live in separate notes
- Concepts must remain atomic
- Extend via links, not explanations
