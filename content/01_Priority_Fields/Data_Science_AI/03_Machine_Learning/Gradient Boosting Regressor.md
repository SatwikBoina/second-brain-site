---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: regression
model-family: ensemble-tree-models
ensemble-method: boosting
status: evergreen
tags:
  - ML
  - fundamentals
---

# Gradient Boosting Regressor

> An ensemble learning algorithm that builds models sequentially, where each new model corrects the errors of the previous ones by optimizing a loss function using gradient descent.

---

## 1. Core Idea

Gradient Boosting builds an **additive model** by training weak learners (usually shallow decision trees) **sequentially**, each focusing on the mistakes made so far.

🔗 Base learner:
- [[Decision Tree Regressor]]

🔗 Ensemble family:
- [[Boosting]]

---

## 2. Intuition

Instead of building many independent trees (like Random Forest), Gradient Boosting:
- starts with a simple model
- repeatedly asks: *“Where am I still wrong?”*
- adds a new model to fix those errors

---

## 3. Analogy

Think of learning to shoot arrows:
- First shot misses badly
- Second shot corrects the biggest error
- Each new shot refines aim until accuracy improves

---

## 4. How the Model Learns (Methodology)

Training proceeds as follows:

1. Initialize model with a constant prediction
2. Compute residuals (errors)
3. Fit a weak learner to residuals
4. Add learner to the model with a learning rate
5. Repeat for many iterations

🔗 Concepts:
- [[Additive Models]]
- [[Residual Learning]]
- [[Greedy Algorithms]]

---

## 5. Optimization Perspective

Gradient Boosting performs **gradient descent in function space**:

- Each new model approximates the negative gradient of the loss
- Loss functions guide learning directly

🔗 See:
- [[Gradient Descent]]
- [[Loss Functions — MOC]]
- [[Functional Gradient Descent]]

---

## 6. Loss Functions (Regression)

Common loss functions include:

- Squared error
- Absolute error
- Huber loss
- Quantile loss

🔗 See:
- [[Regression Loss Functions — MOC]]

---

## 7. Bias–Variance Tradeoff

- Lower bias than Random Forest
- Higher variance if overfit
- Strong control via learning rate and tree depth

🔗 Links:
- [[Bias–Variance Tradeoff]]
- [[Overfitting vs Underfitting]]

---

## 8. Assumptions

Gradient Boosting makes few assumptions:

- No linearity assumption
- Sensitive to noise
- Assumes weak learners can capture structure incrementally

🔗 Contrast:
- [[Linear Models — MOC]]

---

## 9. Hyperparameters (Critical)

Key hyperparameters include:

- n_estimators
- learning_rate
- max_depth
- min_samples_leaf
- subsample

🔗 See:
- [[Hyperparameter Tuning — MOC]]
- [[Early Stopping]]

---

## 10. Regularization Techniques

Gradient Boosting controls overfitting via:

- Shrinkage (learning rate)
- Tree depth limitation
- Subsampling (stochastic gradient boosting)

🔗 Links:
- [[Regularization — MOC]]

---

## 11. Feature Handling

- No feature scaling required
- Automatically models non-linear interactions
- Sensitive to outliers (depending on loss)

🔗 Links:
- [[Feature Importance]]

---

## 12. Evaluation Metrics

Uses standard regression metrics:

- MSE / RMSE
- MAE
- R²

🔗 See:
- [[Regression Metrics — MOC]]

---

## 13. Interpretability

- Less interpretable than Random Forest
- Feature importance and SHAP help explain predictions

🔗 Links:
- [[Model Interpretability]]
- [[SHAP Values]]

---

## 14. When Gradient Boosting Works Well

- Complex structured data
- Medium-sized tabular datasets
- When strong predictive performance matters

---

## 15. When It Fails

- Very noisy data
- Small datasets
- Poor hyperparameter tuning
- Large datasets without optimized implementations

---

## 16. Relationship to Other Models

- Boosting-based ensemble
- Foundation for modern GBMs

🔗 Related:
- [[Random Forest Regressor]]
- [[XGBoost Regressor]]
- [[LightGBM Regressor]]
- [[CatBoost Regressor]]

---

## 17. Position in the ML Landscape

- One of the strongest classical ML algorithms
- Bias-reduction focused ensemble
- Backbone of modern tabular ML
