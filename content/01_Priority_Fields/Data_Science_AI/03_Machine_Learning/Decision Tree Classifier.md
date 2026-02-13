---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: classification
model-family: tree-based-models
status: evergreen
tags:
  - "#ML"
  - "#classification"
  - "#fundamentals"
---

# Decision Tree Classifier

> A non-parametric supervised learning algorithm that classifies data by learning hierarchical decision rules through recursive feature-based splitting.

---

## 1. Core Idea

A Decision Tree Classifier predicts class labels by:
- Asking a sequence of feature-based questions
- Partitioning the feature space into homogeneous regions
- Assigning the most frequent class at each leaf

🔗 Model family:
- [[Tree-Based Models — MOC]]

---

## 2. Intuition

Instead of learning a global decision boundary, the model:
- Breaks the problem into smaller decisions
- Solves them step by step
- Makes locally optimal choices

---

## 3. Analogy

Think of a **flowchart**:
- Each question narrows the possibilities
- Each answer leads you closer to a final decision
- The process is transparent and explainable

---

## 4. How the Model Learns (Methodology)

Training follows **recursive binary splitting**:

1. Select a feature and split point
2. Choose the split that maximizes class purity
3. Repeat recursively on child nodes
4. Stop based on constraints
5. Assign class labels to leaves

🔗 Concepts:
- [[Recursive Partitioning]]
- [[Greedy Algorithms]]

---

## 5. Split Criteria (Classification)

Common impurity measures include:

- Gini Impurity
- Entropy
- Information Gain

🔗 See:
- [[Gini Impurity]]
- [[Entropy]]
- [[Information Gain]]

---

## 6. Mathematical Perspective

- Non-parametric model
- Piecewise constant decision regions
- Greedy optimization (locally optimal splits)

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

Decision Trees assume:

- No linearity
- No distributional assumptions
- Sufficient data to support splits

🔗 Contrast:
- [[Linear Models — MOC]]

---

## 9. Hyperparameters (Critical)

Key hyperparameters include:

- max_depth
- min_samples_split
- min_samples_leaf
- max_features
- criterion

🔗 See:
- [[Hyperparameter Tuning — MOC]]
- [[Tree Pruning]]

---

## 10. Pruning Strategies

To control overfitting:

- Pre-pruning (early stopping)
- Post-pruning (cost complexity pruning)

🔗 Concepts:
- [[Pruning]]
- [[Cost Complexity Pruning]]

---

## 11. Feature Handling

- No feature scaling required
- Handles categorical and numerical features
- Sensitive to small data changes

🔗 Links:
- [[Handling Categorical Features]]
- [[Feature Importance]]

---

## 12. Evaluation Metrics

Common classification metrics:

- Accuracy
- Precision
- Recall
- F1-score
- ROC–AUC

🔗 See:
- [[Classification Metrics — MOC]]

---

## 13. Interpretability

- Highly interpretable
- Easy to visualize
- Rule-based explanations possible

🔗 Links:
- [[Model Interpretability]]

---

## 14. When Decision Trees Work Well

- Non-linear decision boundaries
- Mixed feature types
- Need for interpretability
- Small to medium datasets

---

## 15. When They Fail

- High variance
- Poor generalization on noisy data
- Unstable splits

---

## 16. Relationship to Other Models

- Classification counterpart of Decision Tree Regressor
- Base learner for ensemble classifiers

🔗 Related:
- [[Decision Tree Regressor]]
- [[Random Forest Classifier]]
- [[Gradient Boosting Classifier]]

---

## 17. Position in the ML Landscape

- Canonical non-linear classifier
- Foundation of ensemble tree methods
- High-variance, low-bias learner
