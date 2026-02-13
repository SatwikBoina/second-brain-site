---
type: algorithm
domain: machine-learning
category: unsupervised-learning
model_family: density-based
primary_use: clustering
status: evergreen
---

# DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

> DBSCAN is a density-based clustering algorithm that groups points that are densely packed together and labels sparse regions as noise.

---

## 1. One-Line Intuition

> Clusters are regions of high density separated by regions of low density.

---

## 2. Why DBSCAN Exists

K-Means assumes:
- Spherical clusters
- Equal cluster size
- Every point belongs to some cluster

Hierarchical clustering:
- Sensitive to linkage
- Does not explicitly detect noise

DBSCAN solves:
- Arbitrary cluster shapes
- Noise detection
- No need to specify K

🔗 Related:
- [[K-Means]]
- [[Hierarchical Clustering]]

---

## 3. Core Concepts

DBSCAN defines clusters using two parameters:

- ε (epsilon) → neighborhood radius
- minPts → minimum points to form dense region

---

## 4. Point Types

---

### 4.1 Core Point

A point with at least `minPts` neighbors within ε radius.

---

### 4.2 Border Point

Not a core point, but within ε of a core point.

---

### 4.3 Noise Point

Neither core nor border.

---

## 5. Algorithm Steps

1. Pick an unvisited point.
2. If it is a core point:
   - Start a new cluster.
   - Recursively add density-reachable points.
3. If not:
   - Mark as noise (may later become border).

Clusters grow by density connectivity.

---

## 6. Density Connectivity

Two points are connected if:

- They are within ε
- There exists a chain of core points linking them

This allows:
> Arbitrary-shaped clusters.

---

## 7. Geometric Interpretation

K-Means:
- Divides space into convex regions.

DBSCAN:
- Finds blobs of high density.
- Ignores empty regions.

Works well for:
- Crescent shapes
- Non-linear clusters

---

## 8. Key Hyperparameters

---

### 8.1 ε (epsilon)

Defines neighborhood radius.

Too small:
- Many noise points

Too large:
- Merges clusters

---

### 8.2 minPts

Minimum number of neighbors required.

Common heuristic:
- minPts ≈ dimensionality + 1

🔗 Related:
- [[Hyperparameter Tuning — MOC]]

---

## 9. Strengths

- No need to choose K
- Detects noise
- Handles arbitrary shapes
- Works well with spatial data

---

## 10. Weaknesses

- Sensitive to ε
- Struggles with varying density
- Poor performance in high dimensions
- Distance metric dependent

---

## 11. Failure Modes

- ❌ High-dimensional data (distance concentration)
- ❌ Varying density clusters
- ❌ Poor ε choice
- ❌ Sparse data

DBSCAN assumes relatively uniform density.

🔗 Related:
- [[Curse of Dimensionality]]
- [[Distance Metrics — MOC]]

---

## 12. DBSCAN vs K-Means vs Hierarchical

| Aspect | K-Means | Hierarchical | DBSCAN |
|----------|----------|--------------|--------|
| Need K | Yes | No | No |
| Noise detection | No | No | Yes |
| Cluster shape | Spherical | Flexible | Arbitrary |
| Density-based | No | No | Yes |
| Scalability | Good | Moderate | Moderate |

DBSCAN is best when:
> Cluster shape is irregular.

---

## 13. Computational Complexity

Average case:
\[
O(n \log n)
\]

Worst case:
\[
O(n^2)
\]

Depends on:
- Neighbor search efficiency.

---

## 14. Variants

- OPTICS (handles varying density)
- HDBSCAN (hierarchical density clustering)

These address DBSCAN’s density sensitivity.

---

## 15. DBSCAN and Distance

Distance defines:

- Neighborhoods
- Density estimation
- Cluster connectivity

Euclidean is common,
but cosine or Manhattan can be used.

🔗 Related:
- [[Distance-Based Models — MOC]]

---

## 16. When DBSCAN Works Well

- Spatial data
- Non-spherical clusters
- Datasets with noise
- Moderate dimensionality

---

## 17. When DBSCAN Is a Bad Idea

- Very high dimensions
- Clusters with different densities
- Small datasets with sparse sampling

---

## 18. Relationship to Other Concepts

DBSCAN connects strongly to:

- [[Distance-Based Models — MOC]]
- [[Distance Metrics — MOC]]
- [[Clustering Evaluation Metrics]]
- [[Curse of Dimensionality]]
- [[K-Means]]
- [[Hierarchical Clustering]]

---

## 19. Why DBSCAN Matters

DBSCAN teaches:

- Density-based reasoning
- Noise detection in clustering
- Why geometry alone is insufficient
- Importance of neighborhood structure

It completes the core clustering paradigms:

- Partition-based
- Hierarchical
- Density-based
