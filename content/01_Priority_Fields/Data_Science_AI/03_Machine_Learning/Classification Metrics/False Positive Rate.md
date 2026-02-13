---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: False Positive Rate
tags: [classification, metrics, false-positive-rate, fpr, model-evaluation]
---

## One-line idea
> Measures how often actual negatives are incorrectly predicted as positive.

---

## Definition
False Positive Rate is the proportion of negative instances that are wrongly classified as positive.

It answers the question:  
**“Out of all real negatives, how many false alarms did the model raise?”**

---

## Formula
$$
\text{FPR} = \frac{FP}{FP + TN}
$$
Where:
- FP = False Positives  
- TN = True Negatives  

---

## Intuition
FPR focuses on **false alarms**.

- Low FPR → model is conservative with positives  
- High FPR → model frequently misclassifies negatives as positives  

It is the **mirror of Specificity**.

---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Lower  
- Interpretation:
  - 0.0 → No false positives
  - 1.0 → All negatives misclassified

---

## When to Use
- False positives are costly
- You want to control false alarms
- Essential for:
  - ROC Curve
  - Risk modeling
  - Credit scoring

---

## When NOT to Use
- Missing positives is the primary concern
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
- Reducing FPR usually:
  - Increases false negatives
- Tightly coupled with Sensitivity

---

## Relationship to Other Metrics
- Complement of: [[Specificity]]
- Used with: [[Sensitivity]]
- Axis of: [[ROC Curve]]

---

## Business Interpretation
Lower FPR means fewer unnecessary actions, saving cost and improving trust in model decisions.

---

## Example
Confusion Matrix:

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | 60       | 40       |
| Negative           | 90       | 810      |

\[
FPR = \frac{90}{900} = 0.10
\]

---

## Variants / Extensions
- Macro FPR
- Micro FPR
- Weighted FPR

---

## Advantages
- Direct control over false alarms
- Critical for risk-sensitive systems
- Interpretable

---

## Limitations
- Ignores false negatives
- Misleading if used alone
- Threshold sensitive

---

## Common Misconceptions
- “Low FPR means high recall” ❌
- “FPR measures positive performance” ❌

---

## Interview Explanation (30 seconds)
False Positive Rate measures how often a model incorrectly flags negatives as positives. It is crucial in domains where false alarms are expensive and is a key component of the ROC curve.

---

## Links
- [[Specificity]]
- [[Sensitivity]]
- [[ROC Curve]]
- [[False Negative Rate]]

---

## Tags
#classification #false-positive-rate #fpr #metrics #model-evaluation
