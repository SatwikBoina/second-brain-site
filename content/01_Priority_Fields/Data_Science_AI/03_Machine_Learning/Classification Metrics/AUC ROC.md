---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: AUC
tags: [classification, metrics, auc, roc-auc, model-evaluation]
---

# AUC (Area Under the ROC Curve)

## One-line idea
> Measures how well a model ranks positives higher than negatives across all thresholds.

---

## Definition
AUC is the area under the ROC Curve and represents the probability that the model assigns a higher score to a randomly chosen positive instance than to a randomly chosen negative instance.

---

## Mathematical Interpretation
$$
AUC = P(\hat{y}_{positive} > \hat{y}_{negative})
$$

---

## Intuition
AUC evaluates **ranking quality**, not classification accuracy.

- AUC = 0.5 → Random ranking  
- AUC = 1.0 → Perfect ranking  
- AUC < 0.5 → Inverted ranking  

It ignores the actual threshold.

---
## Visual Aid
![[auc_roc.png]]
---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Higher  
- Interpretation:
  - 0.9–1.0 → Excellent
  - 0.7–0.9 → Good
  - 0.5 → Random

---

## When to Use
- You want **threshold-independent comparison**
- Ranking matters more than absolute predictions
- Examples:
  - Credit scoring
  - Lead ranking
  - Risk prioritization

---

## When NOT to Use
- Highly imbalanced datasets
- Precision at top ranks is critical
- Business costs are asymmetric

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌ (can be misleading)
  - Threshold choice ❌
  - Outliers ❌
- Threshold-dependent: **No**

---

## Trade-offs
- Strong ranking does not guarantee good classification
- High AUC may hide poor precision

---

## Relationship to Other Metrics
- Area under: [[ROC Curve]]
- Alternative to: [[Accuracy]]
- Compared with: [[PR AUC]]

---

## Business Interpretation
AUC reflects how well the model **prioritizes risk or opportunity**, but does not guarantee optimal operational decisions.

---

## Example
Suppose:
- Model A: AUC = 0.85  
- Model B: AUC = 0.82  

Model A ranks positives above negatives more consistently, even if accuracy is similar.

---

## Variants / Extensions
- ROC-AUC
- Macro AUC
- Micro AUC
- Weighted AUC
- Partial AUC

---

## Advantages
- Threshold-independent
- Interpretable probabilistic meaning
- Robust for model comparison

---

## Limitations
- Overly optimistic for imbalanced data
- Ignores probability calibration
- Not directly actionable

---

## Common Misconceptions
- “High AUC means high accuracy” ❌
- “AUC gives best threshold” ❌

---

## Interview Explanation (30 seconds)
AUC measures a model’s ability to rank positive instances above negative ones across all thresholds. It’s threshold-independent and useful for comparing models, but it can be misleading in highly imbalanced datasets.

---

## Links
- [[ROC Curve]]
- [[Precision Recall Curve]]
- [[Log Loss]]
- [[Threshold Optimization]]

---
