---
type: concept
domain: machine-learning
category: classification
status: evergreen
---

# Threshold Tuning

> Threshold tuning is the process of adjusting the **decision threshold** that converts predicted probabilities into class labels in order to optimize business or performance objectives.

---

## 1. Core Idea

Most classifiers output **probabilities**, not class labels.

Default rule:
- Predict class = 1 if probability ≥ **0.5**

Threshold tuning asks:
> *Is 0.5 really the right cutoff for this problem?*

Often, it is not.

---

## 2. Why Threshold Tuning Is Necessary

Using a fixed 0.5 threshold assumes:
- Balanced classes
- Equal cost of false positives and false negatives

In real-world problems, these assumptions rarely hold.

🔗 Related:
- [[Class Imbalance]]
- [[Cost-Sensitive Learning]]

---

## 3. Threshold vs Model Training

Important distinction:

- **Training** → learns probabilities
- **Threshold tuning** → converts probabilities into decisions

Threshold tuning:
- Does NOT change model weights
- Changes prediction behavior

It is a **post-training optimization**.

---

## 4. Effect of Threshold on Metrics

Changing the threshold directly affects:

- Precision
- Recall
- F1-score
- False Positive Rate
- False Negative Rate

| Threshold ↑ | Precision | Recall |
|-----------|-----------|--------|
| Increase | ↑ | ↓ |
| Decrease | ↓ | ↑ |

🔗 Related:
- [[Classification Metrics — MOC]]
- [[Confusion Matrix]]

---

## 5. Threshold Tuning and ROC / PR Curves

Threshold tuning corresponds to **moving along a curve**:

- ROC curve → trade-off between TPR and FPR
- Precision–Recall curve → trade-off between precision and recall

Each point on the curve = one threshold.

🔗 Related:
- [[ROC Curve]]
- [[Precision Recall Curve]]

---

## 6. Common Threshold Selection Strategies

---

### 6.1 Metric Optimization

Choose threshold that:
- Maximizes F1-score
- Maximizes recall at fixed precision
- Minimizes cost function

---

### 6.2 Business Cost Optimization

Define a cost matrix:

- Cost(FP)
- Cost(FN)

Select threshold minimizing **expected cost**.

🔗 Related:
- [[Cost-Sensitive Learning]]

---

### 6.3 Constraint-Based Tuning

Examples:
- Recall ≥ 95%
- False Positive Rate ≤ 1%

Useful in:
- Medical diagnosis
- Fraud detection

---

## 7. Threshold Tuning and Class Imbalance

In imbalanced datasets:
- Default threshold favors majority class
- Minority recall collapses

Threshold tuning is often **mandatory**.

🔗 Related:
- [[Class Imbalance]]

---

## 8. Threshold Tuning and Probability Calibration

Threshold tuning assumes probabilities are meaningful.

Poor calibration → unstable thresholds.

Calibration may be required first.

🔗 Related:
- [[Probability Calibration]]

---

## 9. Threshold Tuning and Data Leakage ⚠️

❌ Wrong:
- Tuning threshold on test set

✅ Correct:
1. Tune threshold on validation set
2. Lock threshold
3. Evaluate once on test set

🔗 Related:
- [[Data Leakage]]
- [[Train–Test Split]]

---

## 10. Algorithm Compatibility

Threshold tuning applies to:
- Logistic Regression
- Naive Bayes
- Tree ensembles
- Boosting models
- Neural networks

Not applicable to:
- Hard-margin classifiers without probabilities (unless calibrated)

🔗 Related:
- [[Probability Calibration]]

---

## 11. Common Mistakes

- ❌ Using accuracy to tune threshold  
- ❌ Ignoring business costs  
- ❌ Tuning on test set  
- ❌ Assuming threshold is model-specific  

Thresholds are **problem-specific**, not model-specific.

---

## 12. When Threshold Tuning Helps Most

- Imbalanced classification
- High-stakes decisions
- Cost-sensitive problems
- Precision–recall trade-offs

---

## 13. When Threshold Tuning Matters Less

- Balanced datasets
- Symmetric error costs
- Exploratory modeling

---

## 14. Why Threshold Tuning Matters

Threshold tuning explains:
- Why accuracy can be misleading
- Why the same model behaves differently in production
- Why business metrics outperform ML metrics
- Why probability outputs are powerful

It is the **final bridge from model to decision**.

---

## Usage Notes

- Link this note from:
  - Class Imbalance
  - Classification Metrics — MOC
  - Probability Calibration
  - Model Selection
- Treat threshold as a tunable hyperparameter (but post-training)
