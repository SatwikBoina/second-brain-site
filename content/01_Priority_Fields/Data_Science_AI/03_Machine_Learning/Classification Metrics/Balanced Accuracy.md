---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Balanced Accuracy
tags:
  - classification
  - metrics
  - model-evaluation
  - ML
---
---
## One-line idea
> Measures average accuracy across classes, giving equal importance to each class.

---

## Definition
Balanced Accuracy is the average of **recall for the positive class** and **recall for the negative class**.  
It compensates for class imbalance by treating both classes equally.

---

## Formula
$$
\text{Balanced Accuracy} = \frac{1}{2}\left(\frac{TP}{TP + FN} + \frac{TN}{TN + FP}\right)
$$
Where:
- TP = True Positives  
- FN = False Negatives  
- TN = True Negatives  
- FP = False Positives  

---

## Intuition
Instead of counting how many predictions are correct overall, Balanced Accuracy asks:

- *How well do I identify positives?*
- *How well do I identify negatives?*

Both answers matter **equally**, even if one class is rare.

---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Higher  
- Interpretation:
  - 1.0 → Perfect classification
  - 0.5 → Random guessing (binary)
  - Much more reliable than Accuracy for imbalanced data

---

## When to Use
- Classes are **imbalanced**
- Minority class is important
- You want a **single-number summary** that respects both classes

---

## When NOT to Use
- You need to emphasize **only one class**
- Error costs are asymmetric
- Multiclass problems without proper averaging

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌
  - Threshold choice ✅
  - Outliers ❌
- Threshold-dependent: **Yes**

---

## Trade-offs
- Improves fairness across classes
- May hide performance on the **most critical class**

---

## Relationship to Other Metrics
- Equals average of: [[Recall]] and [[Specificity]]
- Fixes limitations of: [[Accuracy]]
- Related to: [[G-Mean]]

---

## Business Interpretation
Balanced Accuracy ensures that **rare but important events** (fraud, churn, defects) are not ignored while still maintaining performance on the majority class.

---

## Example
Confusion Matrix:

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | 20       | 80       |
| Negative           | 10       | 890      |

\[
Recall = \frac{20}{100} = 0.20
\]

\[
Specificity = \frac{890}{900} = 0.989
\]

\[
Balanced\ Accuracy = \frac{0.20 + 0.989}{2} = 0.5945
\]

---

## Variants / Extensions
- Macro-averaged Recall
- Multiclass Balanced Accuracy

---

## Advantages
- Robust to class imbalance
- Easy to interpret
- Better baseline than Accuracy

---

## Limitations
- Treats all classes equally (may not match business cost)
- Does not capture precision
- Threshold dependent

---

## Common Misconceptions
- “Balanced Accuracy solves all imbalance issues” ❌
- “It replaces Precision–Recall metrics” ❌

---

## Interview Explanation (30 seconds)
Balanced Accuracy averages recall across classes, ensuring that both majority and minority classes are evaluated fairly. It is especially useful in imbalanced datasets where plain accuracy can be misleading.

---

## Links
- [[Accuracy]]
- [[Recall]]
- [[Specificity]]
- [[Imbalanced Classification]]

---
