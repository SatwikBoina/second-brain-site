---
type: zettel
domain: machine-learning
category: classification
topic: foundation
metric: Probability vs Class Prediction
tags: [classification, probability, class-prediction, foundations, model-evaluation]
---

# Probability vs Class Prediction

## One-line idea
> Models predict probabilities; classes are assigned only after applying a decision rule.

---

## Definition
In classification, models typically output **probabilities**, not class labels.  
Class predictions are derived by applying a **classification threshold** or decision rule to these probabilities.

This distinction separates **model confidence** from **model decisions**.

---

## Probability Prediction
A probability prediction represents the model’s **degree of belief** that an instance belongs to a class.

Example:
- \(p(y=1) = 0.72\)

Meaning:
- The model estimates a **72% chance** of the positive class.

---

## Class Prediction
A class prediction converts probability into a **hard decision**.

Using threshold \(\tau\):

\[
\hat{y} =
\begin{cases}
1 & \text{if } p \ge \tau \\
0 & \text{if } p < \tau
\end{cases}
\]

Example:
- \(p = 0.72\)
- \(\tau = 0.5\) → Positive  
- \(\tau = 0.8\) → Negative  

---

## Intuition
- Probabilities answer: **“How confident is the model?”**
- Class labels answer: **“What action do we take?”**

Most metrics, curves, and business decisions depend on **how probabilities are converted into classes**.

---

## Key Differences

| Aspect | Probability | Class |
|------|-------------|-------|
| Output type | Continuous (0–1) | Discrete (0/1) |
| Threshold-dependent | ❌ | ✅ |
| Used for calibration | ✅ | ❌ |
| Used for decisions | Indirectly | Directly |

---

## Metrics by Prediction Type

### Probability-based Metrics
- [[Log Loss]]
- [[Binary Cross Entropy]]
- [[Brier Score]]
- [[Calibration Curve]]
- [[Expected Calibration Error]]

---

### Class-based Metrics
- [[Accuracy]]
- [[Precision]]
- [[Recall]]
- [[F1 Score]]
- [[Confusion Matrix]]

---

### Ranking-based Metrics
- [[ROC AUC]]
- [[Average Precision]]

---

## Relationship to Threshold
- Probabilities are **threshold-independent**
- Class predictions are **threshold-dependent**
- Sweeping thresholds generates:
  - [[ROC Curve]]
  - [[Precision Recall Curve]]

---

## Business Interpretation
Probabilities enable **flexible decision-making**:
- Different thresholds for different segments
- Cost-sensitive decisions
- Dynamic policy changes without retraining

---

## Common Pitfalls
- Treating probabilities as decisions
- Assuming 0.5 is optimal
- Evaluating probability models using only accuracy

---

## Advantages of Probability Outputs
- More information retained
- Threshold tuning flexibility
- Enables ranking and calibration

---

## Limitations
- Requires calibration
- Harder to interpret for non-technical stakeholders
- Can be overconfident

---

## Interview Explanation (30 seconds)
Classification models usually output probabilities, and class labels are produced by applying a threshold. Understanding this distinction is crucial because probability-based metrics evaluate confidence, while class-based metrics evaluate decisions, and thresholds connect the two.

---

## Links
- [[Classification Threshold]]
- [[Confusion Matrix]]
- [[ROC Curve]]
- [[Precision Recall Curve]]
- [[Calibration Curve]]

---
