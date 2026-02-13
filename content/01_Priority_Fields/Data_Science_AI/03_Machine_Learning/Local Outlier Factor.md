---
type: algorithm
domain: machine-learning
category: anomaly-detection
model_family: density-based
supervision: unsupervised
primary_use: local_anomaly_detection
status: evergreen
---

# Local Outlier Factor (LOF)

> Local Outlier Factor (LOF) detects anomalies by comparing the local density of a point to the local density of its neighbors.

---

## 1. One-Line Intuition

> A point is anomalous if it is much less dense than its neighbors.

Unlike global methods:
- LOF detects **local anomalies**.

---

## 2. Why LOF Exists

Global anomaly detection (e.g., distance threshold):
- Assumes uniform density.

But real data often has:
- Regions of varying density.

A point may:
- Be normal in a sparse region.
- Be anomalous in a dense region.

LOF handles this.

🔗 Related:
- [[Outliers]]
- [[Distance-Based Models — MOC]]

---

## 3. Core Concepts

LOF builds on k-nearest neighbors.

---

## 3.1 k-Distance

Distance to the k-th nearest neighbor.

Defines:
- Local neighborhood size.

---

## 3.2 Reachability Distance

\[
\text{reach-dist}_k(p, o) = \max(k\text{-distance}(o), d(p, o))
\]

Prevents:
- Very small distances from dominating.

---

## 3.3 Local Reachability Density (LRD)

\[
\text{LRD}(p) = \left( \frac{\sum \text{reach-dist}_k(p,o)}{|N_k(p)|} \right)^{-1}
\]

Measures:
- How dense the neighborhood around p is.

Higher LRD → denser region.

---

## 4. LOF Score

\[
LOF(p) = \frac{\sum_{o \in N_k(p)} \text{LRD}(o)}{|N_k(p)| \cdot \text{LRD}(p)}
\]

Interpretation:

- LOF ≈ 1 → normal
- LOF > 1 → anomaly
- Larger LOF → stronger anomaly

If neighbors are denser than p → p is an outlier.

---

## 5. Geometric Interpretation

Imagine:

- A dense cluster
- A point slightly away from the cluster core

Distance-based methods:
- Might classify as normal.

LOF:
- Sees neighbors are denser
- Flags as anomaly

LOF is **relative density comparison**.

---

## 6. Key Hyperparameter: k

Small k:
- Sensitive to noise
- High variance

Large k:
- Smooths density differences
- May miss local anomalies

k controls locality.

🔗 Related:
- [[Hyperparameter Tuning — MOC]]

---

## 7. Strengths

- Detects local anomalies
- Handles varying density regions
- More robust than global distance methods

---

## 8. Weaknesses

- Computationally expensive
- Sensitive to k
- Struggles in high dimensions
- Distance-metric dependent

---

## 9. Failure Modes

- ❌ High-dimensional data
- ❌ Very uniform density
- ❌ Poor k choice
- ❌ Very large datasets

Distance concentration affects LOF.

🔗 Related:
- [[Curse of Dimensionality]]
- [[Distance Metrics — MOC]]

---

## 10. LOF vs Isolation Forest

| Aspect | LOF | Isolation Forest |
|----------|------|------------------|
| Based On | Density comparison | Random isolation |
| Distance required | Yes | No |
| Handles varying density | Yes | Limited |
| High-dim robustness | Moderate | Better |
| Scalability | Moderate | High |

LOF is more sensitive to local structure.
Isolation Forest is more scalable.

---

## 11. LOF vs KDE

| Aspect | LOF | KDE |
|----------|------|------|
| Density type | Relative | Absolute |
| Locality | Yes | Global smoothing |
| Scalability | Better | Worse |
| Interpretability | Relative anomaly score | Density value |

LOF compares density; KDE estimates it.

---

## 12. Computational Complexity

Naively:

\[
O(n^2)
\]

With indexing (KD-tree, Ball-tree):

- Faster in low dimensions
- Degrades in high dimensions

---

## 13. Applications

- Fraud detection
- Network intrusion detection
- Manufacturing defect detection
- Rare behavior detection
- Healthcare anomaly detection

---

## 14. When LOF Works Well

- Data with varying density
- Moderate dimensions
- Need local anomaly detection
- Small to medium datasets

---

## 15. When LOF Is a Bad Idea

- Very high dimensions
- Extremely large datasets
- Uniform density
- Categorical-heavy data

---

## 16. Relationship to Other Concepts

LOF connects strongly to:

- [[Isolation Forest]]
- [[Kernel Density Estimation]]
- [[Gaussian Mixture Models]]
- [[Distance-Based Models — MOC]]
- [[Curse of Dimensionality]]
- [[Outliers]]

---

## 17. Why LOF Matters

LOF teaches:

- Local vs global anomaly distinction
- Density comparison
- Why neighborhood size matters
- How relative context defines abnormality

It is one of the most conceptually elegant anomaly detection methods.
