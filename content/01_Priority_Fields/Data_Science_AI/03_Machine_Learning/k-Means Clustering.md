---
type: algorithm
domain: machine-learning
category: unsupervised-learning
model_family: distance-based
primary_use: clustering
status: evergreen
---

# K-Means Clustering

> K-Means is a centroid-based clustering algorithm that partitions data into K clusters by minimizing within-cluster variance.

---

## 1. One-Line Intuition

> K-Means finds K points (centroids) such that each data point belongs to the nearest centroid.

---

## 2. Core Objective

K-Means minimizes:

$$
\sum_{k=1}^{K} \sum_{x_i \in C_k} ||x_i - \mu_k||^2
$$

Where:
- $C_k$ = cluster k  
- $\mu_k$ = centroid of cluster k  

This is called:

> Within-Cluster Sum of Squares (WCSS)

---

## 3. Algorithm Steps

---

### Step 1: Initialize K Centroids

- Random initialization
- Or k-means++

---

### Step 2: Assign Points to Nearest Centroid

Using:
- Euclidean distance (default)

Each point joins cluster with closest centroid.

---

### Step 3: Update Centroids

Recompute:

$$
\mu_k = \text{mean of points in cluster k}
$$

---

### Step 4: Repeat Until Convergence

Convergence when:
- Assignments stop changing
- Centroids stabilize
- Objective stops decreasing

---

## 4. Geometric Interpretation

K-Means:

- Partitions space into Voronoi regions
- Assumes spherical clusters
- Assumes equal variance in each dimension

It imposes strong geometric bias.

---

## 5. Key Assumptions

K-Means assumes:

- Clusters are convex
- Clusters are roughly spherical
- Similar cluster sizes
- Euclidean distance is meaningful
- Features are scaled properly

Violation leads to poor clustering.

🔗 Related:
- [[Distance Metrics — MOC]]
- [[Feature Scaling]]

---

## 6. Initialization Matters (k-means++)

Random initialization can cause:

- Poor local minima
- Slow convergence

k-means++:
- Spreads initial centroids apart
- Improves stability
- Faster convergence

---

## 7. Choosing K

K is not learned automatically.

Common methods:

- Elbow Method
- Silhouette Score
- Domain knowledge
- Gap Statistic

🔗 Related:
- [[Clustering Evaluation Metrics]]

---

## 8. Computational Complexity

Per iteration:

$$
O(nkd)
$$

Where:
- n = number of points
- k = clusters
- d = dimensions

Scales well for moderate datasets.

---

## 9. Strengths

- Simple
- Fast
- Scalable
- Easy to interpret
- Works well for spherical clusters

---

## 10. Weaknesses

- Requires choosing K
- Sensitive to initialization
- Sensitive to scaling
- Fails for non-convex clusters
- Sensitive to outliers

---

## 11. Failure Cases

K-Means fails when:

- Clusters are non-spherical
- Clusters vary greatly in size
- Data is high-dimensional
- Outliers distort centroids

Better alternatives:
- [[DBSCAN]]
- [[Hierarchical Clustering]]

---

## 12. K-Means and High Dimensions

In high dimensions:

- Distances become similar
- Cluster separation weakens
- Noise dominates

Dimensionality reduction often helps.

🔗 Related:
- [[Curse of Dimensionality]]
- [[Principal Component Analysis]]
- [[UMAP]]

---

## 13. K-Means vs Other Clustering Methods

| Method | Shape Assumption | Density-Based | Hierarchical | Scales Well |
|----------|----------------|---------------|--------------|-------------|
| K-Means | Spherical | ❌ | ❌ | ✅ |
| DBSCAN | Arbitrary | ✅ | ❌ | Moderate |
| Hierarchical | Flexible | ❌ | ✅ | Slower |

---

## 14. K-Means and Bias–Variance

Low K:
- High bias
- Under-clustering

High K:
- Low bias
- High variance
- Over-segmentation

K controls complexity.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 15. K-Means and Distance

Uses:
- Euclidean distance

Changing metric changes behavior.

Not ideal for:
- Cosine similarity problems
- Correlated features (unless transformed)

🔗 Related:
- [[Distance-Based Models — MOC]]

---

## 16. Variants of K-Means

- Mini-batch K-Means (large datasets)
- K-Medoids (robust to outliers)
- Spherical K-Means (cosine similarity)

---

## 17. When K-Means Works Well

- Clear, well-separated clusters
- Low-to-moderate dimensions
- Numeric continuous features
- Similar cluster sizes

---

## 18. When K-Means Is a Bad Idea

- Non-convex clusters
- Strong density variation
- Heavy outliers
- Categorical data without encoding

---

## 19. Relationship to Other Concepts

K-Means connects strongly to:

- [[Distance-Based Models — MOC]]
- [[Distance Metrics — MOC]]
- [[Clustering Evaluation Metrics]]
- [[Curse of Dimensionality]]
- [[Principal Component Analysis]]
- [[Bias–Variance Tradeoff]]

---

## 20. Why K-Means Matters

K-Means teaches:

- Optimization via coordinate descent
- Geometric partitioning
- How distance defines structure
- How assumptions shape outcomes

It is the canonical example of:
> Simple model + strong geometric bias.
