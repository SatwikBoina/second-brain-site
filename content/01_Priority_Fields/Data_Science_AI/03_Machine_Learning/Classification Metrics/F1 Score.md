---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: F1 Score
tags: [classification, metrics, f1-score, model-evaluation]
---

# F1 Score

## One-line idea
> Measures the harmonic mean of precision and recall, balancing false positives and false negatives.

---

## Definition
F1 Score combines **precision** and **recall** into a single metric using the harmonic mean, penalizing extreme imbalance between the two.

It answers:  
**“How good is the model at finding positives without over-predicting them?”**

---

## Formula

$$\text{F1} = 2 \cdot \frac{\text{Precision} \cdot \text{Recall}}{\text{Precision} + \text{Recall}}
$$

Where:
$$
\text{Precision} = \frac{TP}{TP + FP}, \quad
\text{Recall} = \frac{TP}{TP + FN}
$$

---

## Intuition
The harmonic mean:
- Punishes low values harshly
- Requires **both** precision and recall to be high

A model with:
- High precision & low recall → **low F1**
- High recall & low precision → **low F1**

---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Higher  
- Interpretation:
  - 1.0 → Perfect precision and recall
  - 0.0 → Completely failed detection

---

## When to Use
- Classes are **imbalanced**
- Precision and recall are **equally important**
- You need a **single-number summary**

---

## When NOT to Use
- One error type is more costly than the other
- True negatives matter
- You need probability-based evaluation

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌
  - Threshold choice ✅
  - Outliers ❌
- Threshold-dependent: **Yes**

---

## Trade-offs
- Balances precision vs recall
- Hides which component is failing

---

## Relationship to Other Metrics
- Combines: [[Precision]] and [[Recall]]
- Special case of: [[F-beta Score]]
- Alternative to: [[Accuracy]] in imbalanced data

---

## Business Interpretation
F1 Score reflects **operational effectiveness** when both missed opportunities and false alarms are costly.

---

## Example
Confusion Matrix:

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | 40       | 60       |
| Negative           | 20       | 880      |

\[
Precision = \frac{40}{60} = 0.67
\]

\[
Recall = \frac{40}{100} = 0.40
\]

\[
F1 = 2 \cdot \frac{0.67 \cdot 0.40}{0.67 + 0.40} = 0.50
\]

---

## Variants / Extensions
- Fβ Score (weighted recall vs precision)
- Macro F1
- Micro F1
- Weighted F1

---

## Advantages
- Robust for imbalanced datasets
- Penalizes extreme tradeoffs
- Simple single metric

---

## Limitations
- Ignores true negatives
- Threshold sensitive
- Not probability-aware

---

## Common Misconceptions
- “F1 captures overall performance” ❌
- “Higher F1 always means better business outcome” ❌

---

## Interview Explanation (30 seconds)
F1 Score is the harmonic mean of precision and recall, ensuring that both false positives and false negatives are controlled. It is widely used in imbalanced classification problems where accuracy is misleading.

---

## Links
- [[Precision]]
- [[Recall]]
- [[F-beta Score]]
- [[Imbalanced Classification]]

---

