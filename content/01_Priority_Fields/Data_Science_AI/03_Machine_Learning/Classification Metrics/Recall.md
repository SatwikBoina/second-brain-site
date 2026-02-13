---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Recall
tags: [classification, metrics, recall, sensitivity, model-evaluation]
---

# Recall

## One-line idea
> Measures how many actual positives the model successfully identifies.

---

## Definition
Recall is the fraction of correctly predicted positive instances out of all actual positive instances.

It answers the question:  
**“Of all the real positives, how many did the model catch?”**

---

## Formula
\[
\text{Recall} = \frac{TP}{TP + FN}
\]

Where:
- TP = True Positives  
- FN = False Negatives  

---

## Intuition
Recall focuses on **coverage of the positive class**.

- High recall → very few misses  
- Low recall → many positives go undetected  

It does **not** care about false positives.

---

## Range & Interpretation
- Range: 0 → 1  
- Best value: Higher  
- Interpretation:
  - 1.0 → All positives detected
  - Low recall → Model is conservative or blind to positives

---

## When to Use
- Missing a positive is **very costly**
- You want maximum detection
- Examples:
  - Fraud detection
  - Disease screening
  - Churn prediction

---

## When NOT to Use
- False positives are costly
- You need confidence in predictions
- Alone, without Precision

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌
  - Threshold choice ✅
  - Outliers ❌
- Threshold-dependent: **Yes**

---

## Trade-offs
- Increasing recall usually:
  - Decreases precision
- Capturing more positives introduces false alarms

---

## Relationship to Other Metrics
- Also called: [[Sensitivity]]
- Complements: [[Precision]]
- Combined into: [[F1 Score]]
- Opposite focus of: [[Specificity]]

---

## Business Interpretation
High recall ensures **important events are not missed**,  
but operational costs may increase due to false positives.

---

## Example
Confusion Matrix:

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | 80       | 20       |
| Negative           | 100      | 800      |

\[
Recall = \frac{80}{80 + 20} = 0.80
\]

---

## Variants / Extensions
- Recall@K
- Macro Recall
- Micro Recall
- Weighted Recall

---

## Advantages
- Captures minority class performance
- Critical for risk-sensitive domains
- Simple interpretation

---

## Limitations
- Ignores false positives
- Can encourage over-prediction
- Misleading if used alone

---

## Common Misconceptions
- “High recall means accurate model” ❌
- “Recall measures prediction quality” ❌

---

## Interview Explanation (30 seconds)
Recall measures how many actual positives a model successfully detects. It is crucial when missing positives is costly, such as fraud or medical diagnosis, but must be balanced with precision to control false positives.

---

## Links
- [[Precision]]
- [[F1 Score]]
- [[Sensitivity]]
- [[Precision Recall Tradeoff]]

---

