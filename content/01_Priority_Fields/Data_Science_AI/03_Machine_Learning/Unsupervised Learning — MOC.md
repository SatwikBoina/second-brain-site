# 📌 MOC — Unsupervised Learning

> Central hub for **Unsupervised Learning** in Machine Learning.
> Unsupervised learning focuses on discovering **structure, patterns, and representations** in data **without labeled outputs**.

---

## 1. Core Idea

In unsupervised learning, we observe only:

$X = \{x_1, x_2, \dots, x_n\}$

There is **no target variable**.

The goal is to uncover:
- Structure
- Similarity
- Latent factors
- Density
- Anomalies

Unsupervised learning answers:
> *What is going on in the data?*

---

## 2. Why Unsupervised Learning Matters

Unsupervised learning is essential because:

- Labels are expensive or unavailable
- Structure often exists before labels
- Representation learning improves downstream tasks
- Exploration precedes prediction

Many supervised models **depend on unsupervised ideas**.

---

## 3. Main Families of Unsupervised Learning

---

## 3.1 Clustering

Goal:
- Group similar data points together

Key question:
> *Which points belong together?*

**Algorithms**:
- [[k-Means Clustering]]
- [[Hierarchical Clustering]]
- [[DBSCAN]]
- [[Gaussian Mixture Models]]

🔗 Related:
- [[Distance Based Models — MOC]]

---

## 3.2 Dimensionality Reduction / Representation Learning

Goal:
- Reduce dimensionality while preserving structure

Key question:
> *What is the essential representation of the data?*

Examples:
- [[Dimensionality Reduction — MOC]]
- [[Principal Component Analysis]]
- [[t-SNE]]
- [[UMAP]]
- [[Autoencoders]]

---

## 3.3 Density Estimation

Goal:
- Estimate the underlying data distribution

Key question:
> *How likely is a data point?*

Examples:
- [[Kernel Density Estimation]]
- [[Gaussian Mixture Models]]
- [[Normalizing Flows]]

🔗 Related:
- [[Probabilistic Models — MOC]]

---

## 3.4 Anomaly / Outlier Detection

Goal:
- Identify rare or unusual observations

Key question:
> *What does not belong?*

Examples:
- [[Isolation Forest]]
- [[One-Class SVM]]
- [[Local Outlier Factor]]

🔗 Related:
- [[Outliers]]

---

## 3.5 Topic Modeling

Goal:
- Discover latent themes in documents

Key question:
> *What topics generate this text corpus?*

Examples:
- [[Latent Dirichlet Allocation]]
- [[NMF]]

---

## 3.6 Association Rule Mining

Goal:
- Discover co-occurrence patterns

Key question:
> *What items tend to appear together?*

Examples:
- [[Apriori Algorithm]]
- [[FP-Growth]]

---

## 4. Unsupervised Learning vs Supervised Learning

| Aspect | Supervised | Unsupervised |
|----|----|----|
| Labels | Required | Not required |
| Objective | Predict target | Discover structure |
| Evaluation | Clear metrics | Often ambiguous |
| Interpretability | Easier | Harder |

🔗 Related:
- [[Supervised Learning — MOC]]

---

## 5. Evaluation Challenges in Unsupervised Learning

Key difficulty:
> There is no “ground truth”.

Evaluation relies on:
- Internal metrics
- Stability
- Visual inspection
- Downstream task performance

🔗 Related:
- [[Clustering Evaluation Metrics]]

---

## 6. Role of Distance and Similarity

Most unsupervised methods rely on:
- Distance metrics
- Similarity measures
- Geometry of data

Feature scaling is critical.

🔗 Related:
- [[Feature Scaling]]
- [[Distance-Based Models — MOC]]

---

## 7. Unsupervised Learning and Bias–Variance

- Strong assumptions → high bias
- Flexible models → high variance

Unsupervised learning often encodes **strong inductive biases**.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 8. Unsupervised Learning as Preprocessing

Unsupervised methods are often used to:
- Create features
- Reduce noise
- Initialize models
- Improve supervised learning

Examples:
- PCA before regression
- Autoencoder embeddings

---

## 9. Probabilistic View of Unsupervised Learning

Many unsupervised models are probabilistic:
- GMM
- LDA
- KDE

They model:
$P(X)$

🔗 Related:
- [[Probabilistic Models — MOC]]

---

## 10. Common Pitfalls

- ❌ Assuming clusters are “real”
- ❌ Over-interpreting 2D visualizations
- ❌ Ignoring scaling and distance
- ❌ Treating unsupervised results as truth

Unsupervised learning is **exploratory, not authoritative**.

---

## 11. When Unsupervised Learning Works Best

- Exploratory analysis
- Pattern discovery
- Representation learning
- Anomaly detection
- Label-scarce domains

---

## 12. When It Works Poorly

- Very noisy data
- High dimensionality without structure
- When evaluation requires ground truth

---

## 13. Relationship to Other Concepts

Unsupervised learning connects strongly to:

- [[Dimensionality Reduction — MOC]]
- [[Clustering]]
- [[Outliers]]
- [[Representation Learning]]
- [[Neural Networks — MOC]]

---

## 14. How Unsupervised Learning Fits in ML


It is the **exploration and structure-discovery arm** of ML.

---

## Usage Rules

- This MOC is a conceptual + navigational hub
- Algorithms live in separate notes
- Focus on *what structure is discovered*
- Avoid treating results as ground truth
