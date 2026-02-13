---
type: concept
domain: machine-learning
category: unsupervised-learning
sub_category: clustering
status: evergreen
---

# Clustering Evaluation Metrics

> Clustering evaluation metrics measure how well a clustering algorithm groups similar points together and separates dissimilar points — with or without ground truth labels.

---

## 1. Core Problem

In supervised learning:
- We compare predictions to true labels.

In clustering:
- We often have **no labels**.
- “Correct clustering” may be ambiguous.

Evaluation depends on:
- Structure assumptions
- Distance definition
- Intended application

🔗 Related:
- [[Unsupervised Learning — MOC]]
- [[Clustering — MOC]]

---

# 2. Two Major Categories

Clustering metrics fall into two groups:

1. Internal Evaluation (No ground truth)
2. External Evaluation (With ground truth labels)

---

# 3. Internal Evaluation Metrics

These evaluate clustering using:
- Data geometry
- Compactness
- Separation

No labels required.

---

## 3.1 Silhouette Score

### Intuition

Measures:
- How close a point is to its own cluster
- Compared to other clusters

For each point:

\[
s = \frac{b - a}{\max(a, b)}
\]

Where:
- a = average distance to same-cluster points
- b = average distance to nearest other cluster

Range:
- -1 to 1

Interpretation:
- Close to 1 → well clustered
- Close to 0 → overlapping
- Negative → misclassified

Best for:
- Convex clusters (e.g., K-Means)

---

## 3.2 Davies–Bouldin Index (DBI)

### Intuition

Measures:
- Within-cluster scatter
- Between-cluster separation

Lower is better.

Sensitive to:
- Cluster shape
- Distance metric

---

## 3.3 Calinski–Harabasz Index

### Intuition

Ratio of:
- Between-cluster variance
to
- Within-cluster variance

Higher is better.

Works well for:
- Well-separated, spherical clusters

---

# 4. External Evaluation Metrics

These require:
- True labels

Used when clustering is evaluated against known classes.

---

## 4.1 Adjusted Rand Index (ARI)

### Intuition

Measures:
- Agreement between predicted clusters and true labels
- Corrects for random chance

Range:
- -1 to 1
- 1 = perfect agreement

Robust metric.

---

## 4.2 Normalized Mutual Information (NMI)

### Intuition

Measures:
- Shared information between clusters and labels

Range:
- 0 to 1
- 1 = perfect match

Based on:
- Information theory

🔗 Related:
- [[Information Theory — MOC]]

---

## 4.3 Homogeneity, Completeness, V-Measure

- Homogeneity: clusters contain only one class
- Completeness: all class members in same cluster
- V-measure: harmonic mean of both

Useful for:
- Imbalanced datasets

---

# 5. Choosing the Right Metric

Depends on:

- Do you have labels?
- Are clusters convex?
- Are densities uniform?
- Is clustering goal interpretability or prediction?

Example:

| Scenario | Suggested Metric |
|----------|------------------|
| No labels | Silhouette |
| Compare to known classes | ARI / NMI |
| K-means tuning | Silhouette / CH |
| Non-convex clusters | Avoid silhouette |

---

# 6. Metric Sensitivity

Clustering metrics depend on:

- Distance metric (Euclidean, cosine)
- Scale of features
- Number of clusters
- Data preprocessing

Always combine with:

- Visual inspection
- Domain knowledge

🔗 Related:
- [[Feature Scaling]]
- [[Dimensionality Reduction — MOC]]

---

# 7. Common Pitfalls

- ❌ Using silhouette on non-convex clusters
- ❌ Comparing metrics across different algorithms blindly
- ❌ Ignoring feature scaling
- ❌ Treating metric as absolute truth
- ❌ Overfitting number of clusters to maximize metric

Clustering has no universal ground truth.

---

# 8. Internal vs External Comparison

| Aspect | Internal | External |
|---------|----------|-----------|
| Requires labels | ❌ | ✅ |
| Measures geometry | ✅ | ❌ |
| Measures semantic correctness | ❌ | ✅ |
| Objective | Compactness/separation | Agreement with labels |

---

# 9. Relationship to Other Concepts

Clustering evaluation connects to:

- [[K-Means]]
- [[Hierarchical Clustering]]
- [[DBSCAN]]
- [[Unsupervised Learning — MOC]]
- [[Information Theory — MOC]]
- [[Bias–Variance Tradeoff]]

---

# 10. Why Clustering Evaluation Matters

Clustering metrics explain:

- Why choosing K is difficult
- Why visual inspection can mislead
- Why different algorithms behave differently
- Why unsupervised validation is fundamentally harder

Clustering is exploratory — metrics guide, not dictate.
