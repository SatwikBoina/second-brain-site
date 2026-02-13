---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Specificity
tags: [classification, metrics, specificity, true-negative-rate, model-evaluation]
---


## One-line idea
> Measures the ability of a model to correctly identify actual negatives.

---

## Definition
Specificity is the proportion of actual negative instances that are correctly predicted as negative.

It is also known as the **True Negative Rate (TNR)**.

---

## Formula
$$
\text{Specificity} = \frac{TN}{TN + FP}
$$

Where:
- TN = True Negatives  
- FP = False Positives  

---

## Intuition
Specificity focuses on **not raising false alarms**.

- High specificity → very few false positives  
- Low specificity → model incorrectly flags many negatives as positives  

False negatives do not affect specificity.

---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Higher  
- Interpretation:
  - 1.0 → No false positives
  - Low value → many false alarms

---

## When to Use
- False positives are **costly**
- You need confidence in negative predictions
- Examples:
  - Spam filters
  - Credit approvals
  - Alarm systems

---

## When NOT to Use
- Missing positives is costly
- Positive class is critical
- Used alone without Sensitivity

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌
  - Threshold choice ✅
  - Outliers ❌
- Threshold-dependent: **Yes**

---

## Trade-offs
- Increasing specificity:
  - Often decreases sensitivity
- Must be balanced with missed positives

---

## Relationship to Other Metrics
- Also called: [[True Negative Rate]]
- Opposite of: [[False Positive Rate]]
- Complements: [[Sensitivity]]
- Used in: [[Balanced Accuracy]]

---

## Business Interpretation
High specificity ensures **resources are not wasted on false alarms**, but overly high specificity can cause missed opportunities.

---

## Example
Confusion Matrix:

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | 70       | 30       |
| Negative           | 5        | 895      |

\[
Specificity = \frac{895}{900} = 0.994
\]

---

## Variants / Extensions
- Macro Specificity
- Micro Specificity
- Weighted Specificity

---

## Advantages
- Controls false positives
- Easy to interpret
- Important for operational efficiency

---

## Limitations
- Ignores false negatives
- Misleading if used alone
- Threshold sensitive

---

## Common Misconceptions
- “High specificity means good model” ❌
- “Specificity measures positive detection” ❌

---

## Interview Explanation (30 seconds)
Specificity measures how well a model identifies negatives by minimizing false positives. It is crucial when false alarms are expensive, but must be balanced with sensitivity to avoid missing important positives.

---

## Links
- [[Sensitivity]]
- [[Balanced Accuracy]]
- [[False Positive Rate]]
- [[ROC Curve]]

---

## Tags
#classification #specificity #true-negative-rate #metrics #model-evaluation
