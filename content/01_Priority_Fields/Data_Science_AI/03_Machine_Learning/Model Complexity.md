---
type: concept
domain: machine-learning
category: model-evaluation
status: evergreen
---

# Model Complexity

> Model complexity describes a model’s **capacity to fit patterns** in data, including both signal and noise.

---

## 1. Core Idea

Model complexity reflects **how flexible a model is**.

- Low complexity → simple models
- High complexity → flexible models

More flexibility allows learning richer patterns, but also increases the risk of learning noise.

---

## 2. What Determines Model Complexity?

Model complexity can increase due to:

- Number of parameters
- Model structure
- Feature transformations
- Degree of non-linearity
- Training freedom (lack of constraints)

Complexity is **not just parameter count**.

---

## 3. Examples Across Algorithms

| Algorithm | Complexity Driver |
|---------|------------------|
| Linear Regression | Number of features |
| Polynomial Regression | Polynomial degree |
| Decision Tree | Tree depth |
| Random Forest | Number of trees |
| Gradient Boosting | Tree depth + estimators |
| k-NN | Value of k |
| SVM | Kernel choice + C |
| Neural Networks | Layers + neurons |

---

## 4. Low Complexity Models

### Characteristics
- Strong assumptions
- Limited flexibility
- Easy to interpret

### Risks
- Underfitting
- High bias

### Examples
- Linear Regression
- Naive Bayes
- k-NN with large k

🔗 Related:
- [[Underfitting]]
- [[Bias–Variance Tradeoff]]

---

## 5. High Complexity Models

### Characteristics
- Weak assumptions
- High flexibility
- Can fit subtle patterns

### Risks
- Overfitting
- High variance

### Examples
- Deep decision trees
- Gradient boosting with many estimators
- k-NN with small k

🔗 Related:
- [[Overfitting]]
- [[Bias–Variance Tradeoff]]

---

## 6. Model Complexity vs Bias–Variance

| Complexity | Bias | Variance |
|----------|------|----------|
| Low | High | Low |
| Medium | Balanced | Balanced |
| High | Low | High |

🔗 Core concept:
- [[Bias–Variance Tradeoff]]

---

## 7. Model Complexity vs Data Size

- Small datasets → prefer low complexity
- Large datasets → higher complexity can be supported

More data **reduces variance**, not bias.

---

## 8. Controlling Model Complexity

Ways to reduce effective complexity:

- Regularization
- Pruning
- Early stopping
- Feature selection
- Simpler architectures
- Ensembling (averaging effects)

🔗 Related:
- [[Regularization — MOC]]
- [[Early Stopping]]
- [[Pruning]]

---

## 9. Measuring Model Complexity (Indirectly)

There is no single numeric measure, but proxies include:

- Training vs validation error gap
- Learning curves
- Cross-validation stability
- Number of support vectors (SVM)
- Tree depth / number of leaves

🔗 Tools:
- [[Learning Curves]]
- [[Cross Validation]]

---

## 10. Common Misconceptions

- ❌ More complex models are always better  
- ❌ More data always fixes underfitting  
- ❌ Simple models are weak models  

In practice, **appropriate complexity wins**.

---

## 11. Why Model Complexity Matters

Model complexity explains:

- Why regularization exists
- Why ensemble methods work
- Why simpler baselines often outperform complex models
- Why model selection is context-dependent

It is a **core decision axis in ML**.

---

## Usage Notes

- Link this note from all algorithm notes
- Do NOT duplicate this explanation elsewhere
- Extend via backlinks, not by editing
