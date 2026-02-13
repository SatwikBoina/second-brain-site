# 📌 MOC — Distance-Based Models

> Central hub for all models that make predictions based on **distance or similarity** between data points.
> These models rely on the geometry of the feature space rather than explicit parametric learning.

---

## 1. Core Idea

Distance-based models assume:

> “Similar inputs should produce similar outputs.”

Predictions are driven by **proximity in feature space**, not by learned parameters.

---

## 2. Key Characteristics

- Non-parametric or weakly parametric
- Highly sensitive to feature scaling
- Strongly affected by dimensionality
- Simple but powerful baselines

---

## 3. Supervised Distance-Based Algorithms

### Regression

- [[k-NN Regressor]]

### Classification

- [[k-Nearest Neighbors Classifier]]

---

## 4. Unsupervised Distance-Based Algorithms

- [[k-Means Clustering]]
- [[k-Medoids]]
- [[Hierarchical Clustering]]
- [[DBSCAN]]

---

## 5. Distance Metrics

Distance defines *everything* in this family.

- [[Euclidean Distance]]
- [[Manhattan Distance]]
- [[Minkowski Distance]]
- [[Cosine Distance]]
- [[Mahalanobis Distance]]

🔗 Hub:
- [[Distance Metrics — MOC]]

---

## 6. Bias–Variance Perspective

- Small neighborhood → low bias, high variance
- Large neighborhood → high bias, low variance

🔗 See:
- [[Bias–Variance Tradeoff]]

---

## 7. Feature Scaling & Preprocessing

Distance-based models **require careful preprocessing**:

- [[Feature Scaling]]
- [[Standardization]]
- [[Normalization]]
- [[Feature Selection]]

---

## 8. Curse of Dimensionality

As dimensions increase:

- Distances lose meaning
- Neighbors become indistinguishable
- Performance degrades rapidly

🔗 Core concept:
- [[Curse of Dimensionality]]

---

## 9. Computational Characteristics

- Low or zero training cost
- High inference cost
- Memory intensive

🔗 Concepts:
- [[Computational Complexity]]
- [[KD-Tree]]
- [[Ball Tree]]

---

## 10. Hyperparameters

Typical tunables include:

- Number of neighbors (k)
- Distance metric
- Weighting scheme
- Search strategy

🔗 See:
- [[Hyperparameter Tuning — MOC]]

---

## 11. Interpretability

- Intuitive local explanations
- No global model understanding
- Easy to justify predictions via neighbors

🔗 Links:
- [[Model Interpretability]]

---

## 12. When to Use Distance-Based Models

- Small to medium datasets
- Low-dimensional feature spaces
- Strong local similarity structure
- As baselines or sanity checks

---

## 13. When to Avoid Distance-Based Models

- High-dimensional data
- Large datasets
- Poorly scaled features
- Weak notion of similarity

---

## 14. Relationship to Other Model Families

- Contrast with [[Linear Models — MOC]]
- Contrast with [[Tree-Based Models — MOC]]
- Related to [[Kernel Methods — MOC]] via similarity concepts

---

## Usage Rules

- No algorithm derivations here
- Algorithms live in separate notes
- Concepts must remain atomic
- Extend only via links, not explanations
