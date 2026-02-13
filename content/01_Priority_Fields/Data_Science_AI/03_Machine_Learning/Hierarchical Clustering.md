---
type: algorithm
domain: machine-learning
category: unsupervised-learning
model_family: distance-based
primary_use: clustering
status: evergreen
---

# Hierarchical Clustering

> Hierarchical Clustering builds a hierarchy of clusters either by successively merging smaller clusters (agglomerative) or splitting larger clusters (divisive).

---

## 1. One-Line Intuition

> Instead of forcing data into K clusters immediately, hierarchical clustering builds a tree of cluster merges and lets you decide where to cut.

---

## 2. Two Types of Hierarchical Clustering

---

## 2.1 Agglomerative (Bottom-Up)

Most common.

Process:

1. Start with each point as its own cluster  
2. Merge the two closest clusters  
3. Repeat until only one cluster remains  

---

## 2.2 Divisive (Top-Down)

Less common.

Process:

1. Start with all points in one cluster  
2. Recursively split clusters  

---

## 3. Core Idea

Hierarchical clustering relies on:

- Distance between clusters
- A linkage criterion

Distance between clusters ≠ distance between points.

🔗 Related:
- [[Distance Metrics — MOC]]

---

# 4. Linkage Criteria

Linkage determines how cluster distance is computed.

---

## 4.1 Single Linkage

Distance = minimum distance between points of two clusters.

Behavior:
- Can form chain-like clusters
- Sensitive to noise

---

## 4.2 Complete Linkage

Distance = maximum distance between cluster points.

Behavior:
- Produces compact clusters
- Sensitive to outliers

---

## 4.3 Average Linkage

Distance = average pairwise distance.

Balanced approach.

---

## 4.4 Ward Linkage

Minimizes increase in total variance when merging clusters.

Closest to:
- K-Means behavior

---

# 5. Dendrogram

Hierarchical clustering produces a:

> Dendrogram — a tree representing cluster merges.

Height of merge:
- Distance at which clusters combine.

You choose K by:
- Cutting the tree at a chosen height.

---

## 6. Geometric Interpretation

Unlike K-Means:

- No assumption of spherical clusters
- No centroid representation required
- Works with arbitrary distance metrics

But still distance-driven.

---

## 7. Computational Complexity

Agglomerative clustering:

$$
O(n^3)
$$

Optimized implementations:

$$
O(n^2)
$$

Slower than K-Means for large datasets.

---

## 8. Strengths

- No need to choose K upfront
- Flexible cluster shapes
- Produces full hierarchy
- Works with arbitrary distance metrics

---

## 9. Weaknesses

- Computationally expensive
- Sensitive to noise (especially single linkage)
- Irreversible merges (greedy)
- Poor scalability

---

## 10. Failure Modes

- ❌ Poor linkage choice
- ❌ High-dimensional data
- ❌ Distance concentration
- ❌ Early bad merge cannot be undone

Hierarchical clustering is greedy.

---

## 11. Hierarchical vs K-Means

| Aspect | K-Means | Hierarchical |
|----------|----------|--------------|
| Need K upfront | Yes | No |
| Scalability | Better | Worse |
| Cluster shape | Spherical | Flexible |
| Output | Partition | Tree |
| Reversible decisions | Yes (reassignment) | No |

K-Means = partition  
Hierarchical = structure

---

## 12. When Hierarchical Clustering Works Well

- Small to medium datasets
- Exploratory analysis
- Need full cluster structure
- Non-spherical clusters

---

## 13. When It’s a Bad Idea

- Very large datasets
- High-dimensional sparse data
- Real-time applications

---

## 14. Hierarchical Clustering and Distance

Choice of distance strongly affects outcome.

Example:
- Euclidean → geometric clusters
- Cosine → text clusters
- Manhattan → robust clustering

🔗 Related:
- [[Distance-Based Models — MOC]]

---

## 15. Relationship to Other Concepts

Hierarchical clustering connects to:

- [[Distance-Based Models — MOC]]
- [[Distance Metrics — MOC]]
- [[Clustering Evaluation Metrics]]
- [[Curse of Dimensionality]]
- [[K-Means]]
- [[DBSCAN]]

---

## 16. Bias–Variance Perspective

Few large clusters:
- High bias

Many small clusters:
- High variance

Cut height controls complexity.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 17. Variants

- Agglomerative clustering
- Divisive clustering
- BIRCH (scalable variant)
- Spectral hierarchical clustering

---

## 18. Why Hierarchical Clustering Matters

It teaches:

- Structure discovery
- Greedy clustering
- Importance of linkage choice
- Why clustering is ambiguous

It gives a *multi-resolution view* of data.

