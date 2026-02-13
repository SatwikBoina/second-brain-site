---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: False Negative Rate
tags: [classification, metrics, false-negative-rate, fnr, model-evaluation]
---

## One-line idea
> Measures how often actual positives are incorrectly predicted as negative.

---

## Definition
False Negative Rate is the proportion of positive instances that the model fails to identify.

It answers the question:  
**“Out of all real positives, how many did the model miss?”**

---

## Formula
$$
\text{FNR} = \frac{FN}{FN + TP}
$$

Where:
- FN = False Negatives  
- TP = True Positives  

---

## Intuition
FNR focuses on **missed positives**.

- Low FNR → model detects most positives  
- High FNR → many important cases are missed  

It is the **mirror of Sensitivity (Recall)**.

---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Lower  
- Interpretation:
  - 0.0 → No missed positives
  - 1.0 → All positives missed

---

## When to Use
- Missing positives is **very costly**
- You want to quantify detection failure
- Examples:
  - Medical screening
  - Fraud detection
  - Safety systems

---

## When NOT to Use
- False positives are the main concern
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
- Reducing FNR usually:
  - Increases false positives
- Direct trade-off with Specificity

---

## Relationship to Other Metrics
- Complement of: [[Sensitivity]]
- Opposite of: [[True Positive Rate]]
- Related to: [[Recall]]
- Used in: [[ROC Curve]] (indirectly)

---

## Business Interpretation
Lower FNR ensures **critical events are not missed**, even if operational cost increases due to false alarms.

---

## Example
Confusion Matrix:

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | 85       | 15       |
| Negative           | 120      | 780      |

\[
FNR = \frac{15}{100} = 0.15
\]

---

## Variants / Extensions
- Macro FNR
- Micro FNR
- Weighted FNR

---

## Advantages
- Explicitly quantifies misses
- Critical for safety-focused domains
- Simple interpretation

---

## Limitations
- Ignores false positives
- Misleading if used alone
- Threshold sensitive

---

## Common Misconceptions
- “Low FNR means high precision” ❌
- “FNR measures overall error” ❌

---

## Interview Explanation (30 seconds)
False Negative Rate measures how often a model fails to detect actual positives. It is critical in applications like fraud or healthcare, where missing a positive case can have severe consequences.

---

## Links
- [[Sensitivity]]
- [[Recall]]
- [[False Positive Rate]]
- [[ROC Curve]]

