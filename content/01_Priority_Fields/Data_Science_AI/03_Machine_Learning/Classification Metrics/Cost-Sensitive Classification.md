---
type: zettel
domain: machine-learning
category: classification
topic: foundation
metric: Cost-Sensitive Classification
tags: [classification, cost-sensitive, decision-theory, foundations, model-evaluation]
---

# Cost-Sensitive Classification

## One-line idea
> A classification approach that explicitly accounts for different costs of prediction errors.

---

## Definition
Cost-Sensitive Classification incorporates **unequal misclassification costs** into model evaluation, threshold selection, or training, instead of assuming all errors are equally bad.

It reframes classification as a **decision-making problem**, not just a prediction task.

---

## Motivation
In real-world problems:
- False positives and false negatives rarely cost the same
- Optimizing accuracy can be economically suboptimal

Cost-sensitive methods align models with **business impact**.

---

## Cost Matrix (Binary Classification)

| Actual \ Predicted | Positive | Negative |
|--------------------|----------|----------|
| Positive           | C(TP)    | C(FN)    |
| Negative           | C(FP)    | C(TN)    |

Where:
- C(FN) ≫ C(FP) → missing positives is very costly  
- C(FP) ≫ C(FN) → false alarms are very costly  

Often:
- C(TP) = 0  
- C(TN) = 0  

---

## Expected Cost
For a single prediction with probability \(p = P(y=1)\):

$$
\text{Expected Cost} =
p \cdot C(\text{FN}) + (1 - p) \cdot C(\text{FP})
$$

The decision rule minimizes expected cost.

---

## Intuition
Instead of asking:
> “Is this prediction correct?”

Cost-sensitive classification asks:
> “Which decision minimizes expected loss?”

This often leads to **non-0.5 thresholds**.

---

## Relationship to Threshold
Optimal threshold:

\[
\tau^* = \frac{C(\text{FP})}{C(\text{FP}) + C(\text{FN})}
\]

- Higher FN cost → lower threshold  
- Higher FP cost → higher threshold  

---

## Where Cost Can Be Applied

### 1. During Evaluation
- Expected loss
- Cost-weighted accuracy

### 2. During Threshold Selection
- Choose threshold minimizing business cost
- Segment-specific thresholds

### 3. During Training
- Class weights
- Cost-weighted loss functions
- Sampling strategies

---

## Metrics Commonly Used
- [[Expected Loss]]
- [[Precision]]
- [[Recall]]
- [[F-beta Score]]
- [[Cost Matrix]]

Curves:
- [[ROC Curve]] (with cost-based operating point)
- [[Precision Recall Curve]]

---

## Business Interpretation
Cost-sensitive classification ensures the model’s decisions are:
- Economically optimal
- Aligned with risk tolerance
- Actionable at scale

Example:
- Fraud → FN very expensive  
- Marketing → FP very expensive  

---

## When to Use
- Business costs are asymmetric
- Decisions have real-world consequences
- Thresholds must be justified economically

---

## When NOT to Use
- All errors truly have equal cost
- Exploratory modeling
- Costs are unknown or unstable

---

## Advantages
- Business-aligned modeling
- Explicit decision logic
- Reduces hidden risk

---

## Limitations
- Requires cost estimation
- Costs may change over time
- More complex to explain

---

## Common Misconceptions
- “Cost-sensitive means retraining the model” ❌
- “Accuracy already captures cost” ❌

---

## Interview Explanation (30 seconds)
Cost-sensitive classification accounts for unequal costs of false positives and false negatives. Instead of maximizing accuracy, it minimizes expected business loss, often by adjusting thresholds or using weighted losses.

---

## Links
- [[Confusion Matrix]]
- [[Classification Threshold]]
- [[Probability vs Class Prediction]]
- [[Cost Matrix]]
- [[Expected Loss]]

---

