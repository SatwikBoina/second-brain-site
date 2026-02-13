---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: regression
model-family: ensemble-tree-models
ensemble-method: bagging
status: evergreen
tags:
  - "#ML"
  - "#regression"
  - "#fundamentals"
---

# Random Forest Regressor

> An ensemble learning algorithm that builds multiple decision trees on bootstrapped data and averages their predictions to reduce variance and improve generalization.

---

## 1. Core Idea

Random Forest combines **many high-variance decision trees** into a single, more stable model by introducing randomness at:
- the data level (bootstrapping)
- the feature level (feature subsampling)

🔗 Base learner:
- [[Decision Tree Regressor]]

---

## 2. Intuition

Instead of trusting one noisy expert (a single tree), Random Forest:
- asks many independent experts
- lets them vote (average)
- trusts the consensus

---

## 3. Analogy

Think of predicting weather:
- One person may be wrong
- Averaging many independent opinions gives a more reliable forecast

---

## 4. How the Model Learns (Methodology)

Training proceeds as follows:

1. Draw multiple bootstrap samples from the dataset
2. Train a decision tree on each sample
3. At each split, consider only a random subset of features
4. Aggregate predictions by averaging

🔗 Concepts:
- [[Bagging]]
- [[Bootstrap Sampling]]
- [[Feature Subsampling]]

---

## 5. Mathematical Perspective

- Prediction = average of individual tree predictions
- Variance decreases as trees become less correlated
- Bias remains similar to a single tree

🔗 See:
- [[Bias–Variance Tradeoff]]

---

## 6. Bias–Variance Tradeoff

- Slightly higher bias than a single tree
- Much lower variance
- Strong generalization performance

🔗 Links:
- [[Overfitting vs Underfitting]]

---

## 7. Assumptions

Random Forest makes very few assumptions:

- No linearity assumption
- No feature distribution assumptions
- Assumes trees are reasonably decorrelated

🔗 Contrast:
- [[Linear Models — MOC]]

---

## 8. Hyperparameters (Key Controls)

Important hyperparameters include:

- n_estimators
- max_depth
- min_samples_split
- min_samples_leaf
- max_features
- bootstrap

🔗 See:
- [[Hyperparameter Tuning — MOC]]

---

## 9. Feature Handling

- No feature scaling required
- Handles non-linear interactions automatically
- Robust to outliers
- Handles mixed feature types well

🔗 Links:
- [[Feature Importance]]
- [[Handling Categorical Features]]

---

## 10. Evaluation Metrics

Standard regression metrics apply:

- MSE / RMSE
- MAE
- R²

🔗 See:
- [[Regression Metrics — MOC]]

---

## 11. Interpretability

- Less interpretable than a single tree
- Feature importance provides global insight
- Partial dependence improves understanding

🔗 Links:
- [[Model Interpretability]]
- [[Partial Dependence Plots]]

---

## 12. When Random Forest Works Well

- Complex non-linear relationships
- Medium to large datasets
- High variance problems
- Strong baseline for tabular data

---

## 13. When It Fails

- Very large datasets (slow inference)
- High-dimensional sparse data
- Extrapolation beyond training range
- When interpretability is critical

---

## 14. Relationship to Other Models

- Bagging-based ensemble
- Complementary to boosting methods
- Predecessor to modern GBMs

🔗 Related:
- [[Gradient Boosting Regressor]]
- [[XGBoost Regressor]]
- [[Bagging]]

---

## 15. Position in the ML Landscape

- Canonical ensemble tree model
- Low-variance extension of decision trees
- Go-to baseline for tabular regression
