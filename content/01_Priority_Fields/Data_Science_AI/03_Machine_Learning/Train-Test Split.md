---
type: concept
domain: machine-learning
category: data-splitting
status: evergreen
---

# Train–Test Split

> A data-splitting strategy that separates available data into **training** and **testing** sets to evaluate a model’s ability to generalize to unseen data.

---

## 1. Core Idea

The train–test split simulates real-world deployment:

- **Train set** → used to fit the model  
- **Test set** → used only for final evaluation  

The test set must remain **completely unseen** during training.

---

## 2. Why Train–Test Split Is Necessary

Without a proper split:

- Models appear unrealistically accurate
- Overfitting goes undetected
- Performance estimates become biased

Train–test split provides a **baseline estimate of generalization error**.

---

## 3. Typical Split Ratios

Common choices:

- 80% train / 20% test
- 70% train / 30% test
- 90% train / 10% test (large datasets)

There is **no universally optimal ratio** — dataset size matters.

---

## 4. Relationship to Overfitting & Bias–Variance

- Training error → measures fit
- Test error → measures generalization

Large gap between them indicates **overfitting**.

🔗 Related:
- [[Overfitting vs Underfitting]]
- [[Bias–Variance Tradeoff]]

---

## 5. Random vs Deterministic Splits

### Random Split
- Assumes data is IID
- Most common in tabular ML

### Deterministic Split
- Used when order matters
- Common in time-series data

🔗 See:
- [[Time Series Split]]

---

## 6. Stratified Train–Test Split

For classification problems:

- Preserves class proportions
- Prevents minority class distortion

🔗 Concepts:
- [[Stratified Sampling]]
- [[Class Imbalance]]

---

## 7. Common Pitfalls (Critical)

### Data Leakage
Occurs when information from the test set influences training.

Examples:
- Scaling before splitting
- Feature selection using full dataset
- Target encoding without care

🔗 Core concept:
- [[Data Leakage]]

---

## 8. What Should Happen After the Split

Correct workflow:

1. Split data  
2. Fit preprocessing **only on train set**  
3. Apply transformations to test set  
4. Train model  
5. Evaluate once on test set  

Never tune hyperparameters using the test set.

---

## 9. Train–Test Split vs Cross Validation

| Aspect | Train–Test Split | Cross Validation |
|-----|-----------------|------------------|
| Speed | Fast | Slower |
| Variance | High | Low |
| Reliability | Lower | Higher |
| Use case | Baseline / final test | Model selection |

🔗 See:
- [[Cross Validation]]

---

## 10. Role in Model Selection

- Train–test split gives a **final unbiased estimate**
- Cross-validation is used **before** the test set

Test set should be touched **once**.

🔗 Related:
- [[Model Selection]]

---

## 11. When Train–Test Split Is Enough

- Large datasets
- Stable data distributions
- Quick baseline modeling

---

## 12. When It Is Not Enough

- Small datasets
- High-variance models
- Hyperparameter tuning

Use cross-validation instead.

---

## Usage Notes

- Link this note from all modeling workflows
- Never mix with preprocessing explanations
- Treat the test set as sacred
