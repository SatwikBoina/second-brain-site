---
type: algorithm
domain: machine-learning
category: dimensionality-reduction
model_family: linear
supervision: supervised
status: evergreen
---

# Linear Discriminant Analysis (LDA)

> Linear Discriminant Analysis (LDA) is a **supervised dimensionality reduction and classification technique** that projects data onto directions that **maximize class separability**.

---

## 1. One-Line Intuition

> PCA separates points by **variance**;  
> LDA separates points by **class discrimination**.

---

## 2. Why LDA Exists

PCA ignores labels.

But in classification:
- Variance ≠ usefulness
- Low-variance directions may be highly discriminative

LDA exists to:
- Use class labels
- Reduce dimensionality
- Improve class separability
- Enable simpler classifiers

---

## 3. Core Objective

LDA finds a projection that:

- **Maximizes distance between class means**
- **Minimizes spread within each class**

In short:
> Pull classes apart, squeeze each class tight.

---

## 4. Geometric Intuition

Imagine projecting data onto a line.

A good LDA projection:
- Pushes class centers far apart
- Minimizes overlap between projected class distributions

The result is a space where classes are easier to separate linearly.

---

## 5. Statistical Intuition

LDA assumes:
- Each class is generated from a Gaussian distribution
- All classes share the same covariance matrix

Under these assumptions:
> LDA is the **optimal linear classifier**.

---

## 6. Mathematical Foundation

LDA is built on **scatter matrices**.

---

### 6.1 Within-Class Scatter Matrix \(S_W\)

Measures how spread out each class is:

$$
S_W = \sum_{k=1}^{K} \sum_{x \in C_k} (x - \mu_k)(x - \mu_k)^T
$$

---

### 6.2 Between-Class Scatter Matrix \(S_B\)

Measures how far apart class means are:

$$
S_B = \sum_{k=1}^{K} n_k (\mu_k - \mu)(\mu_k - \mu)^T
$$

---

### 6.3 Optimization Objective

LDA maximizes:

$$
\frac{|W^T S_B W|}{|W^T S_W W|}
$$

This is a **generalized eigenvalue problem**.

🔗 Related:
- [[Linear Algebra for Machine Learning — MOC]]

---

## 7. Dimensionality Limit (Important)

If there are:
- \(K\) classes

Then LDA can produce **at most \(K - 1\)** components.

This is a **hard theoretical limit**.

---

## 8. LDA as Dimensionality Reduction vs Classifier

LDA has two roles:

---

### 8.1 As Dimensionality Reduction

- Project data to \(K - 1\) dimensions
- Then apply another classifier

---

### 8.2 As a Classifier

- Decision boundaries are linear
- Equivalent to Gaussian Naive Bayes with shared covariance

---

## 9. Assumptions Behind LDA

LDA assumes:

- Linearly separable classes (in projected space)
- Gaussian class distributions
- Equal covariance matrices
- Balanced class importance (by default)

Violation of assumptions reduces effectiveness.

---

## 10. LDA vs PCA (Critical Comparison)

| Aspect | PCA | LDA |
|---|---|---|
| Supervision | ❌ Unsupervised | ✅ Supervised |
| Objective | Maximize variance | Maximize class separation |
| Uses labels | ❌ | ✅ |
| Max dimensions | min(n, d) | K − 1 |
| Best for | Compression | Classification |

🔗 Related:
- [[Principal Component Analysis]]

---

## 11. LDA and Feature Scaling

LDA is **scale-sensitive**.

- Features with large scales dominate scatter matrices
- Standardization is often required

🔗 Related:
- [[Feature Scaling]]

---

## 12. LDA and Bias–Variance Tradeoff

Effect of LDA:
- Reduces variance by lowering dimension
- Can increase bias if class structure is nonlinear

LDA is a **variance-reduction tool with supervision**.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 13. LDA in ML Pipelines

Common usage:
- Scaling → LDA → Classifier

LDA must be:
- Fit only on training data
- Placed inside pipelines

🔗 Related:
- [[Model Pipelines]]

---

## 14. LDA and Class Imbalance

Standard LDA:
- Is sensitive to class priors
- Can be biased toward majority classes

Class priors can be adjusted to mitigate this.

🔗 Related:
- [[Class Imbalance]]

---

## 15. Failure Modes

- ❌ Non-Gaussian class distributions
- ❌ Strongly nonlinear boundaries
- ❌ Heavy outliers
- ❌ Very small sample size per class
- ❌ Singular within-class scatter matrix

---

## 16. When LDA Works Well

- Moderate dimensional data
- Clearly separated classes
- Gaussian-like distributions
- As a preprocessing step for classifiers

---

## 17. When LDA Is a Bad Choice

- Highly nonlinear class boundaries
- Complex multimodal classes
- Very high-dimensional small-sample data
- When interpretability of components matters

---

## 18. Relationship to Other Concepts

LDA connects strongly to:

- [[Principal Component Analysis]]
- [[Dimensionality Reduction — MOC]]
- [[Linear Algebra for Machine Learning — MOC]]
- [[Classification — MOC]]
- [[Bias–Variance Tradeoff]]
- [[Feature Scaling]]

---

## 19. Why LDA Matters

LDA explains:

- Why labels matter in dimensionality reduction
- How class separation can be optimized linearly
- Why PCA can fail for classification
- How geometry + statistics combine in ML

It is the **cleanest example of supervised representation learning**.

---

## Usage Notes

- Always compare PCA vs LDA empirically
- Keep LDA inside pipelines
- Validate assumptions before trusting results
- Ask: *are low-variance directions class-informative?*
