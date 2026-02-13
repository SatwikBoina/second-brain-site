---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: G-Mean
tags: [classification, metrics, g-mean, imbalanced-classification, model-evaluation]
---

# G-Mean

## One-line idea
> Measures how well a model balances performance between positive and negative classes.

---

## Definition
G-Mean (Geometric Mean) is the square root of the product of **Sensitivity (Recall)** and **Specificity**.

It ensures that the classifier performs well on **both classes**, not just one.

---

## Formula
\[
\text{G-Mean} = \sqrt{\text{Sensitivity} \times \text{Specificity}}
\]

Where:
\[
\text{Sensitivity} = \frac{TP}{TP + FN}, \quad
\text{Specificity} = \frac{TN}{TN + FP}
\]

---

## Intuition
G-Mean:
- Penalizes extreme imbalance
- Drops sharply if **either class performance is poor**

A classifier that performs well on only one class will have a **low G-Mean**.

---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Higher  
- Interpretation:
  - 1.0 → Perfect classification for both classes
  - Low value → Model ignores one class

---

## When to Use
- Binary classification with **imbalanced classes**
- Both classes are important
- You want fairness across classes

---

## When NOT to Use
- One class is significantly more important
- Precision matters more than recall
- Multiclass without proper generalization

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌
  - Threshold choice ✅
  - Outliers ❌
- Threshold-dependent: **Yes**

---

## Trade-offs
- Encourages balanced performance
- Does not account for precision

---

## Relationship to Other Metrics
- Combines: [[Sensitivity]] and [[Specificity]]
- Related to: [[Balanced Accuracy]]
- Alternative to: [[F1 Score]]

---

## Business Interpretation
G-Mean ensures that improvements in majority-class performance do not come at the expense of minority-class failure.

---

## Example
Confusion Matrix:

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | 30       | 70       |
| Negative           | 5        | 895      |

\[
Sensitivity = \frac{30}{100} = 0.30
\]

\[
Specificity = \frac{895}{900} = 0.994
\]

\[
G\text{-Mean} = \sqrt{0.30 \times 0.994} \approx 0.546
\]

---

## Variants / Extensions
- Multiclass G-Mean
- Weighted G-Mean

---

## Advantages
- Robust to class imbalance
- Encourages balanced classifiers
- Simple interpretation

---

## Limitations
- Ignores precision
- Threshold sensitive
- Less intuitive than F1

---

## Common Misconceptions
- “High G-Mean means high precision” ❌
- “G-Mean replaces F1” ❌

---

## Interview Explanation (30 seconds)
G-Mean evaluates whether a classifier performs well on both positive and negative classes by combining sensitivity and specificity. It is particularly useful in imbalanced datasets where accuracy can be misleading.

---

## Links
- [[Sensitivity]]
- [[Specificity]]
- [[Balanced Accuracy]]
- [[Imbalanced Classification]]

---

## Tags
#classification #g-mean #metrics #model-evaluation
