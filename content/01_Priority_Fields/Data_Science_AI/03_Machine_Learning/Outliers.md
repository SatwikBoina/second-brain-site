---
type: concept
domain: machine-learning
category: data-quality
status: evergreen
---

# Outliers

> Outliers are data points that **deviate significantly** from the majority of observations and may represent noise, errors, or rare but valid events.

---

## 1. Core Idea

An outlier is **not always bad data**.

It can be:
- A data error
- A rare but real event
- A different data-generating process

The key question is:
> *Should the model learn from it or ignore it?*

---

## 2. Why Outliers Matter

Outliers can:
- Skew statistics (mean, variance)
- Distort distance metrics
- Break gradient-based optimization
- Dominate loss functions
- Cause unstable models

🔗 Related:
- [[Model Complexity]]
- [[Bias–Variance Tradeoff]]

---

## 3. Types of Outliers

---

### 3.1 Point Outliers

- Single extreme observations
- Most common type

Example:
- Salary = 10 crore in a dataset of 5–20 LPA

---

### 3.2 Contextual Outliers

- Only outliers in a specific context

Example:
- High temperature in winter
- High sales on a festival day

---

### 3.3 Collective Outliers

- A group of unusual points

Example:
- Sudden spike in traffic for several days

---

## 4. Common Causes of Outliers

- Data entry errors
- Measurement errors
- Rare events
- Data drift
- Fraud or anomalies

🔗 Related:
- [[Data Quality]]

---

## 5. How to Detect Outliers

---

### 5.1 Statistical Methods

- Z-score
- IQR (Interquartile Range)
- Modified Z-score (robust)

🔗 Related:
- [[Interquartile Range]]
- [[Robust Statistics]]

---

### 5.2 Visualization Methods

- Box plots
- Scatter plots
- Histograms

---

### 5.3 Model-Based Detection

- Isolation Forest
- One-Class SVM
- Local Outlier Factor (LOF)

🔗 Related:
- [[Anomaly Detection]]

---

## 6. Algorithm Sensitivity to Outliers

| Algorithm Family | Sensitivity |
|----------------|-------------|
| Linear Regression | Very High |
| Logistic Regression | High |
| k-NN | Very High |
| SVM (RBF) | High |
| Naive Bayes | Medium |
| Decision Trees | Low |
| Random Forest | Low |
| Gradient Boosting | Medium |
| XGBoost / LightGBM | Medium |
| CatBoost | Medium |

---

## 7. Outliers and Loss Functions

Loss choice matters:

- Squared error → very sensitive
- Absolute error → more robust
- Huber loss → balanced

🔗 Related:
- [[Loss Functions — MOC]]
- [[Huber Loss]]

---

## 8. Strategies to Handle Outliers

---

### 8.1 Do Nothing (Sometimes Best)

When:
- Outliers are genuine
- Problem cares about rare events
- Model is robust

---

### 8.2 Remove Outliers

When:
- Data errors are confirmed
- Outliers are irrelevant

⚠️ Risk:
- Removing valid rare cases

---

### 8.3 Transform the Data

- Log transform
- Box-Cox transform
- Winsorization

🔗 Related:
- [[Feature Transformation]]

---

### 8.4 Use Robust Statistics

- Median instead of mean
- IQR instead of variance

🔗 Related:
- [[Robust Scaling]]

---

### 8.5 Use Robust Models

- Tree-based models
- Ensemble methods
- Robust loss functions

---

## 9. Outliers and Feature Scaling

Outliers strongly affect:

- Standardization (mean, std)
- Distance metrics

Better options:
- Robust scaling
- Log transforms

🔗 Related:
- [[Feature Scaling]]

---

## 10. Outliers and Data Leakage ⚠️

❌ Wrong:
- Detecting outliers using full dataset

✅ Correct:
1. Split data
2. Detect outliers on training set
3. Apply same logic to test set

🔗 Related:
- [[Data Leakage]]
- [[Train–Test Split]]

---

## 11. When Outliers Are the Signal

In some domains, outliers **are the target**:

- Fraud detection
- Anomaly detection
- Rare disease diagnosis

Removing them destroys the problem.

---

## 12. Common Mistakes

- ❌ Removing outliers blindly  
- ❌ Using mean-based methods on skewed data  
- ❌ Ignoring domain context  
- ❌ Treating all outliers as noise  

Outlier handling is a **domain decision**, not a formula.

---

## 13. Why Outliers Matter

Outliers explain:
- Why linear models fail
- Why robust losses exist
- Why trees often outperform linear models
- Why preprocessing decisions matter

They sit at the intersection of **data quality and modeling**.

---

## Usage Notes

- Link this note from:
  - Feature Scaling
  - Loss Functions
  - Data Quality
  - Model Selection
- Keep algorithm-specific tricks out of this note
