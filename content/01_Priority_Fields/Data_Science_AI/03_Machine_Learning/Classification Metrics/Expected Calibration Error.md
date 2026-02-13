---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Expected Calibration Error
tags: [classification, metrics, ece, calibration, probability, model-evaluation]
---

# Expected Calibration Error (ECE)

## One-line idea
> Measures how far predicted probabilities deviate from actual outcome frequencies on average.

---

## Definition
Expected Calibration Error (ECE) quantifies the **average gap** between predicted probabilities and observed frequencies across probability bins.

It provides a **single-number summary** of calibration quality.

---

## Formula
$$
\text{ECE} = \sum_{m=1}^{M} \frac{|B_m|}{N}
\left| \text{acc}(B_m) - \text{conf}(B_m) \right|
$$

Where:
- \(B_m\) = m-th probability bin  
- \(\text{acc}(B_m)\) = fraction of positives in bin  
- \(\text{conf}(B_m)\) = average predicted probability in bin  
- \(N\) = total number of samples  

---

## Intuition
ECE answers:  
**“On average, how wrong is my model’s confidence?”**

- Low ECE → well-calibrated probabilities  
- High ECE → over- or under-confident predictions  

---
## Visual Aid :
![[calibration curve.png]]
## Range & Interpretation
- Range: 0 → 1  
- Best value: **Lower**
- Interpretation:
  - 0 → Perfect calibration
  - Higher values → unreliable confidence

---

## When to Use
- Probabilities are used in decisions
- You want a **single calibration metric**
- Comparing calibration across models

---

## When NOT to Use
- Very small datasets
- Binning choice is unstable
- Ranking quality is primary concern

---

## Sensitivity Analysis
- Sensitive to:
  - Binning strategy ✅
  - Sample size ✅
  - Class imbalance ❌
- Threshold-dependent: **No**

---

## Trade-offs
- Simple numeric summary
- Loses fine-grained calibration detail

---

## Relationship to Other Metrics
- Numeric summary of: [[Calibration Curve]]
- Complementary to: [[Brier Score]]
- Orthogonal to: [[ROC AUC]]

---

## Business Interpretation
Low ECE means predicted probabilities can be **trusted at face value**, enabling consistent and risk-aware decisions.

---

## Example (Conceptual)
If predictions around 0.7 result in:
- Actual positives ≈ 0.5  

→ That bin contributes **0.2 error** to ECE.

---

## Variants / Extensions
- Maximum Calibration Error (MCE)
- Adaptive ECE
- Classwise ECE

---

## Advantages
- Simple scalar calibration metric
- Easy model comparison
- Interpretable

---

## Limitations
- Sensitive to binning choice
- Can hide local calibration issues
- Not differentiable

---

## Common Misconceptions
- “Low ECE means good ranking” ❌
- “ECE replaces calibration curve” ❌

---

## Interview Explanation (30 seconds)
Expected Calibration Error measures the average difference between predicted probabilities and actual outcomes across bins. It summarizes calibration quality into a single number and is useful when model confidence must be trusted.

---

## Links
- [[Calibration Curve]]
- [[Brier Score]]
- [[Log Loss]]
- [[Maximum Calibration Error]]

---
