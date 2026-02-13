---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Accuracy
tags:
  - classification
  - metrics
  - model-evaluation
  - ML
---

## One-line idea
> Measures the proportion of total predictions the model got right.

---

## Definition
Accuracy is the fraction of all predictions (both positive and negative) that are correctly classified by the model.

---

## Formula
$$
\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}

$$
Where:
- TP = True Positives  
- TN = True Negatives  
- FP = False Positives  
- FN = False Negatives  

---

## Intuition
Accuracy increases when the model correctly predicts both positive and negative classes.  
It treats **all errors equally**, regardless of class importance.

---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Higher  
- Interpretation:
  - 1.0 → Perfect classification
  - 0.5 → Random guessing (binary, balanced)
  - High accuracy ≠ good model (if data is imbalanced)

---

## When to Use
- Classes are **balanced**
- False positives and false negatives have **similar cost**
- As a **baseline metric**

---

## When NOT to Use
- Severe **class imbalance**
- Minority class is critical (fraud, disease, churn)
- Business cost of errors is asymmetric

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ✅
  - Threshold choice ❌ (indirectly)
  - Outliers ❌
- Threshold-dependent: **Yes**

---

## Trade-offs
- Improving accuracy may reduce:
  - Recall of minority class
  - Precision of positive class

---

## Relationship to Other Metrics
- Related to: [[Confusion Matrix]]
- Complements: [[Precision]], [[Recall]]
- Extended by: [[Balanced Accuracy]]

---

## Business Interpretation
High accuracy means most decisions are correct overall,  
but it may **hide critical failures** in important customer segments.

---

## Example
Confusion Matrix:

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | 40       | 10       |
| Negative           | 5        | 45       |

\[
Accuracy = \frac{40 + 45}{100} = 0.85
\]

---

## Variants / Extensions
- Balanced Accuracy
- Top-K Accuracy

---

## Advantages
- Simple and intuitive
- Easy to communicate
- Good baseline metric

---

## Limitations
- Misleading for imbalanced data
- Ignores business cost of errors
- No insight into error type

---

## Common Misconceptions
- “High accuracy means good model” ❌
- “Accuracy reflects minority class performance” ❌

---

## Interview Explanation (30 seconds)
Accuracy measures the overall correctness of a classifier by calculating the fraction of correct predictions. It works well when classes are balanced and error costs are similar, but fails badly in imbalanced problems because it ignores which class is being predicted correctly.

---

## Links
- [[Confusion Matrix]]
- [[Balanced Accuracy]]
- [[Why Accuracy Fails]]

---
