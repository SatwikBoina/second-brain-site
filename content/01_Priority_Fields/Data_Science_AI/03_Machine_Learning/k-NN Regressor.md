---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: regression
model-family: distance-based-models
status: evergreen
---

# k-Nearest Neighbors Regressor (k-NN Regressor)

> A non-parametric regression algorithm that predicts a continuous value by averaging the targets of the k most similar data points.

---

## 1. Core Idea

k-NN Regressor makes predictions by:
- Finding the **k closest training points**
- Aggregating their target values
- Producing a **local estimate** of the target

There is **no explicit training phase**.

🔗 Model family:
- [[Distance-Based Models — MOC]]

---

## 2. Intuition

Similar inputs should produce similar outputs.  
Prediction is driven entirely by **proximity in feature space**.

---

## 3. Analogy

Predicting house prices by:
- Looking at the k most similar houses nearby
- Averaging their prices
- Ignoring the rest of the city

---

## 4. How the Model Works (Methodology)

1. Store all training data
2. Compute distance between query and all points
3. Select k nearest neighbors
4. Aggregate their target values

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

## 6. Weighting Schemes

Neighbors can contribute:

- Uniformly
- Distance-weighted (closer points matter more)

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

- Meaningful distance in feature space
- Locally smooth target function
- Similarity implies relevance

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

- Mandatory feature normalization
- Unscaled features distort distance

🔗 Links:
- [[Feature Scaling]]
- [[Standardization]]

---

## 11. Evaluation Metrics

Uses standard regression metrics:

- RMSE
- MAE
- R²

🔗 See:
- [[Regression Metrics — MOC]]

---

## 12. Computational Characteristics

- No training cost
- High prediction cost
- Memory intensive
- Scales poorly with dataset size

🔗 Concepts:
- [[Computational Complexity]]

---

## 13. Interpretability

- Intuitive and explainable
- Predictions can be traced to neighbors
- No global model insight

---

## 14. When k-NN Works Well

- Small datasets
- Low-dimensional data
- Locally smooth relationships

---

## 15. When It Fails

- High-dimensional data (curse of dimensionality)
- Large datasets
- Noisy features
- Poor distance metric choice

🔗 Concepts:
- [[Curse of Dimensionality]]

---

## 16. Relationship to Other Models

- Instance-based learner
- Regression counterpart of k-NN classifier

🔗 Related:
- [[k-Nearest Neighbors Classifier]]
- [[Support Vector Regression]]

---

## 17. Position in the ML Landscape

- Simplest non-parametric regressor
- Strong baseline for local learning
- Conceptually important distance-based model
