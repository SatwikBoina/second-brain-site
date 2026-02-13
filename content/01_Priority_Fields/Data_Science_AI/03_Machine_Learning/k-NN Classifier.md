---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: classification
model-family: distance-based-models
status: evergreen
---

# k-Nearest Neighbors Classifier (k-NN Classifier)

> A non-parametric classification algorithm that predicts a class label based on the majority vote of the k most similar data points.

---

## 1. Core Idea

k-NN Classifier assigns a class to a query point by:
- Finding the **k nearest training samples**
- Aggregating their labels (majority vote or weighted vote)
- Producing a **local decision** based on proximity

There is **no explicit training phase**.

🔗 Model family:
- [[Distance-Based Models — MOC]]

---

## 2. Intuition

Points that are close in feature space are likely to belong to the **same class**.  
Classification is driven entirely by **neighborhood structure**.

---

## 3. Analogy

Classifying a person by:
- Looking at the k most similar people
- Seeing which group they mostly belong to
- Assigning that group as the label

---

## 4. How the Model Works (Methodology)

1. Store all labeled training data
2. Compute distances between the query and all points
3. Select the k nearest neighbors
4. Aggregate labels (vote)
5. Assign the most frequent (or weighted) class

🔗 Concepts:
- [[Distance Metrics]]
- [[Lazy Learning]]

---

## 5. Distance Metrics

Common distance functions:

- Euclidean distance
- Manhattan distance
- Minkowski distance
- Cosine distance

🔗 See:
- [[Distance Metrics — MOC]]

---

## 6. Voting & Weighting Schemes

Neighbor contributions can be:

- **Uniform voting** (equal weight)
- **Distance-weighted voting** (closer points matter more)

🔗 Concepts:
- [[Distance Weighting]]

---

## 7. Bias–Variance Tradeoff

- Small k → low bias, high variance
- Large k → high bias, low variance

🔗 See:
- [[Bias–Variance Tradeoff]]

---

## 8. Assumptions

k-NN assumes:

- Distance meaningfully reflects similarity
- Classes form local clusters
- Feature space geometry is informative

🔗 Contrast:
- [[Linear Models — MOC]]
- [[Tree-Based Models — MOC]]

---

## 9. Hyperparameters (Critical)

Key hyperparameters include:

- k (number of neighbors)
- Distance metric
- Weighting scheme
- Search algorithm (brute, KD-tree, Ball-tree)

🔗 See:
- [[Hyperparameter Tuning — MOC]]

---

## 10. Feature Scaling Requirement

k-NN is **extremely sensitive to feature scale**:

- Mandatory feature normalization or standardization
- Unscaled features distort distances

🔗 Links:
- [[Feature Scaling]]
- [[Standardization]]

---

## 11. Handling Class Imbalance

k-NN can be affected by imbalance:

- Majority class can dominate local votes
- Distance weighting can help
- Careful choice of k is important

🔗 Concepts:
- [[Class Imbalance]]

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

## 13. Computational Characteristics

- No training cost
- High inference cost
- Memory intensive
- Scales poorly with dataset size

🔗 Concepts:
- [[Computational Complexity]]
- [[KD-Tree]]
- [[Ball Tree]]

---

## 14. Interpretability

- Highly intuitive and explainable
- Predictions traceable to neighbors
- No global decision boundary

---

## 15. When k-NN Classifier Works Well

- Small to medium datasets
- Low-dimensional feature spaces
- Well-separated local class clusters

---

## 16. When It Fails

- High-dimensional data (curse of dimensionality)
- Large datasets
- Noisy features
- Poorly chosen distance metric

🔗 Concepts:
- [[Curse of Dimensionality]]

---

## 17. Relationship to Other Models

- Classification counterpart of k-NN Regressor
- Distance-based alternative to SVM and Logistic Regression

🔗 Related:
- [[k-NN Regressor]]
- [[Support Vector Machine]]
- [[Logistic Regression]]

---

## 18. Position in the ML Landscape

- Simplest distance-based classifier
- Strong baseline and sanity check
- Conceptually important non-parametric model
