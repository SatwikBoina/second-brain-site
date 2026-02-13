---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: regression
model-family: tree-based-models
status: evergreen
tags:
  - "#ML"
  - "#fundamentals"
  - "#regression"
---

# Decision Tree Regressor

> A non-parametric supervised learning algorithm that predicts a continuous target by recursively partitioning the feature space into regions with similar target values.

---

## 1. Core Idea

A Decision Tree Regressor learns **decision rules** in the form of feature-based splits, creating a tree where:
- internal nodes = decisions
- leaves = predicted values (usually mean of targets)

🔗 Model family:
- [[Tree-Based Models — MOC]]

---

## 2. Intuition

Instead of fitting a global equation, the model:
- asks a sequence of **yes/no questions**
- narrows down to a region of similar outcomes
- predicts using local averages

---

## 3. Analogy

Think of diagnosing a problem by asking:
> “Is it more than X?”  
> “Is it less than Y?”

Each question narrows the possibilities until a final decision is reached.

---

## 4. How the Model Learns (Methodology)

Training involves **recursive binary splitting**:

1. Choose a feature and split point
2. Split data to minimize impurity
3. Repeat on child nodes
4. Stop based on constraints
5. Assign prediction to leaf nodes

🔗 Concepts:
- [[Recursive Partitioning]]
- [[Greedy Algorithms]]

---

## 5. Split Criterion (Regression)

For regression trees, splits are chosen to minimize variance:

- Mean Squared Error (MSE)
- Variance reduction

🔗 See:
- [[Variance Reduction]]
- [[Mean Squared Error]]

---

## 6. Mathematical Perspective

- No explicit parametric form
- Piecewise constant approximation
- Locally optimal (greedy)

🔗 Related:
- [[Non-Parametric Models]]

---

## 7. Bias–Variance Tradeoff

- Very low bias
- Very high variance
- Easily overfits without constraints

🔗 See:
- [[Bias–Variance Tradeoff]]
- [[Overfitting vs Underfitting]]

---

## 8. Assumptions

Decision Trees make **minimal assumptions**:

- No linearity assumption
- No distributional assumptions
- Sensitive to noise

🔗 Contrast:
- [[Linear Models — MOC]]

---

## 9. Hyperparameters (Critical)

Key controls to prevent overfitting:

- max_depth
- min_samples_split
- min_samples_leaf
- max_features

🔗 See:
- [[Hyperparameter Tuning — MOC]]
- [[Tree Pruning]]

---

## 10. Pruning Strategies

- Pre-pruning (early stopping)
- Post-pruning (cost complexity pruning)

🔗 Concepts:
- [[Pruning]]
- [[Cost Complexity Pruning]]

---

## 11. Feature Handling

- No need for feature scaling
- Handles non-linear interactions automatically
- Sensitive to small data changes

🔗 Links:
- [[Feature Importance]]
- [[Handling Categorical Features]]

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

- Highly interpretable
- Can be visualized easily
- Rule-based explanations possible

🔗 Links:
- [[Model Interpretability]]

---

## 14. When Decision Trees Work Well

- Non-linear relationships
- Mixed feature types
- Need for explainability
- Small to medium datasets

---

## 15. When They Fail

- High variance
- Poor extrapolation
- Unstable with noisy data

---

## 16. Relationship to Other Models

- Base learner for ensembles
- Foundation of Random Forests and Boosting

🔗 Related:
- [[Random Forest Regressor]]
- [[Gradient Boosting Regressor]]
- [[Bagging]]
- [[Boosting]]

---

## 17. Position in the ML Landscape

- Canonical non-linear model
- High-variance, low-bias learner
- Building block of modern ensemble methods
