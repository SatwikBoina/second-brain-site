---
type: concept
domain: machine-learning
category: preprocessing
status: evergreen
---

# Handling Missing Data

> Handling missing data is the process of detecting, understanding, and treating missing values so that models learn valid patterns without bias or leakage.

---

## 1. Core Idea

Missing data is not just a technical issue — it is an **information problem**.

Before fixing missing values, ask:
- Why are values missing?
- Is missingness informative?
- Will imputation distort reality?

---

## 2. Types of Missingness (Critical)

Understanding *why* data is missing matters more than *how much* is missing.

---

### 2.1 MCAR — Missing Completely at Random

- Missingness unrelated to any variable
- Safest case

Example:
- Random sensor failure

---

### 2.2 MAR — Missing at Random

- Missingness depends on observed variables
- Common in real datasets

Example:
- Income missing more often for younger users

---

### 2.3 MNAR — Missing Not at Random

- Missingness depends on the missing value itself
- Most dangerous case

Example:
- People with low income not reporting income

---

## 3. Why Missing Data Is Dangerous

Improper handling can:
- Introduce bias
- Cause data leakage
- Reduce model performance
- Break distance-based models

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Data Leakage]]

---

## 4. Simple Handling Strategies

---

### 4.1 Deletion Methods

#### Row-wise Deletion
- Remove rows with missing values

✔ Simple  
❌ Loses data  
❌ Risky unless MCAR

---

#### Column-wise Deletion
- Drop features with excessive missingness

✔ Reduces noise  
❌ May remove important signals

---

## 5. Imputation Techniques

---

### 5.1 Constant Imputation

- Fill with fixed value (0, -1, “Unknown”)

✔ Simple  
❌ Can distort distributions

---

### 5.2 Statistical Imputation

- Mean
- Median
- Mode

✔ Fast  
❌ Underestimates variance

Best practice:
- Median for skewed data

---

### 5.3 Group-wise Imputation

- Impute based on groups (e.g., by category)

✔ More realistic  
❌ Requires domain knowledge

---

### 5.4 Model-Based Imputation

- k-NN imputation
- Regression imputation
- Iterative imputation (MICE)

✔ Powerful  
❌ Computationally expensive  
❌ Risk of leakage if misused

---

## 6. Missingness as a Feature

Sometimes, *missing itself is informative*.

Technique:
- Add a missing-indicator feature

✔ Useful for tree-based and boosting models

🔗 Related:
- [[Feature Engineering]]

---

## 7. Algorithm-Specific Considerations

| Algorithm Family | Missing Data Handling |
|----------------|----------------------|
| Linear Models | Require imputation |
| Logistic Regression | Require imputation |
| k-NN | Very sensitive to missing data |
| SVM | Requires complete data |
| Decision Trees | Can handle missing via surrogate splits |
| Random Forest | Handles missing reasonably |
| XGBoost | Learns default split directions |
| LightGBM | Native missing value handling |
| CatBoost | Native missing handling |

---

## 8. Missing Data and Feature Scaling

- Impute **before** scaling
- Never scale missing values
- Fit imputer on training data only

🔗 Related:
- [[Feature Scaling]]
- [[Train–Test Split]]

---

## 9. Missing Data and Data Leakage ⚠️

❌ Wrong:
- Imputing before train–test split

✅ Correct:
1. Split data
2. Fit imputer on training set
3. Apply to validation/test sets

🔗 Core concept:
- [[Data Leakage]]

---

## 10. Evaluation Impact

Improper handling of missing data can:
- Inflate performance
- Reduce robustness
- Cause silent failures in production

Always validate imputation choices via:
- Cross-validation
- Sensitivity analysis

🔗 Related:
- [[Cross Validation]]

---

## 11. Common Mistakes

- ❌ Blind mean imputation
- ❌ Ignoring missingness mechanism
- ❌ Imputing using full dataset
- ❌ Treating missing as zero without thinking

Missing data is **a modeling decision**, not a cleanup step.

---

## 12. When Missing Data Becomes a Signal

Examples:
- Credit risk (missing income)
- Medical tests (test not ordered)
- Surveys (non-response)

In such cases:
- Missingness ≠ noise
- It is **information**

---

## 13. Why Handling Missing Data Matters

Handling missing data correctly:
- Preserves statistical validity
- Improves generalization
- Prevents leakage
- Makes models production-safe

It is one of the **most underrated ML skills**.

---

## Usage Notes

- Link this note from:
  - Feature Engineering
  - Feature Scaling
  - Data Leakage
  - Model Selection
- Keep algorithm-specific tricks out of this note
