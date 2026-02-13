---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: classification
model-family: ensemble-tree-models
ensemble-method: bagging
status: evergreen
---

# Random Forest Classifier

> An ensemble classification algorithm that builds multiple decision trees using bootstrapped data and random feature selection, then predicts the class by majority voting.

---

## 1. Core Idea

Random Forest Classifier combines many **high-variance decision tree classifiers** into a single, more robust model by:

- Training trees on different bootstrap samples
- Randomly selecting features at each split
- Aggregating predictions via majority vote

🔗 Base learner:
- [[Decision Tree Classifier]]

---

## 2. Intuition

A single decision tree may overfit and make unstable decisions.  
Random Forest reduces this instability by **averaging out errors across many independent trees**.

---

## 3. Analogy

Think of a jury:
- Each juror (tree) sees a slightly different version of the evidence
- The final verdict is decided by majority vote
- Individual biases cancel out

---

## 4. How the Model Learns (Methodology)

1. Draw multiple bootstrap samples from the dataset  
2. Train a decision tree on each sample  
3. At each split, consider only a random subset of features  
4. Aggregate predictions using majority voting  

🔗 Concepts:
- [[Bagging]]
- [[Bootstrap Sampling]]
- [[Feature Subsampling]]

---

## 5. Split Criteria (Classification)

Each tree typically uses:

- Gini Impurity
- Entropy (Information Gain)

🔗 See:
- [[Gini Impurity]]
- [[Entropy]]

---

## 6. Mathematical Perspective

- Prediction = mode of individual tree predictions
- Ensemble reduces variance via decorrelation
- Bias similar to a single tree, but much lower variance

🔗 See:
- [[Bias–Variance Tradeoff]]

---

## 7. Bias–Variance Tradeoff

- Slightly higher bias than a single tree
- Much lower variance
- Strong generalization performance

🔗 Links:
- [[Overfitting vs Underfitting]]

---

## 8. Assumptions

Random Forest makes minimal assumptions:

- No linearity assumption
- No distributional assumptions
- Assumes trees are sufficiently decorrelated

🔗 Contrast:
- [[Linear Models — MOC]]

---

## 9. Hyperparameters (Key Controls)

Important hyperparameters include:

- n_estimators
- max_depth
- min_samples_split
- min_samples_leaf
- max_features
- class_weight

🔗 See:
- [[Hyperparameter Tuning — MOC]]

---

## 10. Feature Handling

- No feature scaling required
- Handles non-linear interactions automatically
- Robust to outliers and noise
- Works well with mixed feature types

🔗 Links:
- [[Feature Importance]]
- [[Handling Categorical Features]]

---

## 11. Handling Class Imbalance

Random Forest can handle imbalance via:

- Class weighting
- Balanced bootstrap sampling
- Threshold tuning

🔗 Concepts:
- [[Class Imbalance]]
- [[Threshold Tuning]]

---

## 12. Evaluation Metrics

Common classification metrics include:

- Accuracy
- Precision
- Recall
- F1-score
- ROC–AUC

🔗 See:
- [[Classification Metrics — MOC]]

---

## 13. Interpretability

- Less interpretable than a single tree
- Feature importance provides global insight
- Partial dependence improves understanding

🔗 Links:
- [[Model Interpretability]]
- [[Partial Dependence Plots]]

---

## 14. When Random Forest Works Well

- Complex non-linear decision boundaries
- Medium to large tabular datasets
- High-variance classification problems
- Strong baseline classifier

---

## 15. When It Fails

- Very large datasets (memory + inference cost)
- High-dimensional sparse data
- When interpretability is critical
- Extrapolation beyond training distribution

---

## 16. Relationship to Other Models

- Bagging-based tree ensemble
- Classification counterpart of Random Forest Regressor
- Predecessor to boosting classifiers

🔗 Related:
- [[Random Forest Regressor]]
- [[Gradient Boosting Classifier]]
- [[XGBoost Classifier]]

---

## 17. Position in the ML Landscape

- Canonical ensemble classifier
- Low-variance extension of decision trees
- Go-to baseline for tabular classification
