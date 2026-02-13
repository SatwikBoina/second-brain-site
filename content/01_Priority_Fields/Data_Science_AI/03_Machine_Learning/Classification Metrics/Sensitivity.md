---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Sensitivity
tags: [classification, metrics, sensitivity, recall, model-evaluation]
---


## One-line idea
> Measures the ability of a model to correctly identify actual positives.

---

## Definition
Sensitivity is the proportion of actual positive instances that are correctly predicted as positive.

It is **mathematically identical to Recall**.

---

## Formula
\[
\text{Sensitivity} = \frac{TP}{TP + FN}
\]

Where:
- TP = True Positives  
- FN = False Negatives  

---

## Intuition
Sensitivity focuses on **not missing positives**.

- High sensitivity → almost all positives are detected  
- Low sensitivity → many positives are missed  

False positives do not affect sensitivity.

---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Higher  
- Interpretation:
  - 1.0 → No missed positives
  - Low value → model is blind to positives

---

## When to Use
- Missing positives is **very costly**
- Safety-critical or risk-sensitive problems
- Examples:
  - Medical diagnosis
  - Fraud detection
  - Defect detection

---

## When NOT to Use
- False positives are costly
- You need confidence in predictions
- Used alone without Precision

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌
  - Threshold choice ✅
  - Outliers ❌
- Threshold-dependent: **Yes**

---

## Trade-offs
- Increasing sensitivity:
  - Often decreases precision
- Requires balancing with false positives

---

## Relationship to Other Metrics
- Same as: [[Recall]]
- Opposite of: [[False Negative Rate]]
- Complements: [[Specificity]]
- Used in: [[Balanced Accuracy]]

---

## Business Interpretation
High sensitivity ensures **important events are not missed**, but operational load may increase due to false positives.

---

## Example
Confusion Matrix:

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | 95       | 5        |
| Negative           | 200      | 700      |

\[
Sensitivity = \frac{95}{100} = 0.95
\]

---

## Variants / Extensions
- Macro Sensitivity
- Micro Sensitivity
- Weighted Sensitivity

---

## Advantages
- Critical for risk avoidance
- Simple interpretation
- Domain-standard terminology

---

## Limitations
- Ignores false positives
- Misleading if used alone
- Threshold sensitive

---

## Common Misconceptions
- “Sensitivity measures prediction quality” ❌
- “High sensitivity means low risk” ❌

---

## Interview Explanation (30 seconds)
Sensitivity, also called recall, measures how well a model detects actual positives. It is critical in domains like healthcare and fraud where missing a positive is far more costly than raising false alarms.

---

## Links
- [[Recall]]
- [[Specificity]]
- [[Balanced Accuracy]]
- [[False Negative Rate]]

---

## Tags
#classification #sensitivity #recall #metrics #model-evaluation
