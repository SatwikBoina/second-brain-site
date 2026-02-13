---
type: concept
domain: machine-learning
category: evaluation
status: evergreen
---

# Error Analysis

> Error analysis is the systematic process of **examining model mistakes** to understand *why* they occur and *how* to fix them.

---

## 1. Core Idea

Evaluation metrics tell you **how bad** a model is.  
Error analysis tells you **why**.

Key shift:
> Stop optimizing numbers. Start understanding failures.

---

## 2. Why Error Analysis Matters

Without error analysis:
- You tune blindly
- You chase noise
- You plateau early

With error analysis:
- Improvements become targeted
- Feature engineering becomes purposeful
- Model selection becomes justified

Most performance gains come from **fixing the right errors**, not changing algorithms.

---

## 3. Error Analysis vs Evaluation Metrics

| Aspect | Evaluation Metrics | Error Analysis |
|---|---|---|
| Purpose | Measure performance | Understand failures |
| Output | Numbers | Insights |
| Granularity | Aggregate | Instance / segment-level |
| Actionability | Indirect | Direct |

Metrics decide *if* you improve.  
Error analysis decides *how*.

---

## 4. Types of Errors to Analyze

---

### 4.1 Prediction-Level Errors

Look at individual wrong predictions:
- What was predicted?
- What was the true label?
- How confident was the model?

High-confidence wrong predictions are **red flags**.

---

### 4.2 Error by Class / Segment

Break errors by:
- Class
- Subgroup
- Feature ranges
- Time windows
- Geography

Aggregate metrics often hide **localized failures**.

🔗 Related:
- [[Fairness in Machine Learning]]

---

### 4.3 Error by Probability / Confidence

Analyze:
- Low-confidence correct predictions
- High-confidence incorrect predictions

This reveals:
- Calibration issues
- Threshold problems

🔗 Related:
- [[Probability Calibration]]
- [[Threshold Tuning]]

---

### 4.4 Error by Data Quality

Common causes:
- Missing values
- Noisy labels
- Outliers
- Incorrect preprocessing

🔗 Related:
- [[Handling Missing Data]]
- [[Outliers]]

---

## 5. Confusion Matrix as a Starting Point

For classification, error analysis often begins with:
- False positives
- False negatives

But should not end there.

Ask:
> Which false negatives matter most?

🔗 Related:
- [[Classification Metrics — MOC]]

---

## 6. Error Analysis for Regression

Key approaches:
- Residual plots
- Error vs feature plots
- Segment-wise MAE / RMSE

Look for:
- Systematic bias
- Heteroscedasticity
- Non-linear patterns

🔗 Related:
- [[Regression Metrics — MOC]]

---

## 7. Error Analysis and Bias–Variance

Error patterns reveal:
- High bias → systematic errors
- High variance → unstable, noisy errors

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Overfitting vs Underfitting]]

---

## 8. Error Analysis and Feature Engineering

Error analysis often answers:
- What feature is missing?
- What interaction is needed?
- What transformation helps?

Most feature ideas come from **studying failures**.

🔗 Related:
- [[Feature Engineering]]
- [[Interaction Terms]]

---

## 9. Error Analysis and Model Choice

Error patterns can indicate:
- Model too simple
- Model too complex
- Wrong inductive bias

Changing models without error analysis is guessing.

🔗 Related:
- [[Model Selection]]

---

## 10. Error Analysis Under Class Imbalance

Aggregate metrics hide minority-class errors.

Always inspect:
- Minority class false negatives
- Costly mistakes

🔗 Related:
- [[Class Imbalance]]
- [[Cost-Sensitive Learning]]

---

## 11. Error Analysis and Fairness

Check if errors are:
- Disproportionately affecting groups
- Systematically biased

Fairness issues often surface only during error analysis.

🔗 Related:
- [[Fairness in Machine Learning]]

---

## 12. Practical Error Analysis Workflow

1. Fix evaluation metric
2. Identify worst error type
3. Segment errors
4. Inspect raw examples
5. Hypothesize causes
6. Apply targeted fixes
7. Re-evaluate

Iterate deliberately.

---

## 13. Common Anti-Patterns

- ❌ Only looking at overall metrics  
- ❌ Random hyperparameter tuning  
- ❌ Ignoring high-confidence errors  
- ❌ Treating all errors as equal  
- ❌ Skipping manual inspection  

Error analysis requires **human judgment**.

---

## 14. When Error Analysis Is Most Valuable

- Plateaued model performance
- High-stakes decisions
- Imbalanced data
- Business-critical systems
- Fairness-sensitive applications

---

## 15. Why Error Analysis Matters

Error analysis explains:

- Why models fail silently
- Why feature engineering works
- Why metrics mislead
- Why iteration must be intentional

It is the **feedback loop that turns ML into engineering**.

---

## Usage Notes

- Link this note from:
  - Evaluation Metrics — MOC
  - Model Selection
  - Feature Engineering
  - Fairness in Machine Learning
- Treat error analysis as a mandatory step, not optional
