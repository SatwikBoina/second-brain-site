---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: F-beta Score
tags: [classification, metrics, f-beta, fbeta, model-evaluation]
---


## One-line idea
> A weighted harmonic mean of precision and recall that emphasizes recall or precision based on business priority.

---

## Definition
F-beta Score generalizes the F1 score by introducing a weight **β** that controls the relative importance of **recall** versus **precision**.

It answers:  
**“How much more do I care about missing positives vs raising false alarms?”**

---

## Formula
$$
\text{F}_{\beta} = (1 + \beta^2)\cdot \frac{\text{Precision} \cdot \text{Recall}}{(\beta^2 \cdot \text{Precision}) + \text{Recall}}
$$

Where:
- β > 1 → Recall is emphasized
- β < 1 → Precision is emphasized
- β = 1 → F1 Score

---

## Intuition
F-beta lets you **encode business preference** into the metric:

- Large β → *“Missing positives is very bad”*
- Small β → *“False positives are very bad”*

The harmonic mean still penalizes imbalance.

---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Higher  
- Interpretation:
  - 1.0 → Perfect precision and recall (per β)
  - Lower values → imbalance or poor detection

---

## When to Use
- Precision and recall have **unequal importance**
- Business costs are asymmetric
- Examples:
  - Fraud detection (β > 1)
  - Spam filtering (β < 1)
  - Medical screening (β ≫ 1)

---

## When NOT to Use
- True negatives matter
- Costs are unknown
- Probability calibration is required

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌
  - Threshold choice ✅
  - Outliers ❌
- Threshold-dependent: **Yes**

---

## Trade-offs
- Explicitly biases toward:
  - Recall (β > 1)
  - Precision (β < 1)
- Can hide poor performance of the less-weighted metric

---

## Relationship to Other Metrics
- Generalizes: [[F1 Score]]
- Combines: [[Precision]] and [[Recall]]
- Alternative to: [[Accuracy]] in imbalanced data

---

## Business Interpretation
F-beta Score allows stakeholders to **quantify business risk tolerance** directly in the evaluation metric.

---

## Example
Assume:
- Precision = 0.60  
- Recall = 0.80  

For β = 2 (recall-focused):

\[
F_2 = \frac{5 \cdot (0.60 \cdot 0.80)}{(4 \cdot 0.60) + 0.80} = 0.75
\]

---

## Variants / Extensions
- F0.5 Score (precision-focused)
- F2 Score (recall-focused)
- Macro Fβ
- Micro Fβ
- Weighted Fβ

---

## Advantages
- Encodes business priorities
- Flexible generalization of F1
- Suitable for imbalanced datasets

---

## Limitations
- Choice of β is subjective
- Ignores true negatives
- Threshold sensitive

---

## Common Misconceptions
- “Fβ is always better than F1” ❌
- “β is a hyperparameter of the model” ❌

---

## Interview Explanation (30 seconds)
F-beta Score generalizes F1 by allowing us to weigh recall or precision depending on business cost. A higher β emphasizes recall, making it useful in risk-sensitive domains like fraud or healthcare.

---

## Links
- [[F1 Score]]
- [[Precision]]
- [[Recall]]
- [[Imbalanced Classification]]

---

## Tags
#classification #f-beta #fbeta #metrics #model-evaluation
