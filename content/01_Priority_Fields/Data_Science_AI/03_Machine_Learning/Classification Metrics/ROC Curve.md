---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: ROC Curve
tags: [classification, metrics, roc-curve, threshold-independent, model-evaluation]
---

# ROC Curve (Receiver Operating Characteristic Curve)

## One-line idea
> Visualizes the trade-off between detecting positives and raising false alarms across all thresholds.

---

## Definition
The ROC Curve plots **True Positive Rate (Sensitivity)** against **False Positive Rate** for all possible classification thresholds.

It evaluates a model’s **ranking ability**, not a single threshold decision.

---

## Axes Definition
- **X-axis:** False Positive Rate (FPR)
  $$
  FPR = \frac{FP}{FP + TN}
  $$

- **Y-axis:** True Positive Rate (TPR / Sensitivity)

  $$TPR = \frac{TP}{TP + FN}$$
  

---

## Intuition
Each point on the ROC curve represents a **different threshold**.

- Lower threshold → more positives → ↑ TPR, ↑ FPR  
- Higher threshold → fewer positives → ↓ TPR, ↓ FPR  

The curve shows how well the model **separates positives from negatives**.

---
## Visual Aid 
![[roc curve.png]]

## Shape Interpretation
- Diagonal line → Random classifier  
- Curve near top-left → Strong classifier  
- Perfect model → Point at (0, 1)

---

## Range & Interpretation
- ROC curve spans:
  - FPR: 0 → 1
  - TPR: 0 → 1
- Better curve:
  - Closer to top-left corner
  - Larger enclosed area

---

## When to Use
- You want **threshold-independent evaluation**
- You care about **ranking quality**
- Comparing multiple classifiers

---

## When NOT to Use
- Highly imbalanced datasets (can be misleading)
- Business focuses on positive class performance
- Precision matters more than recall

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌ (but interpretation can be misleading)
  - Threshold choice ❌
  - Outliers ❌
- Threshold-dependent: **No**

---

## Trade-offs
- Increasing TPR usually increases FPR
- No single “best” threshold from ROC alone

---

## Relationship to Other Metrics
- Uses: [[Sensitivity]] and [[False Positive Rate]]
- Area summarized by: [[AUC]]
- Alternative to: [[Precision Recall Curve]]

---

## Business Interpretation
ROC Curve helps decide **how aggressive or conservative** a model should be, depending on tolerance for false alarms versus missed positives.

---

## Example (Conceptual)
- Threshold = 0.9 → Low FPR, low TPR  
- Threshold = 0.5 → Balanced FPR & TPR  
- Threshold = 0.1 → High TPR, high FPR  

Each forms a point on the ROC curve.

---

## Variants / Extensions
- Partial ROC
- ROC for multiclass (OvR / OvO)

---

## Advantages
- Threshold-independent
- Good for model comparison
- Intuitive geometric interpretation

---

## Limitations
- Can be overly optimistic for imbalanced data
- Does not reflect precision
- No direct business cost encoding

---

## Common Misconceptions
- “ROC curve gives the best threshold” ❌
- “High ROC means high precision” ❌

---

## Interview Explanation (30 seconds)
The ROC curve plots true positive rate against false positive rate across thresholds, showing how well a model separates positives from negatives. It is threshold-independent and useful for comparing classifiers, though it can be misleading in highly imbalanced datasets.

---

## Links
- [[Sensitivity]]
- [[False Positive Rate]]
- [[AUC]]
- [[Precision Recall Curve]]

---
