---
type: concept
domain: machine-learning
category: data-integrity
status: evergreen
---

# Data Leakage

> Data leakage occurs when information from **outside the training process** is used to create the model, leading to overly optimistic performance estimates.

---

## 1. Core Idea

Data leakage happens when a model **learns from data it should not have access to** at prediction time.

This makes evaluation results **invalid**.

---

## 2. Why Data Leakage Is Dangerous

Leakage leads to:

- Inflated validation/test scores
- Models that fail in production
- False confidence during model selection

Once leakage happens, **all conclusions are unreliable**.

---

## 3. Common Types of Data Leakage

### 3.1 Train–Test Leakage

Information from the test set leaks into training.

Examples:
- Scaling before splitting
- Feature selection using full dataset
- Imputation using global statistics

🔗 Related:
- [[Train–Test Split]]

---

### 3.2 Target Leakage

Features contain information derived from the target.

Examples:
- Post-event features
- Aggregates computed using future data
- Leaky encodings

🔗 Related:
- [[Target Leakage]]

---

### 3.3 Temporal Leakage

Future information is used to predict the past.

Examples:
- Shuffling time-series data
- Using future sales to predict past demand

🔗 Related:
- [[Time Series Split]]

---

## 4. Leakage vs Overfitting

- Overfitting → model fits noise
- Leakage → model sees the answer

Leakage is **worse** than overfitting.

🔗 Related:
- [[Overfitting vs Underfitting]]

---

## 5. Leakage in Cross Validation

Leakage often occurs when:

- Preprocessing is done before CV
- Encoders use full dataset statistics

Correct approach:
- All preprocessing must happen **inside each fold**

🔗 Related:
- [[Cross Validation]]

---

## 6. Leakage in Feature Engineering

Common feature-engineering leaks:

- Using rolling averages including future points
- Aggregating target over entire dataset
- Target encoding without ordering

🔗 Related:
- [[Feature Engineering]]
- [[Target Encoding]]

---

## 7. Warning Signs of Leakage

- Unrealistically high performance
- Validation score much higher than training score
- Sudden performance drop in production

Leakage often looks “too good to be true”.

---

## 8. How to Prevent Data Leakage

### Golden Rules

1. Split data first
2. Fit preprocessing only on training data
3. Respect time and causality
4. Use pipelines
5. Treat test set as sacred

---

## 9. Data Leakage and Pipelines

Using pipelines ensures:

- Correct order of operations
- No accidental information sharing
- Reproducible workflows

🔗 Related:
- [[Pipelines]]

---

## 10. Algorithm-Specific Leakage Examples

| Algorithm | Common Leakage |
|--------|---------------|
| Linear / Logistic Regression | Scaling before split |
| Tree Models | Target leakage via engineered features |
| k-NN | Distance normalization on full data |
| Naive Bayes | Smoothing using global counts |
| Boosting | Early stopping on test set |

---

## 11. Why Data Leakage Is Hard to Detect

- Code runs without errors
- Metrics look excellent
- Requires domain understanding to spot

Leakage is a **human problem**, not a library bug.

---

## 12. Why Data Leakage Matters

Data leakage undermines:

- Model evaluation
- Model selection
- Trust in ML systems

Preventing leakage is **more important than tuning**.

---

## Usage Notes

- Link this note from:
  - Train–Test Split
  - Cross Validation
  - Feature Engineering
  - Model Selection
- Treat leakage as a critical failure, not a minor issue
