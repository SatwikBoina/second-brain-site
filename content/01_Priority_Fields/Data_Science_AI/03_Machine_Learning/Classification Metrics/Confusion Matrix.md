---
type: zettel
domain: machine-learning
category: classification
topic: foundation
metric: Confusion Matrix
tags: [classification, confusion-matrix, fundamentals, model-evaluation]
---

# Confusion Matrix

## One-line idea
> A table that summarizes prediction outcomes by comparing actual and predicted classes.

---

## Definition
A Confusion Matrix is a structured table that shows how a classification model’s predictions align with actual class labels by counting correct and incorrect predictions.

It is the **foundation** for almost all classification metrics.

---

## Structure (Binary Classification)

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | TP       | FN       |
| Negative           | FP       | TN       |

Where:
- **TP (True Positive):** Correctly predicted positives  
- **FP (False Positive):** Incorrectly predicted positives  
- **FN (False Negative):** Missed positives  
- **TN (True Negative):** Correctly predicted negatives  

---

## Intuition
The confusion matrix answers **four fundamental questions**:
- How many positives did we catch? (TP)
- How many positives did we miss? (FN)
- How many false alarms did we raise? (FP)
- How many negatives did we correctly ignore? (TN)

Every classification metric is derived from these counts.

---

## Range & Properties
- Contains **counts**, not rates
- Size depends on number of classes:
  - Binary → 2×2
  - Multiclass → K×K

---

## When to Use
- Always inspect before choosing metrics
- Error analysis
- Model debugging
- Business explanation of errors

---

## When NOT to Use
- As a standalone performance metric
- For large multiclass problems without aggregation

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ✅
  - Threshold choice ✅
- Threshold-dependent: **Yes**

---

## Relationship to Metrics
Derived directly from the confusion matrix:
- [[Accuracy]]
- [[Precision]]
- [[Recall]]
- [[Sensitivity]]
- [[Specificity]]
- [[False Positive Rate]]
- [[False Negative Rate]]
- [[F1 Score]]
- [[Balanced Accuracy]]
- [[G-Mean]]

---

## Business Interpretation
The confusion matrix translates model behavior into **business mistakes**:
- FN → Missed opportunities / risks
- FP → Wasted resources / false alarms

It enables cost-based decision-making.

---

## Example
Suppose:

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | 80       | 20       |
| Negative           | 50       | 850      |

Interpretation:
- 20 positives were missed
- 50 false alarms occurred

---

## Multiclass Confusion Matrix
- Square matrix of size \(K \times K\)
- Diagonal = correct predictions
- Off-diagonal = misclassifications

---

## Advantages
- Complete error visibility
- Interpretable
- Metric-agnostic foundation

---

## Limitations
- Does not summarize performance
- Hard to compare models directly
- Scales poorly with many classes

---

## Common Misconceptions
- “Confusion matrix gives accuracy” ❌
- “Only useful for binary classification” ❌

---

## Interview Explanation (30 seconds)
A confusion matrix shows the counts of correct and incorrect predictions across actual and predicted classes. It forms the basis of all classification metrics and helps understand what types of errors a model makes.

---

