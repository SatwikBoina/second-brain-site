---
type: concept
domain: machine-learning
category: data-splitting
status: evergreen
---

# Stratified Sampling

> A sampling technique that preserves the **class distribution** of the target variable across subsets of data.

---

## 1. Core Idea

Stratified sampling ensures that each subset (train, validation, test, or fold):

- Contains the **same proportion of classes**
- Accurately represents the original dataset
- Avoids minority class distortion

This is especially important for **classification problems**.

---

## 2. Why Stratified Sampling Is Needed

Random sampling can accidentally:

- Exclude minority classes
- Over-represent majority classes
- Produce misleading evaluation metrics

Stratification reduces this randomness.

---

## 3. How Stratified Sampling Works

1. Divide the dataset into **strata** based on class labels
2. Sample proportionally from each stratum
3. Combine samples to form the final subset

The class ratio remains approximately constant.

---

## 4. Where Stratified Sampling Is Used

Stratified sampling is commonly applied in:

- Train–test split
- Cross validation (stratified k-fold)
- Model evaluation on imbalanced datasets

🔗 Related:
- [[Train–Test Split]]
- [[Cross Validation]]

---

## 5. Stratified Train–Test Split

Ensures:

- Training set has representative class proportions
- Test set reflects real-world distribution

Critical for:
- Accuracy
- Precision / Recall
- ROC–AUC stability

🔗 Related:
- [[Classification Metrics — MOC]]

---

## 6. Stratified k-Fold Cross Validation

Each fold:
- Preserves class proportions
- Reduces fold-to-fold variance
- Produces more reliable CV scores

This is the **default choice** for classification.

🔗 Related:
- [[Class Imbalance]]

---

## 7. Relationship to Class Imbalance

Stratification:
- Does NOT fix class imbalance
- Prevents imbalance from worsening during sampling

To *fix* imbalance, use:
- Resampling
- Class weights
- Threshold tuning

🔗 Related:
- [[Class Imbalance]]

---

## 8. When Stratified Sampling Helps Most

- Small datasets
- Highly imbalanced classes
- Rare-event classification
- Medical, fraud, churn problems

---

## 9. When Stratification Is Less Important

- Very large datasets
- Perfectly balanced classes
- Regression problems (usually)

---

## 10. Common Pitfalls

- ❌ Stratifying on the wrong variable
- ❌ Stratifying time-series data
- ❌ Assuming stratification fixes imbalance

Stratification preserves distribution — it doesn’t change it.

---

## 11. Stratified Sampling vs Random Sampling

| Aspect | Random Sampling | Stratified Sampling |
|-----|----------------|--------------------|
| Class balance | Unstable | Preserved |
| Variance | Higher | Lower |
| Reliability | Lower | Higher |
| Default for classification | ❌ | ✅ |

---

## 12. Why Stratified Sampling Matters

Stratified sampling ensures that:

- Evaluation metrics are meaningful
- Minority classes are respected
- Model selection is reliable

It is a **best practice**, not an optimization trick.

---

## Usage Notes

- Use stratification by default for classification
- Avoid stratification for time-dependent data
- Link this note from:
  - Train–Test Split
  - Cross Validation
  - Class Imbalance
