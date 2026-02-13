---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Binary Cross Entropy
tags: [classification, metrics, binary-cross-entropy, log-loss, probability, model-evaluation]
---

# Binary Cross Entropy (BCE)

## One-line idea
> Measures the distance between true labels and predicted probabilities, heavily penalizing confident wrong predictions.

---

## Definition
Binary Cross Entropy measures how well predicted probabilities match the true binary outcomes.

It is **mathematically identical to Log Loss** in binary classification and is widely used as a **training loss function**.

---

## Formula
$$
\text{BCE} = -\frac{1}{N} \sum_{i=1}^{N}
\Big[ y_i \log(p_i) + (1 - y_i)\log(1 - p_i) \Big]
$$
Where:
- (y_i \in \{0,1\}) = true label  
- (p_i) = predicted probability of class 1  

---

## Intuition
Binary Cross Entropy:
- Rewards correct, confident predictions
- Severely penalizes confident mistakes
- Encourages **well-calibrated probabilities**

Wrong predictions with high confidence explode the loss.

---

## Range & Interpretation
- Range: \(0 \rightarrow \infty\)
- Best value: **Lower**
- Interpretation:
  - 0 → Perfect probabilistic predictions
  - High value → Poor probability estimation

---

## When to Use
- Binary classification
- Neural networks & logistic regression
- When probability quality matters more than labels

---

## When NOT to Use
- Only class labels are available
- You care only about ranking
- Interpretability over probabilities

---

## Sensitivity Analysis
- Sensitive to:
  - Class imbalance ❌
  - Threshold choice ❌
  - Outliers ✅ (very sensitive)
- Threshold-dependent: **No**

---

## Trade-offs
- Strong penalty discourages overconfidence
- Sensitive to noisy labels

---

## Relationship to Other Metrics
- Same as: [[Log Loss]]
- Special case of: [[Cross Entropy]]
- Related to: [[Brier Score]]
- Complementary to: [[ROC AUC]]

---

## Business Interpretation
Low binary cross entropy means **model confidence can be trusted**, which is critical when probabilities drive pricing, risk, or prioritization.

---

## Example
True label: \(y = 0\)

| Predicted Probability | BCE |
|----------------------|-----|
| 0.01 | Very small |
| 0.30 | Moderate |
| 0.50 | High |
| 0.99 | Extremely large |

---

## Variants / Extensions
- Categorical Cross Entropy
- Weighted Binary Cross Entropy
- Focal Loss

---

## Advantages
- Uses full probability information
- Differentiable and smooth
- Standard loss for binary classifiers

---

## Limitations
- Hard to interpret directly
- Sensitive to label noise
- Penalizes extreme predictions harshly

---

## Common Misconceptions
- “BCE is different from log loss” ❌
- “Lower BCE guarantees better accuracy” ❌

---

## Interview Explanation (30 seconds)
Binary Cross Entropy measures how close predicted probabilities are to true binary outcomes and heavily penalizes confident mistakes. It is mathematically the same as log loss and is commonly used as a training objective in classification models.

---

## Links
- [[Log Loss]]
- [[Brier Score]]
- [[Calibration Curve]]
- [[Cross Entropy]]

---

## Tags
#classification #binary-cross-entropy #log-loss #probability #metrics #model-evaluation
