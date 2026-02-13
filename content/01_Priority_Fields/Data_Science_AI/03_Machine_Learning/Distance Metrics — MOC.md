# 📌 MOC — Distance Metrics

> Distance metrics define how similarity between data points is measured.
> In many ML algorithms, distance determines structure, prediction, and clustering behavior.

---

## 1. Core Idea

A distance metric is a function:

$d(x, y)$

that measures how far two points are in feature space.

A valid metric must satisfy:

1. Non-negativity  
2. Identity of indiscernibles  
3. Symmetry  
4. Triangle inequality  

Distance choice shapes model behavior.

🔗 Related:
- [[Distance-Based Models — MOC]]

---

# 2. Why Distance Matters

Distance determines:

- Neighbor relationships
- Cluster assignments
- Density estimation
- Anomaly detection
- Manifold geometry
- Kernel similarity

Poor metric → distorted geometry → poor learning.

---

# 3. Lp Norm Family (Minkowski Distance)

General form:

$$
d(x,y) = \left(\sum |x_i - y_i|^p\right)^{1/p}
$$

---

## 3.1 Euclidean Distance (L2)

$$
\sqrt{\sum (x_i - y_i)^2}
$$

Assumes:
- Continuous features
- Equal scaling
- Isotropic geometry

Used in:
- K-Means
- PCA
- k-NN (default)

---

## 3.2 Manhattan Distance (L1)

$$
\sum |x_i - y_i|
$$

More robust to:
- Outliers
- Sparse high-dimensional data

---

## 3.3 Chebyshev Distance (L∞)

$$
\max |x_i - y_i|
$$

Sensitive to:
- Largest coordinate difference

---

# 4. Cosine Distance / Similarity


$$\cos(\theta) = \frac{x \cdot y}{||x|| ||y||}
$$

Measures:
- Angle between vectors
- Directional similarity

Best for:
- Text data
- High-dimensional sparse data

🔗 Related:
- [[Natural Language Processing MOC]]

---

# 5. Mahalanobis Distance

$$
d(x,y) = \sqrt{(x - y)^T \Sigma^{-1} (x - y)}
$$

Accounts for:
- Feature correlation
- Covariance structure

Scale-invariant.

Used in:
- Outlier detection
- Gaussian models

🔗 Related:
- [[Principal Component Analysis]]

---

# 6. Hamming Distance

Counts:
- Number of positions where two vectors differ

Used for:
- Binary data
- Categorical encoding
- Error correction

---

# 7. Jaccard Distance

$$
1 - \frac{|A \cap B|}{|A \cup B|}
$$

Used for:
- Set similarity
- Sparse binary data
- Market basket analysis

🔗 Related:
- [[Apriori Algorithm]]
- [[FP-Growth]]

---

# 8. Edit Distance (Levenshtein)

Measures:
- Minimum operations to convert one string to another

Used in:
- NLP
- Spell correction
- DNA sequence analysis

🔗 Related:
- [[Natural Language Processing — MOC]]

---

# 9. Wasserstein Distance (Earth Mover’s Distance)

Measures:
- Cost of transforming one distribution into another

Used in:
- Generative models
- Distribution comparison
- Optimal transport

🔗 Related:
- [[Probabilistic Models — MOC]]

---

# 10. Kernel-Induced Distance

Some algorithms define similarity via kernels:

$$
K(x, y)
$$

Distance can be derived from kernel space.

Used in:
- [[Support Vector Machine]]
- Spectral clustering

🔗 Related:
- [[Kernel Methods — MOC]]

---

# 11. Distance in High Dimensions

In high-dimensional spaces:

- Distances become similar
- Contrast decreases
- Nearest ≈ farthest

This is the **distance concentration problem**.

🔗 Related:
- [[Curse of Dimensionality]]

---

# 12. Feature Scaling and Distance

Distance is sensitive to scale.

Example:
- Age (0–100)
- Income (0–1,000,000)

Income dominates unless scaled.

🔗 Related:
- [[Feature Scaling]]

---

# 13. Choosing a Distance Metric

Depends on:

- Data type (continuous, binary, text)
- Feature scaling
- Distribution shape
- Correlation structure
- Sparsity
- Application goal

---

# 14. Distance vs Similarity

Some algorithms use similarity instead of distance:

Similarity high → close  
Distance low → close  

Conversion:

$$
Similarity = 1 / (1 + Distance)
$$

Or via kernels.

---

# 15. Relationship to Algorithms

Distance metrics power:

- [[k-NN Classifier]]
- [[k-NN Regressor]]
- [[K-Means]]
- [[DBSCAN]]
- [[Hierarchical Clustering]]
- [[Isomap]]
- [[LLE]]
- [[t-SNE]]
- [[UMAP]]
- [[Distance-Based Models — MOC]]

Distance defines geometry.

---

# 16. Strengths and Limitations

Strengths:
- Simple
- Interpretable
- Flexible

Limitations:
- Sensitive to irrelevant features
- Poor scaling behavior
- High-dimensional breakdown

---

# 17. Why Distance Metrics Matter

Distance metrics explain:

- Why scaling is critical
- Why high dimensions are hard
- Why clustering changes with metric
- Why representation learning helps

Distance is the geometric foundation of many ML systems.
