---
type: concept
domain: machine-learning
category: model-evaluation
status: evergreen
---

# Cross Validation

> A model evaluation technique that repeatedly splits data into training and validation sets to obtain a **more reliable estimate of generalization performance**.

---

## 1. Core Idea

Instead of relying on a single train–test split, cross validation:

- Trains the model multiple times
- Uses different validation subsets each time
- Averages performance across runs

This reduces evaluation variance.

---

## 2. Why Cross Validation Is Needed

Single train–test splits can be:

- Noisy
- Dataset-dependent
- Misleading (especially on small data)

Cross validation provides a **stable estimate** of model performance.

---

## 3. k-Fold Cross Validation

### How It Works

1. Split data into k equal folds
2. Train on k−1 folds
3. Validate on the remaining fold
4. Repeat for all folds
5. Average the scores

Typical values:
- k = 5
- k = 10

---

## 4. Bias–Variance Perspective

- Small k (e.g., 2) → high bias, low variance
- Large k (e.g., leave-one-out) → low bias, high variance

k-fold CV balances both.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 5. Common Variants of Cross Validation

### Stratified k-Fold
- Preserves class proportions
- Essential for classification

🔗 See:
- [[Stratified Sampling]]
- [[Class Imbalance]]

---

### Leave-One-Out Cross Validation (LOOCV)
- k = number of samples
- Very low bias
- Very high variance and cost

---

### Repeated k-Fold
- Repeats k-fold with different random splits
- Further stabilizes estimates

---

### Time-Series Cross Validation
- Respects temporal ordering
- No data shuffling

🔗 See:
- [[Time Series Split]]

---

## 6. Cross Validation vs Train–Test Split

| Aspect | Cross Validation | Train–Test Split |
|-----|-----------------|------------------|
| Stability | High | Low |
| Computation | Expensive | Cheap |
| Data usage | Efficient | Less efficient |
| Use case | Model selection | Final evaluation |

🔗 See:
- [[Train–Test Split]]

---

## 7. Role in Model Selection

Cross validation is used to:

- Compare models
- Tune hyperparameters
- Choose regularization strength

It must happen **before** touching the test set.

🔗 Related:
- [[Model Selection]]
- [[Hyperparameter Tuning — MOC]]

---

## 8. Cross Validation and Data Leakage

Common mistakes:

- Scaling before CV
- Feature selection using full data
- Target encoding without care

All preprocessing must be done **inside each fold**.

🔗 Core concept:
- [[Data Leakage]]

---

## 9. Computational Cost

- Training cost multiplied by k
- Can be expensive for:
  - Large datasets
  - Complex models
  - Ensembles

Trade-off between reliability and cost.

---

## 10. When to Use Cross Validation

- Small to medium datasets
- Hyperparameter tuning
- Comparing multiple models
- High-variance algorithms

---

## 11. When Not to Use It

- Very large datasets
- Quick baseline checks
- When a dedicated validation set exists

---

## 12. Common Misconceptions

- ❌ Cross validation replaces test set  
- ❌ Higher k is always better  
- ❌ CV prevents overfitting by itself  

Cross validation **evaluates** models — it doesn’t fix them.

---

## 13. Why Cross Validation Matters

Cross validation explains:

- Why some models fail in production
- Why leaderboard scores fluctuate
- Why stable evaluation is hard

It is the **backbone of trustworthy ML evaluation**.

---

## Usage Notes

- Use CV for model selection
- Use test set once for final reporting
- Link this note from all tuning workflows
