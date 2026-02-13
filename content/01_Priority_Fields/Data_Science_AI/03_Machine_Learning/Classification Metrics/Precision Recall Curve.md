---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Precision Recall Curve
tags: [classification, metrics, precision-recall-curve, imbalanced-classification, model-evaluation]
---

# Precision–Recall Curve

## One-line idea
> Visualizes the trade-off between precision and recall across different classification thresholds.

---

## Definition
The Precision–Recall (PR) Curve plots **Precision** on the Y-axis against **Recall** on the X-axis for all possible classification thresholds.

It focuses exclusively on **positive-class performance**.

---

## Axes Definition
- **X-axis:** Recall  
  
$$Recall = \frac{TP}{TP + FN}$$

- **Y-axis:** Precision  
  $$
  Precision = \frac{TP}{TP + FP}
  $$

---

## Intuition
Each point on the PR curve corresponds to a **different threshold**.

- Lower threshold → more positives → ↑ Recall, ↓ Precision  
- Higher threshold → fewer positives → ↓ Recall, ↑ Precision  

The curve shows how **precision degrades** as you try to capture more positives.

---
## Visual Aid
![[Precision recall curve.png]]
## Shape Interpretation
- Curve close to top-right → Strong classifier  
- Rapid precision drop → Many false positives  
- Flat low curve → Weak classifier  

Baseline precision equals **positive class prevalence**.

---

## Range & Interpretation
- Recall: 0 → 1  
- Precision: 0 → 1  
- Better curve:
  - Higher precision for the same recall
  - Larger area under the curve

---

## When to Use
- **Highly imbalanced datasets**
- Positive class is critical
- You care about **quality of positive predictions**

---

## When NOT to Use
- True negatives matter
- Classes are balanced
- Ranking across entire population is the goal

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ✅ (desirable)
  - Threshold choice ❌
  - Outliers ❌
- Threshold-dependent: **No (curve), Yes (points)**

---

## Trade-offs
- Increasing recall inevitably reduces precision
- No free lunch in positive detection

---

## Relationship to Other Metrics
- Uses: [[Precision]] and [[Recall]]
- Area summarized by: [[Average Precision]]
- Preferred alternative to: [[ROC Curve]] in imbalanced data

---

## Business Interpretation
PR Curve helps answer:  
**“How many false alarms am I willing to tolerate to catch more positives?”**

Critical for:
- Fraud detection
- Churn prevention
- Campaign targeting

---

## Example (Conceptual)
- Recall = 0.2 → Precision = 0.9  
- Recall = 0.5 → Precision = 0.6  
- Recall = 0.8 → Precision = 0.3  

Each reflects a different operating point.

---

## Variants / Extensions
- Micro PR Curve
- Macro PR Curve
- Weighted PR Curve

---

## Advantages
- Focuses on positive class
- Honest in imbalanced datasets
- Business-aligned interpretation

---

## Limitations
- Ignores true negatives
- Harder to interpret than ROC
- Curves can cross (model comparison tricky)

---

## Common Misconceptions
- “PR curve replaces ROC always” ❌
- “High PR curve means low false negatives” ❌

---

## Interview Explanation (30 seconds)
The Precision–Recall curve plots precision versus recall across thresholds and is especially useful in imbalanced datasets. Unlike ROC, it focuses on positive-class performance and better reflects the cost of false positives.

---

## Links
- [[Precision]]
- [[Recall]]
- [[Average Precision]]
- [[ROC Curve]]

---

## Tags
#classification #precision-recall-curve #metrics #model-evaluation
