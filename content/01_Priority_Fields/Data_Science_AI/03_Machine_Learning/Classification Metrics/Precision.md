---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Precision
tags: [classification, metrics, precision, model-evaluation]
---

## One-line idea
> Measures how many of the predicted positives are actually positive.

---

## Definition
Precision is the fraction of correctly predicted positive instances out of all instances predicted as positive.

It answers the question:  
**“When the model predicts positive, how often is it correct?”**

---

## Formula
$$
\text{Precision} = \frac{TP}{TP + FP}
$$
Where:
- TP = True Positives  
- FP = False Positives  

---

## Intuition
Precision focuses only on **predicted positives**.

- High precision → very few false alarms  
- Low precision → many false positives  

It does **not** care about false negatives.

---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Higher  
- Interpretation:
  - 1.0 → Every positive prediction is correct
  - Low precision → Model cries “positive” too often

---

## When to Use
- False positives are **costly**
- You want **high confidence** in positive predictions
- Examples:
  - Spam detection
  - Marketing targeting
  - Lead qualification

---

## When NOT to Use
- Missing positives is costly
- You care about coverage of positives
- Alone, without Recall

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌
  - Threshold choice ✅
  - Outliers ❌
- Threshold-dependent: **Yes**

---

## Trade-offs
- Increasing precision usually:
  - Decreases recall
- Precision–Recall tradeoff is unavoidable

---

## Relationship to Other Metrics
- Complements: [[Recall]]
- Combined into: [[F1 Score]]
- Related to: [[False Positive Rate]]

---

## Business Interpretation
High precision means **resources are not wasted** on wrong positives,  
but the business may miss opportunities if recall is low.

---

## Example
Confusion Matrix:

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | 30       | 70       |
| Negative           | 10       | 890      |

\[
Precision = \frac{30}{30 + 10} = 0.75
\]

---

## Variants / Extensions
- Precision@K
- Macro Precision
- Micro Precision

---

## Advantages
- Clear interpretation
- Useful in high-cost FP scenarios
- Works well with ranking problems

---

## Limitations
- Ignores false negatives
- Misleading if used alone
- Threshold sensitive

---

## Common Misconceptions
- “High precision means good model” ❌
- “Precision measures coverage” ❌

---

## Interview Explanation (30 seconds)
Precision measures how reliable positive predictions are. It is critical when false positives are expensive, such as in marketing or spam detection, but it must be evaluated together with recall.

---

## Links
- [[Recall]]
- [[F1 Score]]
- [[Precision Recall Tradeoff]]

---
