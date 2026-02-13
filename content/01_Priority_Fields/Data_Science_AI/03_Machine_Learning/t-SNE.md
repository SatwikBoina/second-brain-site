---
type: algorithm
domain: machine-learning
category: dimensionality-reduction
model_family: nonlinear
supervision: unsupervised
primary_use: visualization
status: evergreen
---

# t-SNE (t-Distributed Stochastic Neighbor Embedding)

> t-SNE is a **nonlinear dimensionality reduction technique** designed primarily for **visualizing high-dimensional data** by preserving **local neighborhood structure**.

---

## 1. One-Line Intuition

> t-SNE places points in low dimensions so that **points that are close in high dimensions stay close**, even if global structure is distorted.

---

## 2. Why t-SNE Exists

High-dimensional data:
- Is impossible to visualize directly
- Suffers from distance concentration
- Hides cluster structure

t-SNE exists to:
- Reveal local clusters
- Visualize embeddings
- Diagnose representation quality

🔗 Related:
- [[Curse of Dimensionality]]
- [[Dimensionality Reduction — MOC]]

---

## 3. What t-SNE Is (and Is Not)

### What it IS:
- A visualization technique
- A local-structure preserving method
- A diagnostic tool

### What it is NOT:
- A feature extractor for modeling
- A global structure preserver
- A clustering algorithm

> t-SNE is for **seeing**, not **learning**.

---

## 4. Core Idea

t-SNE works by:

1. Converting distances in high dimensions into **probabilities of similarity**
2. Doing the same in low dimensions
3. Minimizing the mismatch between these probability distributions

Close points matter a lot.  
Far points matter very little.

---

## 5. High-Dimensional Similarities

In high dimensions:
- Similarity between points is modeled using **Gaussian distributions**
- Each point has its own local neighborhood scale

This adapts to varying densities.

---

## 6. Low-Dimensional Similarities

In low dimensions:
- Similarities are modeled using a **Student’s t-distribution**
- Heavy tails allow distant points to repel strongly

This prevents points from collapsing into the center.

---

## 7. Objective Function (High-Level)

t-SNE minimizes:

\[
KL(P \parallel Q)
\]

Where:
- \(P\) = similarity distribution in high dimensions
- \(Q\) = similarity distribution in low dimensions

This is **asymmetric**:
- Preserving neighbors is prioritized
- Global distances are sacrificed

🔗 Related:
- [[Information Theory — MOC]]

---

## 8. Geometric Intuition

t-SNE behaves like:
- Nearby points connected by springs
- Distant points weakly repelling each other

Local neighborhoods are protected.  
Global geometry is flexible.

---

## 9. Perplexity (Critical Hyperparameter)

Perplexity controls:
- Effective number of neighbors
- Local vs slightly-global view

Typical values:
- 5–50

Low perplexity:
- Very local clusters

High perplexity:
- Smoother, broader structure

🔗 Related:
- [[Hyperparameter Tuning — MOC]]

---

## 10. t-SNE and PCA (Important Relationship)

Common workflow:
- PCA → t-SNE

Why?
- PCA removes noise
- Reduces dimensionality
- Makes t-SNE faster and more stable

🔗 Related:
- [[Principal Component Analysis]]

---

## 11. t-SNE vs PCA vs LDA

| Aspect | PCA | LDA | t-SNE |
|---|---|---|---|
| Supervision | ❌ | ✅ | ❌ |
| Linear | ✅ | ✅ | ❌ |
| Preserves | Variance | Class separation | Local neighborhoods |
| Use case | Compression | Classification | Visualization |
| Global structure | ✅ | Partial | ❌ |

---

## 12. Interpretation Rules (Very Important)

When reading t-SNE plots:

- ❌ Do NOT interpret distances between clusters
- ❌ Do NOT compare cluster sizes
- ❌ Do NOT infer density quantitatively
- ✅ Look for local grouping
- ✅ Compare relative neighborhood mixing

Most t-SNE misuse comes from **over-interpretation**.

---

## 13. t-SNE and Clustering

t-SNE:
- Makes clusters look more separated than they really are
- Can create apparent clusters even in continuous data

Never:
> Run clustering on t-SNE output and trust it blindly.

---

## 14. Computational Properties

t-SNE is:
- Computationally expensive
- Sensitive to initialization
- Non-deterministic (unless seeded)

Not suitable for:
- Large-scale production pipelines
- Real-time use

---

## 15. Failure Modes

- ❌ Over-interpreting global geometry
- ❌ Wrong perplexity
- ❌ No PCA preprocessing
- ❌ Using t-SNE features for downstream models
- ❌ Comparing different t-SNE runs directly

---

## 16. When t-SNE Works Well

- Inspecting embeddings
- Debugging representations
- Visualizing clusters
- Exploring data structure

Common in:
- NLP embeddings
- Computer vision features
- Graph embeddings

🔗 Related:
- [[Natural Language Processing MOC]]
- [[Computer Vision MOC]]
- [[Graph Machine Learning]]

---

## 17. When t-SNE Is a Bad Idea

- Feature engineering
- Model input
- Quantitative analysis
- Preserving global geometry

---

## 18. Relationship to Other Concepts

t-SNE connects strongly to:

- [[Dimensionality Reduction — MOC]]
- [[Curse of Dimensionality]]
- [[Principal Component Analysis]]
- [[Information Theory — MOC]]
- [[Hyperparameter Tuning — MOC]]
- [[Error Analysis]]

---

## 19. Why t-SNE Matters

t-SNE explains:

- Why high-dimensional intuition fails
- Why visualization is hard
- Why local structure is often what matters
- Why dimensionality reduction is not one-size-fits-all

It is a **microscope**, not a map.

---

## Usage Notes

- Use t-SNE only for visualization
- Always try multiple perplexities
- Preprocess with PCA
- Never treat plots as ground truth
- Ask: *what local structure is being revealed?*
