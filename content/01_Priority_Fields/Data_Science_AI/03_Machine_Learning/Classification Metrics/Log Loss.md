---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Log Loss
tags: [classification, metrics, log-loss, cross-entropy, probability, model-evaluation]
---

# Log Loss (Logarithmic Loss)

## One-line idea
> Measures how close predicted probabilities are to the true class, penalizing confident wrong predictions heavily.

---

## Definition
Log Loss evaluates a classification model by comparing **predicted probabilities** with actual class labels.  
It strongly penalizes predictions that are **confident but wrong**.

Also known as **Binary Cross-Entropy** in binary classification.

---

## Formula (Binary Classification)
$$
\text{Log Loss} = -\frac{1}{N} \sum_{i=1}^{N} \Big[ y_i \log(p_i) + (1 - y_i)\log(1 - p_i) \Big]
$$

Where:
- $$(y_i \in \{0,1\}) $$= true label  
- $(p_i)$= predicted probability of class 1  

---

## Intuition
Log Loss cares about **probability calibration**.

- Correct & confident → very small loss  
- Wrong & confident → huge loss  
- Uncertain (≈0.5) → moderate loss  

It discourages overconfidence.

---
## Visual Aid :
![[Log-loss.png]]
## Range & Interpretation
- Range: \(0 \rightarrow \infty\)
- Best value: **Lower**
- Interpretation:
  - 0 → Perfect probability predictions
  - Large value → Poorly calibrated or overconfident model

---

## When to Use
- Model outputs **probabilities**
- Decision thresholds may change
- You care about **confidence correctness**

Examples:
- Risk modeling
- Credit scoring
- Ensemble optimization

---

## When NOT to Use
- Only class labels are available
- Interpretability is more important than probability quality
- Extreme outliers dominate decisions

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌
  - Threshold choice ❌
  - Outliers ✅ (very sensitive)
- Threshold-dependent: **No**

---

## Trade-offs
- Encourages calibrated probabilities
- Harsh penalty for confident mistakes

---

## Relationship to Other Metrics
- Same as: [[Binary Cross Entropy]]
- Related to: [[Brier Score]]
- Complementary to: [[ROC AUC]]

---

## Business Interpretation
Log Loss reflects how **trustworthy model confidence** is.  
A low log loss means probabilities can be safely used in downstream business decisions.

---

## Example
True label: \(y = 1\)

| Predicted Probability | Log Loss |
|----------------------|----------|
| 0.99 | Very small |
| 0.70 | Small |
| 0.51 | Moderate |
| 0.01 | Extremely large |

---

## Variants / Extensions
- Multiclass Log Loss
- Categorical Cross-Entropy

---

## Advantages
- Uses full probability information
- Strong theoretical foundation
- Differentiable (good for training)

---

## Limitations
- Harder to interpret
- Sensitive to mislabeled data
- Penalizes extreme confidence harshly

---

## Common Misconceptions
- “Low log loss means high accuracy” ❌
- “Log loss is threshold-based” ❌

---

## Interview Explanation (30 seconds)
Log loss measures how close predicted probabilities are to the true labels and heavily penalizes confident wrong predictions. It is useful when probability calibration matters and is commonly used as a training objective.

---

## Links
- [[Binary Cross Entropy]]
- [[Brier Score]]
- [[Calibration Curve]]
- [[ROC AUC]]

---
