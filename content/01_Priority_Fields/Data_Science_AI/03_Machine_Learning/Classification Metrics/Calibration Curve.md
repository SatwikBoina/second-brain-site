---
type: zettel
domain: machine-learning
category: classification
topic: evaluation-metric
metric: Calibration Curve
tags: [classification, metrics, calibration-curve, probability, calibration, model-evaluation]
---

# Calibration Curve (Reliability Diagram)

## One-line idea
> Visualizes how well predicted probabilities match actual outcome frequencies.

---

## Definition
A Calibration Curve plots **predicted probabilities** against **observed outcome frequencies** to assess whether a model’s confidence is trustworthy.

It is also called a **Reliability Diagram**.

---

## Construction Steps
1. Divide predictions into probability bins (e.g., 0–0.1, 0.1–0.2, …)
2. For each bin:
   - X-axis → average predicted probability
   - Y-axis → fraction of positives
3. Plot the points and compare to the diagonal

---

## Axes Definition
- **X-axis:** Mean predicted probability  
- **Y-axis:** Observed fraction of positives  

Reference line:
- \(y = x\) → Perfect calibration

---

## Intuition
- Curve above diagonal → Model is **underconfident**
- Curve below diagonal → Model is **overconfident**
- Close to diagonal → Well-calibrated probabilities

Calibration is about **confidence correctness**, not ranking.

---

## Range & Interpretation
- X-axis: 0 → 1  
- Y-axis: 0 → 1  
- Best curve:
  - Lies close to the diagonal

---

## When to Use
- Probabilities are used directly
- Decision thresholds may change
- Trust in confidence matters

Examples:
- Credit risk
- Medical prognosis
- Pricing & prioritization

---

## When NOT to Use
- Only class labels matter
- Ranking quality is the focus
- Very small datasets

---

## Sensitivity Analysis
- Sensitive to:
  - Binning strategy ✅
  - Sample size ✅
  - Class imbalance ❌
- Threshold-dependent: **No**

---

## Trade-offs
- Visual and intuitive
- Requires sufficient data per bin

---

## Relationship to Other Metrics
- Evaluated numerically by: [[Brier Score]]
- Summarized by: [[Expected Calibration Error]]
- Complementary to: [[Log Loss]]
- Orthogonal to: [[ROC AUC]]

---

## Business Interpretation
A well-calibrated model ensures that **“70% risk” truly means 70%**, enabling reliable downstream decision-making.

---

## Example (Conceptual)
Predicted probability ≈ 0.8  
Observed positives ≈ 0.6  
→ Model is **overconfident** in this region

---

## Variants / Extensions
- Isotonic Calibration Curve
- Platt-scaled Calibration Curve

---

## Advantages
- Highly interpretable
- Directly evaluates trustworthiness
- Business-friendly visualization

---

## Limitations
- No single summary score
- Sensitive to bin choice
- Does not measure ranking quality

---

## Common Misconceptions
- “Good ROC means good calibration” ❌
- “Calibration improves accuracy” ❌

---

## Interview Explanation (30 seconds)
A calibration curve shows whether predicted probabilities reflect true outcome frequencies. A well-calibrated model lies close to the diagonal, meaning its confidence can be trusted, which is critical when probabilities drive decisions.

---

## Links
- [[Brier Score]]
- [[Expected Calibration Error]]
- [[Log Loss]]
- [[ROC AUC]]

---
