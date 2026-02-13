---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Average Precision
tags: [classification, metrics, average-precision, pr-auc, model-evaluation]
---

# Average Precision (AP)

## One-line idea
> Summarizes the Precision–Recall curve by averaging precision across recall levels.

---

## Definition
Average Precision (AP) measures the area under the **Precision–Recall curve** by computing a weighted mean of precisions achieved at different recall thresholds.

It evaluates how well a model maintains **high precision while recall increases**.

---

## Formula
$$
\text{AP} = \sum_{n} (R_n - R_{n-1}) \cdot P_n
$$

Where:
- \(P_n\) = precision at step \(n\)  
- \(R_n\) = recall at step \(n\)

---

## Intuition
AP rewards models that:
- Retrieve **true positives early**
- Maintain high precision as recall grows

False positives early in ranking hurt AP significantly.

---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Higher  
- Interpretation:
  - 1.0 → Perfect precision at all recall levels
  - Baseline ≈ positive class prevalence

---

## When to Use
- **Highly imbalanced datasets**
- Positive class is critical
- Ranking quality of positives matters

Examples:
- Fraud detection
- Information retrieval
- Lead scoring

---

## When NOT to Use
- True negatives matter
- Dataset is balanced
- Probability calibration is the goal

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ✅
  - Threshold choice ❌
  - Outliers ❌
- Threshold-dependent: **No**

---

## Trade-offs
- Focuses only on positive class
- Ignores negative-class performance

---

## Relationship to Other Metrics
- Area under: [[Precision Recall Curve]]
- Alternative to: [[ROC AUC]] (for imbalance)
- Related to: [[Precision at K]]

---

## Business Interpretation
Average Precision measures how effectively a model **prioritizes high-value positives**, minimizing wasted effort on false alarms.

---

## Example (Conceptual)
If a model:
- Has high precision for top-ranked predictions
- Precision drops slowly as recall increases  

→ AP will be high.

---

## Variants / Extensions
- Mean Average Precision (mAP)
- Macro AP
- Micro AP
- Weighted AP

---

## Advantages
- Honest for imbalanced problems
- Strong ranking interpretation
- Widely used in IR and ML competitions

---

## Limitations
- Less intuitive than ROC-AUC
- Ignores true negatives
- Sensitive to ranking noise

---

## Common Misconceptions
- “AP equals ROC AUC” ❌
- “High AP guarantees high recall” ❌

---

## Interview Explanation (30 seconds)
Average Precision summarizes the precision–recall curve into a single score and is especially useful for imbalanced datasets. It emphasizes ranking positives early with high precision, making it preferable to ROC AUC in many real-world problems.

---

## Links
- [[Precision Recall Curve]]
- [[ROC AUC]]
- [[Precision at K]]
- [[Imbalanced Classification]]

---
