# 📌 MOC — Dimensionality Reduction

> Central hub for **Dimensionality Reduction** in Machine Learning.
> Dimensionality reduction techniques transform high-dimensional data into a lower-dimensional representation while preserving important structure, information, or relationships.

---

## 1. Core Idea

High-dimensional data causes problems:

- Curse of dimensionality
- Overfitting
- High variance
- Poor distance metrics
- Visualization difficulty

Dimensionality reduction asks:
> *What is the smallest representation that still captures what matters?*

---

## 2. Why Dimensionality Reduction Matters

Reducing dimensions helps to:
- Improve generalization
- Reduce noise
- Speed up training
- Improve distance-based models
- Enable visualization
- Improve interpretability (sometimes)

Dimensionality reduction is **model-enabling**, not cosmetic.

---

## 3. Feature Selection vs Feature Extraction

Important distinction:

| Approach | What Happens |
|-------|--------------|
| Feature Selection | Choose subset of original features |
| Feature Extraction | Create new lower-dimensional features |

Dimensionality reduction usually refers to **feature extraction**.

🔗 Related:
- [[Feature Selection]]
- [[Feature Engineering]]

---

## 4. Curse of Dimensionality

As dimensions increase:
- Data becomes sparse
- Distances lose meaning
- Models overfit easily

Dimensionality reduction fights this directly.

🔗 Related:
- [[Curse of Dimensionality]]
- [[k-NN Classifier]]

---

## 5. Types of Dimensionality Reduction

---

### 5.1 Linear Dimensionality Reduction

Assume data lies in a **linear subspace**.

Examples:
- [[Principal Component Analysis]]
- [[Linear Discriminant Analysis]]

Characteristics:
- Fast
- Interpretable
- Limited expressiveness

---

### 5.2 Non-Linear Dimensionality Reduction (Manifold Learning)

Assume data lies on a **non-linear manifold**.

Examples:
- [[t-SNE]]
- [[UMAP]]
- [[Isomap]]
- [[Locally Linear Embedding]]

Characteristics:
- Captures complex structure
- Often used for visualization
- Poor inverse mapping

---

### 5.3 Probabilistic Dimensionality Reduction

Model data generation probabilistically.

Examples:
- [[Probabilistic PCA]]
- [[Factor Analysis]]
- [[Autoencoders]] (probabilistic variants)

🔗 Related:
- [[Probabilistic Models — MOC]]

---

### 5.4 Neural Network–Based Methods

Learn representations via deep models.

Examples:
- [[Autoencoders]]
- Variational Autoencoders

Characteristics:
- Highly expressive
- Data-hungry
- Less interpretable

🔗 Related:
- [[Neural Networks — MOC]]

---

## 6. Supervised vs Unsupervised Reduction

### Unsupervised
- Ignore labels
- Preserve variance or geometry

Example:
- PCA, t-SNE

---

### Supervised
- Use labels
- Preserve class separation

Example:
- LDA

---

## 7. Dimensionality Reduction and Bias–Variance

- Fewer dimensions → ↑ bias
- Fewer dimensions → ↓ variance

Dimensionality reduction is a **regularization tool**.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Regularization — MOC]]

---

## 8. Dimensionality Reduction and Distance Metrics

Distance-based models depend heavily on:
- Meaningful distances
- Low effective dimensionality

Dimensionality reduction often improves:
- k-NN
- Clustering

🔗 Related:
- [[Distance Based Models — MOC]]

---

## 9. Dimensionality Reduction and Visualization

Reducing to:
- 2D or 3D enables human understanding

Used for:
- Exploratory data analysis
- Cluster inspection
- Model debugging

⚠️ Visualization ≠ faithful modeling

---

## 10. Dimensionality Reduction and Information Loss

Trade-off:
- Reduce dimensions
- Lose some information

Key question:
> *Which information are we willing to lose?*

Different methods preserve different properties:
- Variance
- Distances
- Neighborhoods
- Class separation

---

## 11. When Dimensionality Reduction Helps Most

- High-dimensional datasets
- Distance-based models
- Noisy features
- Visualization needs
- Limited data

---

## 12. When It Helps Less (or Hurts)

- Already low-dimensional data
- Strongly interpretable features
- Tree-based models (often)
- When inverse mapping matters

---

## 13. Common Mistakes

- ❌ Applying reduction before train–test split  
- ❌ Using t-SNE as a feature generator  
- ❌ Ignoring scaling requirements  
- ❌ Assuming variance = importance  

Dimensionality reduction is **context-sensitive**.

---

## 14. Relationship to Other ML Concepts

Dimensionality reduction connects to:

- [[Feature Scaling]]
- [[Outliers]]
- [[Clustering]]
- [[Visualization]]
- [[Model Selection]]

---

## 15. Why Dimensionality Reduction Matters

Dimensionality reduction explains:

- Why simple models start working
- Why distance metrics fail in high dimensions
- Why visualization is possible
- Why representation learning matters

It is the **geometry layer of machine learning**.

---

## Usage Rules

- This MOC is a conceptual + navigational hub
- Each technique lives in its own note
- Do NOT mix visualization tools with modeling tools
- Always ask: *what structure is preserved?*
