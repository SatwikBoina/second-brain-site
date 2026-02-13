---
type: zettel
domain: machine-learning
category: classification
topic: foundation
metric: Classification Threshold
tags: [classification, threshold, decision-boundary, fundamentals, model-evaluation]
---

# Classification Threshold

## One-line idea
> A cutoff value that converts predicted probabilities into class labels.

---

## Definition
A classification threshold is the probability value above which a model predicts the positive class and below which it predicts the negative class.

It bridges **probabilistic outputs** and **hard decisions**.

---

## Formal Rule
For a binary classifier producing probability \(p\):

\[
\hat{y} =
\begin{cases}
1 & \text{if } p \ge \tau \\
0 & \text{if } p < \tau
\end{cases}
\]

Where:
- \(\tau\) = classification threshold

---

## Intuition
Changing the threshold controls **model behavior**:

- Lower threshold → more positives → ↑ Recall, ↑ FPR  
- Higher threshold → fewer positives → ↑ Precision, ↑ Specificity  

The threshold determines **how aggressive or conservative** the model is.

---

## Default Threshold
- Common default: **0.5**
- Optimal threshold depends on:
  - Class imbalance
  - Business cost
  - Metric of interest

---

## When to Adjust Threshold
- Classes are imbalanced
- Business costs are asymmetric
- Precision–Recall tradeoff matters

---

## Sensitivity Analysis
- Affects:
  - [[Confusion Matrix]]
  - [[Precision]]
  - [[Recall]]
  - [[Specificity]]
  - [[False Positive Rate]]
- Threshold-dependent: **Yes (strongly)**

---

## Relationship to Metrics
Threshold movement changes:
- One point on the [[ROC Curve]]
- One point on the [[Precision Recall Curve]]

Entire curves are formed by sweeping the threshold.

---

## Business Interpretation
Threshold selection translates model predictions into **operational decisions**:
- Lower threshold → catch more risks but raise cost
- Higher threshold → save cost but miss opportunities

---

## Example
Predicted probability = 0.62

| Threshold | Prediction |
|---------|------------|
| 0.50 | Positive |
| 0.70 | Negative |

Same model, different decision.

---

## Threshold Optimization Strategies
- Maximize [[F1 Score]]
- Minimize expected cost
- Youden’s J Statistic
- Precision@K / Recall@K

---

## Multiclass Thresholds
- One-vs-Rest thresholds per class
- Argmax probability decision
- Cost-sensitive thresholds

---

## Advantages
- Simple to adjust
- Business-aligned control
- No retraining required

---

## Limitations
- Single threshold may not suit all segments
- Sensitive to probability calibration
- Can be unstable with small data

---

## Common Misconceptions
- “0.5 is the best threshold” ❌
- “Threshold tuning improves model quality” ❌

---

## Interview Explanation (30 seconds)
A classification threshold converts predicted probabilities into class labels. Adjusting it controls the tradeoff between false positives and false negatives and should be chosen based on business cost rather than defaulting to 0.5.

---

## Links
- [[Confusion Matrix]]
- [[ROC Curve]]
- [[Precision Recall Curve]]
- [[AUC ROC]]

---
