---
type: algorithm
domain: machine-learning
category: dimensionality-reduction
model_family: manifold-learning
supervision: unsupervised
primary_use: visualization_and_embedding
status: evergreen
---

# UMAP (Uniform Manifold Approximation and Projection)

> UMAP is a **nonlinear dimensionality reduction technique** based on manifold learning and topological principles, designed to preserve both **local and some global structure** in data.

---

## 1. One-Line Intuition

> UMAP builds a graph representing local relationships in high dimensions and optimizes a low-dimensional embedding that preserves that graph structure.

---

## 2. Why UMAP Exists

t-SNE:
- Preserves local structure well
- Distorts global structure
- Computationally expensive

Isomap:
- Preserves global geometry
- Sensitive to noise
- Less scalable

UMAP was designed to:
- Preserve local AND some global structure
- Scale better
- Be faster
- Be usable beyond visualization

🔗 Related:
- [[t-SNE]]
- [[Isomap]]
- [[Principal Component Analysis]]

---

## 3. Core Assumptions (Manifold Hypothesis)

UMAP assumes:

> Data lies on a low-dimensional manifold embedded in high-dimensional space.

It also assumes:
- The manifold is locally connected
- Distance reflects meaningful similarity

🔗 Related:
- [[Curse of Dimensionality]]

---

## 4. High-Level Algorithm Steps

UMAP has two main phases:

---

### Step 1: Construct Fuzzy Topological Graph

- Build a k-nearest neighbor graph
- Estimate local distances
- Convert into a weighted graph
- Represent local connectivity probabilistically

This captures manifold structure.

---

### Step 2: Optimize Low-Dimensional Embedding

- Initialize points randomly
- Minimize cross-entropy between:
  - High-dimensional graph
  - Low-dimensional graph

This preserves structure via attraction and repulsion forces.

🔗 Related:
- [[Information Theory — MOC]]

---

## 5. Key Hyperparameters

---

### 5.1 n_neighbors

Controls:
- Size of local neighborhood
- Balance between local vs global structure

Small value:
- Focus on local clusters

Large value:
- More global continuity

---

### 5.2 min_dist

Controls:
- How tightly points can cluster

Low value:
- Tighter clusters

High value:
- More spread-out embedding

---

### 5.3 n_components

- Dimensionality of output space
- Usually 2 or 3 for visualization
- Can be higher for embedding

🔗 Related:
- [[Hyperparameter Tuning — MOC]]

---

## 6. UMAP vs t-SNE

| Aspect | t-SNE | UMAP |
|---|---|---|
| Speed | Slower | Faster |
| Global structure | Poor | Better |
| Scalability | Limited | Better |
| Hyperparameters | Perplexity | n_neighbors, min_dist |
| Embedding reuse | Weak | Stronger |

UMAP often preserves **cluster continuity** better.

---

## 7. UMAP vs Isomap

| Aspect | Isomap | UMAP |
|---|---|---|
| Focus | Global geodesic distances | Local fuzzy topology |
| Noise sensitivity | High | Lower |
| Scalability | Moderate | High |
| Robustness | Sensitive to graph | More stable |

UMAP is generally more practical.

---

## 8. UMAP vs PCA

| Aspect | PCA | UMAP |
|---|---|---|
| Linear | ✅ | ❌ |
| Preserves variance | ✅ | ❌ |
| Preserves manifold | ❌ | ✅ |
| Fast | Very | Fast |
| Interpretability | Moderate | Low |

PCA is for compression.  
UMAP is for nonlinear structure discovery.

---

## 9. Geometric Intuition

UMAP behaves like:

- Attractive forces between neighbors
- Repulsive forces between non-neighbors

Points move until:
- Local graph structure is preserved
- Embedding stabilizes

Similar to t-SNE, but more globally aware.

---

## 10. Strengths of UMAP

- Fast
- Scalable
- Preserves cluster shape better
- Can embed new points (with some implementations)
- Works well on embeddings

---

## 11. Weaknesses of UMAP

- Sensitive to hyperparameters
- Still distorts some global distances
- Can hallucinate clusters
- Embedding not unique

Visualization must be interpreted carefully.

---

## 12. When UMAP Works Well

- Visualizing high-dimensional embeddings
- Exploring clusters
- Preprocessing for clustering
- NLP / CV embedding diagnostics

🔗 Related:
- [[Natural Language Processing MOC]]
- [[Computer Vision MOC]]

---

## 13. When UMAP Is a Bad Idea

- Feature engineering for prediction
- Precise geometric analysis
- When interpretability of axes matters
- Small noisy datasets

---

## 14. UMAP and Clustering

UMAP often:
- Makes clusters visually separable
- Improves downstream clustering performance

But:
> Clustering on UMAP output must be validated carefully.

---

## 15. UMAP and Curse of Dimensionality

UMAP helps because:
- It relies on local neighborhoods
- Avoids relying purely on Euclidean distance

But:
- It does not eliminate the curse
- It works under manifold assumptions

---

## 16. Relationship to Other Concepts

UMAP connects strongly to:

- [[Dimensionality Reduction — MOC]]
- [[Curse of Dimensionality]]
- [[t-SNE]]
- [[Isomap]]
- [[Principal Component Analysis]]
- [[Graph Machine Learning]]
- [[Information Theory — MOC]]

---

## 17. Why UMAP Matters

UMAP explains:

- Why manifold learning works
- Why local topology matters
- Why visualization is nonlinear
- Why embeddings reveal structure

It is the **modern practical manifold learner**.

---

## Usage Notes

- Try PCA before UMAP
- Tune n_neighbors carefully
- Use for visualization or embedding exploration
- Do not over-interpret distances
- Ask: *what local topology is being preserved?*


PCA (linear variance)
LDA (supervised linear)
Isomap (global nonlinear geometry)
t-SNE (local nonlinear visualization)
UMAP (local + partial global topology)  ← this
