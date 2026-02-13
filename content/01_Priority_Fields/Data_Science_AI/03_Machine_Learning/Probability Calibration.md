---
type: concept
domain: machine-learning
category: probabilistic-models
status: evergreen
---

# Probability Calibration

> Probability calibration adjusts a model’s predicted probabilities so that they reflect true empirical likelihoods.

---

## 1. One-Line Intuition

> If a model predicts 70% probability, about 70% of those cases should actually be positive.

---

## 2. What Calibration Means

A classifier is **well-calibrated** if:

\[
P(Y=1 \mid \hat{p} = 0.7) \approx 0.7
\]

That means:

- Among all predictions near 0.7,
- About 70% are truly positive.

---

## 3. Accuracy vs Calibration

A model can:

- Have high accuracy
- Have high AUC
- Still be poorly calibrated

Example:

Model predicts:
- 0.99 for most positives
- 0.01 for most negatives

But true probabilities:
- Around 0.7 and 0.3

High discrimination, poor calibration.

---

## 4. Why Calibration Matters

Calibration is critical for:

- Medical diagnosis
- Credit risk
- Fraud detection
- Decision thresholds
- Cost-sensitive learning

Probabilities drive decisions.

🔗 Related:
- [[Threshold Tuning]]
- [[Cost Sensitive Learning]]

---

## 5. Calibration Curve (Reliability Diagram)

Procedure:

1. Divide predictions into bins.
2. Compute:
   - Average predicted probability per bin
   - True fraction of positives per bin
3. Plot predicted vs actual.

Perfect calibration:
- Diagonal line.

---

## 6. Common Calibration Problems

---

### 6.1 Overconfident Model

Predictions too extreme:
- 0.99 when true probability ≈ 0.8

Common in:
- Deep neural networks
- Boosting

---

### 6.2 Underconfident Model

Predictions too moderate:
- 0.6 when true probability ≈ 0.8

---

## 7. Common Calibration Methods

---

## 7.1 Platt Scaling

- Fit logistic regression on model logits.
- Maps scores to calibrated probabilities.

\[
P(y=1) = \sigma(ax + b)
\]

Works well for:
- SVM
- Boosted trees

---

## 7.2 Isotonic Regression

- Non-parametric calibration.
- Monotonic mapping.
- Flexible but may overfit small datasets.

---

## 7.3 Temperature Scaling (Neural Networks)

For softmax logits:

\[
Softmax(z_i / T)
\]

T > 1:
- Smooths probabilities.
- Reduces overconfidence.

Common in deep learning.

🔗 Related:
- [[Softmax Function]]

---

## 8. Calibration and Loss Functions

Cross-entropy encourages:

- Good probability estimation.

But some models:

- Optimize margin (e.g., SVM).
- Do not optimize probability directly.

Thus require calibration.

🔗 Related:
- [[Cross Entropy]]
- [[Hinge Loss]]

---

## 9. Calibration vs Discrimination

Discrimination:
- Ability to rank positives higher than negatives.
- Measured by AUC.

Calibration:
- Accuracy of predicted probabilities.
- Measured by Brier score.

Both are different properties.

---

## 10. Brier Score

\[
\text{Brier} = \frac{1}{n} \sum (y_i - \hat{p}_i)^2
\]

Lower Brier score:
- Better calibrated probabilities.

---

## 11. Which Models Are Well-Calibrated?

Often well-calibrated:
- Logistic Regression

Often poorly calibrated:
- Random Forest
- Gradient Boosting
- Neural Networks
- SVM

---

## 12. Calibration and Bias–Variance

Overfitting models:

- Overconfident predictions.
- Poor calibration.

Regularization and early stopping help.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Early Stopping]]

---

## 13. Calibration vs Interpretability

Even if feature importance is clear:

- Probability may still be unreliable.

Interpretability ≠ calibration.

🔗 Related:
- [[Model Interpretability]]

---

## 14. Strengths of Calibration

- Improves decision-making
- Makes probabilities trustworthy
- Improves threshold selection
- Important for risk-sensitive systems

---

## 15. Limitations

- Requires validation data
- May overfit if not careful
- Adds extra modeling layer

---

## 16. Relationship to Other Concepts

Probability Calibration connects strongly to:

- [[Logistic Regression]]
- [[Softmax Function]]
- [[Sigmoid Function]]
- [[Cross Entropy]]
- [[Threshold Tuning]]
- [[Cost Sensitive Learning]]
- [[Evaluation Metrics MOC]]

---

## 17. Why Probability Calibration Matters

Calibration teaches:

- Difference between ranking and probability
- Why probabilities must match reality
- How modern models become overconfident
- How to make ML predictions decision-ready

It is essential for:
> Production-grade ML systems.
