---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: classification
model-family: ensemble-tree-models
ensemble-method: boosting
status: evergreen
---

# Gradient Boosting Classifier

> An ensemble classification algorithm that builds models sequentially, where each new model focuses on correcting the classification errors of the previous ones by optimizing a loss function.

---

## 1. Core Idea

Gradient Boosting Classifier builds an **additive model** of weak learners (usually shallow decision trees) trained sequentially to reduce classification error.

🔗 Base learner:
- [[Decision Tree Classifier]]

🔗 Ensemble family:
- [[Boosting]]

---

## 2. Intuition

Instead of training many independent trees, the model:
- Starts with a weak classifier
- Identifies misclassified samples
- Adds new classifiers to focus on those mistakes

Each step improves the overall decision boundary.

---

## 3. Analogy

Think of coaching a team:
- First strategy fails for some opponents
- You adjust specifically for those failures
- Repeated refinements lead to a strong overall strategy

---

## 4. How the Model Learns (Methodology)

1. Initialize predictions (e.g., class probabilities)
2. Compute gradients of the loss function
3. Fit a weak learner to these gradients
4. Add learner to the ensemble with a learning rate
5. Repeat for many iterations

🔗 Concepts:
- [[Additive Models]]
- [[Gradient Descent]]
- [[Greedy Algorithms]]

---

## 5. Loss Functions (Classification)

Common loss functions include:

- Log loss (cross-entropy)
- Exponential loss (AdaBoost-style)
- Deviance

🔗 See:
- [[Classification Loss Functions — MOC]]
- [[Log Loss]]

---

## 6. Mathematical Perspective

- Performs **gradient descent in function space**
- Each tree approximates the negative gradient
- Flexible and loss-driven framework

🔗 Concepts:
- [[Functional Gradient Descent]]
- [[Convex Optimization]]

---

## 7. Bias–Variance Tradeoff

- Significantly reduces bias
- Can increase variance if overfit
- Controlled by learning rate and tree depth

🔗 See:
- [[Bias–Variance Tradeoff]]
- [[Overfitting vs Underfitting]]

---

## 8. Assumptions

Gradient Boosting assumes:

- Weak learners can incrementally improve performance
- Errors contain learnable structure
- Sensitive to noise and outliers

🔗 Contrast:
- [[Random Forest Classifier]]

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

Overfitting is controlled via:

- Learning rate shrinkage
- Tree depth limitation
- Subsampling (stochastic gradient boosting)

🔗 Links:
- [[Regularization — MOC]]

---

## 11. Feature Handling

- No feature scaling required
- Automatically models feature interactions
- Sensitive to noisy features

---

## 12. Handling Class Imbalance

Gradient Boosting can handle imbalance via:

- Class weights
- Custom loss functions
- Threshold tuning

🔗 Concepts:
- [[Class Imbalance]]
- [[Threshold Tuning]]

---

## 13. Evaluation Metrics

Common classification metrics:

- Accuracy
- Precision
- Recall
- F1-score
- ROC–AUC
- Log loss

🔗 See:
- [[Classification Metrics — MOC]]

---

## 14. Interpretability

- Less interpretable than Random Forest
- Feature importance and SHAP aid explanation

🔗 Links:
- [[Model Interpretability]]
- [[SHAP Values]]

---

## 15. When Gradient Boosting Classifier Works Well

- Complex non-linear decision boundaries
- Structured tabular data
- Medium-sized datasets
- When accuracy is critical

---

## 16. When It Fails

- Very noisy datasets
- Small datasets
- Poor hyperparameter tuning
- Large datasets without optimized implementations

---

## 17. Relationship to Other Models

- Boosting-based ensemble
- Foundation for modern GBM classifiers

🔗 Related:
- [[Random Forest Classifier]]
- [[XGBoost Classifier]]
- [[LightGBM Classifier]]
- [[CatBoost Classifier]]

---

## 18. Position in the ML Landscape

- One of the strongest classical classifiers
- Bias-reduction focused ensemble
- Backbone of modern tabular classification
