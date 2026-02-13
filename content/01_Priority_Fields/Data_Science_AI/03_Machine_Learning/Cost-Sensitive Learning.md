---
type: concept
domain: machine-learning
category: classification
status: evergreen
---

# Cost-Sensitive Learning

> Cost-sensitive learning is an approach where **different types of prediction errors incur different costs**, and the model is trained or configured to minimize *expected cost* rather than raw error.

---

## 1. Core Idea

Not all mistakes are equal.

In many real-world problems:
- False negatives can be far more costly than false positives (or vice versa)
- Accuracy treats all errors equally → wrong objective

Cost-sensitive learning asks:
> *What is the cost of being wrong in each way?*

---

## 2. Why Cost-Sensitive Learning Is Needed

Standard ML assumes:
- Equal error costs
- Balanced objectives

Reality involves:
- Financial loss
- Safety risk
- Legal exposure
- User harm

Optimizing accuracy can **optimize the wrong outcome**.

---

## 3. Common Real-World Examples

- Fraud detection → missing fraud is very costly
- Medical diagnosis → false negatives are dangerous
- Credit lending → false positives incur financial loss
- Spam detection → false positives annoy users

Cost, not frequency, drives decisions.

---

## 4. Cost Matrix

Costs are often defined using a **cost matrix**:

| Actual \ Predicted | Positive | Negative |
|-------------------|----------|----------|
| Positive | 0 | Cost(FN) |
| Negative | Cost(FP) | 0 |

The goal is to minimize **expected cost**, not error count.

---

## 5. Cost-Sensitive Learning vs Class Imbalance

Important distinction:

- **Class imbalance** → unequal class frequencies  
- **Cost sensitivity** → unequal error consequences  

They often co-exist, but are **not the same**.

🔗 Related:
- [[Class Imbalance]]

---

## 6. Approaches to Cost-Sensitive Learning

---

### 6.1 Algorithm-Level (In-Training)

Incorporate costs directly into training:

- Class weights
- Weighted loss functions
- Custom loss functions

Used in:
- Logistic Regression
- SVM
- Tree-based models
- Boosting models

🔗 Related:
- [[Custom Loss Functions]]
- [[Classification Loss Functions — MOC]]

---

### 6.2 Data-Level (Resampling)

Approximate costs via:
- Oversampling minority / high-cost class
- Undersampling low-cost class

⚠️ Indirect and imperfect

🔗 Related:
- [[Sampling Techniques]]

---

### 6.3 Prediction-Level (Post-Training)

Apply costs after training via:
- Threshold tuning
- Decision rules

Often simplest and safest.

🔗 Related:
- [[Threshold Tuning]]

---

## 7. Cost-Sensitive Learning and Threshold Tuning

Threshold selection can be derived from costs:

\[
\text{Optimal Threshold} =
\frac{Cost(FP)}{Cost(FP) + Cost(FN)}
\]

This directly links **business cost → decision rule**.

---

## 8. Cost-Sensitive Learning and Loss Functions

Loss functions can encode cost asymmetry:

- Weighted cross entropy
- Focal loss
- Asymmetric hinge loss
- Custom losses

Loss defines *what the model learns to fear*.

---

## 9. Evaluation Under Cost Sensitivity

Standard metrics may fail.

Better evaluation:
- Expected cost
- Cost-weighted accuracy
- Group-wise cost analysis

🔗 Related:
- [[Evaluation Metrics — MOC]]

---

## 10. Cost Sensitivity and Probability Calibration

Cost-sensitive decisions rely on:
- Accurate probabilities
- Well-calibrated outputs

Poor calibration → poor cost decisions.

🔗 Related:
- [[Probability Calibration]]

---

## 11. Cost Sensitivity and Fairness

Costs often differ across groups.

Risk:
- Cost-sensitive models may unintentionally amplify bias

Fairness analysis is mandatory.

🔗 Related:
- [[Fairness in Machine Learning]]

---

## 12. Common Mistakes

- ❌ Using accuracy in cost-sensitive problems  
- ❌ Guessing costs without domain input  
- ❌ Encoding costs twice (loss + threshold)  
- ❌ Ignoring calibration  

Cost-sensitive learning requires **clarity, not guesswork**.

---

## 13. When Cost-Sensitive Learning Helps Most

- High-stakes decisions
- Imbalanced problems with asymmetric harm
- Business-driven ML systems
- Regulated domains

---

## 14. When Cost Sensitivity Is Less Important

- Exploratory modeling
- Balanced datasets
- Symmetric error consequences

---

## 15. Why Cost-Sensitive Learning Matters

Cost-sensitive learning explains:

- Why accuracy is misleading
- Why thresholds matter
- Why business alignment beats leaderboard scores
- Why ML decisions must reflect consequences

It is the **decision-theoretic core of applied ML**.

---

## Usage Notes

- Link this note from:
  - Class Imbalance
  - Threshold Tuning
  - Custom Loss Functions
  - Model Selection
- Treat costs as first-class design inputs
