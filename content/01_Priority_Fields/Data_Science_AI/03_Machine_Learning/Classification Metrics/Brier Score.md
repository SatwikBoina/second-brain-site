---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Brier Score
tags: [classification, metrics, brier-score, probability, calibration, model-evaluation]
---

# Brier Score

## One-line idea
> Measures the mean squared error between predicted probabilities and actual outcomes.

---

## Definition
The Brier Score evaluates the accuracy of probabilistic predictions by computing the squared difference between predicted probabilities and true binary labels.

Unlike log loss, it penalizes errors **quadratically** rather than exponentially.

---

## Formula
$$
\text{Brier Score} = \frac{1}{N} \sum_{i=1}^{N} (p_i - y_i)^2
$$
Where:
- \(p_i\) = predicted probability of the positive class  
- \(y_i \in \{0,1\}\) = true label  

---

## Intuition
Brier Score:
- Rewards well-calibrated probabilities
- Penalizes overconfidence smoothly
- Is more forgiving than log loss

It behaves like **MSE for probabilities**.

## Visual Intuition :
![[brier score.png]]

---

## Range & Interpretation
- Range: 0 → 1 (binary classification)
- Best value: **Lower**
- Interpretation:
  - 0 → Perfect probability predictions
  - ≈ 0.25 → Random guessing (balanced data)

---

## When to Use
- You care about **probability calibration**
- Predictions drive downstream decisions
- Interpretability of probability errors matters

Examples:
- Weather forecasting
- Risk scoring
- Medical prognosis

---

## When NOT to Use
- Ranking is the main goal
- Extreme penalties for confident mistakes are needed
- Pure label accuracy is sufficient

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌
  - Threshold choice ❌
  - Outliers ⚠️ (less than log loss)
- Threshold-dependent: **No**

---

## Trade-offs
- Less harsh than log loss
- May under-penalize confident wrong predictions

---

## Relationship to Other Metrics
- Alternative to: [[Log Loss]]
- Related to: [[Binary Cross Entropy]]
- Used with: [[Calibration Curve]]

---

## Business Interpretation
Brier Score reflects how **trustworthy probability estimates** are, making it ideal when probabilities are used directly in business rules or pricing.

---

## Example
True label: \(y = 1\)

| Predicted Probability | Brier Score |
|----------------------|-------------|
| 0.90 | 0.01 |
| 0.70 | 0.09 |
| 0.50 | 0.25 |
| 0.10 | 0.81 |

---

## Variants / Extensions
- Multiclass Brier Score
- Decomposed Brier Score (reliability, resolution, uncertainty)

---

## Advantages
- Simple interpretation
- Calibration-focused
- Robust to noisy probabilities

---

## Limitations
- Less sensitive to ranking errors
- Not ideal for rare-event detection
- Scale depends on class prevalence

---

## Common Misconceptions
- “Lower Brier means better ranking” ❌
- “Brier replaces log loss” ❌

---

## Interview Explanation (30 seconds)
Brier Score measures the mean squared error between predicted probabilities and actual outcomes. It focuses on probability calibration and is less harsh than log loss, making it useful when probabilities are directly used in decision-making.

---

## Links
- [[Log Loss]]
- [[Binary Cross Entropy]]
- [[Calibration Curve]]
- [[Expected Calibration Error]]

---
