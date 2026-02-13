---
type: concept
domain: machine-learning
category: preprocessing
status: evergreen
---

# Feature Selection

> Feature selection is the process of identifying and retaining the **most relevant features** for a model while removing redundant, irrelevant, or noisy ones.

---

## 1. Core Idea

Not all features help a model.

Feature selection aims to:
- Improve generalization
- Reduce overfitting
- Lower model complexity
- Improve interpretability
- Reduce computation cost

More features ≠ better model.

---

## 2. Feature Selection vs Feature Engineering

- **Feature Engineering** → create new features  
- **Feature Selection** → remove unnecessary features  

They are complementary, not substitutes.

🔗 Related:
- [[Feature Engineering]]
- [[Model Complexity]]

---

## 3. Why Feature Selection Is Important

Too many features can cause:
- Overfitting
- High variance
- Curse of dimensionality
- Slower training
- Harder interpretation

🔗 Related:
- [[Overfitting vs Underfitting]]
- [[Curse of Dimensionality]]

---

## 4. Types of Feature Selection Methods

---

### 4.1 Filter Methods

Use **statistical properties** of data.

Examples:
- Correlation
- Mutual Information
- Chi-square test
- Variance threshold

✔ Fast  
❌ Ignore model interaction

🔗 Concepts:
- [[Correlation]]
- [[Mutual Information]]

---

### 4.2 Wrapper Methods

Evaluate feature subsets using a **model**.

Examples:
- Forward selection
- Backward elimination
- Recursive Feature Elimination (RFE)

✔ Model-aware  
❌ Computationally expensive

🔗 Related:
- [[Recursive Feature Elimination]]

---

### 4.3 Embedded Methods

Feature selection happens **during training**.

Examples:
- L1 regularization (Lasso)
- Tree-based feature importance

✔ Efficient  
✔ Model-integrated  

🔗 Related:
- [[Lasso Regression]]
- [[Tree-Based Models — MOC]]

---

## 5. Algorithm-Specific Feature Selection Behavior

| Algorithm Family | Sensitivity to Feature Selection |
|----------------|----------------------------------|
| Linear Models | High |
| Logistic Regression | High |
| k-NN | Very High |
| SVM | High |
| Tree-Based Models | Medium |
| Random Forest | Low |
| Boosting Models | Low |
| Naive Bayes | Medium |

---

## 6. Feature Selection and Bias–Variance

- Fewer features → ↑ bias, ↓ variance
- More features → ↓ bias, ↑ variance

Feature selection shifts this balance.

🔗 Core concept:
- [[Bias–Variance Tradeoff]]

---

## 7. Feature Selection and Regularization

Regularization often performs **implicit feature selection**.

Examples:
- L1 regularization sets coefficients to zero
- Early stopping limits effective features

🔗 Related:
- [[Regularization — MOC]]
- [[Early Stopping]]

---

## 8. Feature Selection and Data Leakage ⚠️

❌ Wrong:
- Selecting features using full dataset

✅ Correct:
1. Split data
2. Perform feature selection on training set only
3. Apply selection to validation/test sets

🔗 Core concept:
- [[Data Leakage]]

---

## 9. Feature Selection and Model Interpretability

Fewer features:
- Easier explanations
- Clearer coefficients
- More trustworthy insights

🔗 Related:
- [[Model Interpretability]]

---

## 10. When Feature Selection Helps Most

- High-dimensional data
- Small datasets
- Distance-based models
- Linear models
- Noisy or redundant features

---

## 11. When Feature Selection Matters Less

- Tree ensembles
- Very large datasets
- Strong regularization already present

---

## 12. Common Mistakes

- ❌ Removing features blindly  
- ❌ Using correlation alone  
- ❌ Performing selection before splitting  
- ❌ Assuming trees don’t benefit at all  

Feature selection is **context-dependent**.

---

## 13. Why Feature Selection Matters

Feature selection explains:
- Why simpler models often win
- Why k-NN degrades in high dimensions
- Why linear models overfit with many features
- Why interpretability improves

It is a **core generalization tool**, not just preprocessing.

---

## Usage Notes

- Link this note from:
  - Feature Scaling
  - Feature Encoding
  - Model Complexity
  - Regularization
- Keep algorithm-specific logic out of this note
