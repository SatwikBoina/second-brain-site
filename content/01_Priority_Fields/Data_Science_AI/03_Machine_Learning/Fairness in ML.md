---
type: concept
domain: machine-learning
category: ethics
status: evergreen
---

# Fairness in Machine Learning

> Fairness in ML refers to designing, training, and deploying models such that **no individual or group is systematically disadvantaged** due to protected or sensitive attributes.

---

## 1. Core Idea

Machine learning models learn from data — and **data reflects society**.

If historical data contains bias:
- Models will reproduce it
- Sometimes amplify it
- Often hide it behind accuracy

Fairness asks:
> *Who benefits, who is harmed, and why?*

---

## 2. Why Fairness Matters

Fairness is critical for:

- Ethical responsibility
- Legal compliance
- Trust and adoption
- Long-term system stability
- Avoiding real-world harm

Unfair models can be **accurate and harmful at the same time**.

---

## 3. Sources of Unfairness in ML

Fairness issues arise due to:

---

### 3.1 Biased Data

- Historical discrimination
- Under-representation of groups
- Measurement bias

Example:
- Loan data reflecting past exclusion

---

### 3.2 Feature Bias

- Proxy variables for sensitive attributes
- Correlated but seemingly innocent features

Example:
- Zip code acting as proxy for race

🔗 Related:
- [[Feature Engineering]]

---

### 3.3 Label Bias

- Subjective or inconsistent labeling
- Human bias in ground truth

---

### 3.4 Algorithmic Bias

- Loss functions optimizing wrong objective
- Metrics ignoring subgroup performance

🔗 Related:
- [[Classification Loss Functions — MOC]]
- [[Evaluation Metrics — MOC]]

---

## 4. Sensitive / Protected Attributes

Common sensitive attributes include:

- Gender
- Race / ethnicity
- Age
- Religion
- Disability
- Socioeconomic status

Fairness often focuses on **group-level effects**, not individuals.

---

## 5. Types of Fairness Definitions

⚠️ Important truth:
> You cannot satisfy all fairness definitions at once.

---

### 5.1 Demographic Parity

Outcome rates are equal across groups.

Example:
- Equal loan approval rates

✔ Simple  
❌ Ignores qualification differences

---

### 5.2 Equal Opportunity

True positive rates are equal across groups.

Example:
- Qualified candidates treated equally

✔ Often preferred  
❌ Ignores false positives

---

### 5.3 Equalized Odds

Both true positive and false positive rates are equal.

✔ Strong fairness  
❌ Often hard to achieve

---

### 5.4 Individual Fairness

Similar individuals receive similar predictions.

✔ Ideal  
❌ Hard to define similarity

---

## 6. Fairness vs Accuracy Trade-off

Often, improving fairness:
- Reduces overall accuracy
- Improves minority group outcomes

This is a **value choice**, not a technical mistake.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 7. Fairness and Class Imbalance

Minority classes often overlap with protected groups.

Ignoring class imbalance:
- Worsens fairness
- Penalizes already disadvantaged groups

🔗 Related:
- [[Class Imbalance]]

---

## 8. Fairness and Threshold Tuning

Different thresholds per group can:
- Improve fairness
- Reduce disparate impact

But may raise ethical and legal concerns.

🔗 Related:
- [[Threshold Tuning]]

---

## 9. Fairness and Interpretability

Interpretability enables fairness by:

- Identifying biased features
- Detecting proxy discrimination
- Auditing model behavior

Opaque models hide unfairness.

🔗 Related:
- [[Model Interpretability]]

---

## 10. Mitigation Strategies

---

### 10.1 Pre-processing Methods

- Re-sampling
- Re-weighting
- Fair representation learning

---

### 10.2 In-processing Methods

- Fairness-aware loss functions
- Constraints during training

🔗 Related:
- [[Custom Loss Functions]]

---

### 10.3 Post-processing Methods

- Threshold adjustment
- Output correction

---

## 11. Fairness Evaluation

Fairness must be **measured**, not assumed.

Evaluate:
- Metrics per subgroup
- Error rates across groups
- Calibration by group

🔗 Related:
- [[Evaluation Metrics — MOC]]
- [[Probability Calibration]]

---

## 12. Fairness and Data Leakage ⚠️

⚠️ Using protected attributes incorrectly can:
- Introduce leakage
- Create legal issues
- Backfire ethically

Fairness analysis ≠ fairness training.

🔗 Related:
- [[Data Leakage]]

---

## 13. Common Misconceptions

- ❌ Removing sensitive features ensures fairness  
- ❌ Fair models must be less accurate  
- ❌ Fairness is purely technical  
- ❌ One fairness metric fits all problems  

Fairness is **contextual and normative**.

---

## 14. When Fairness Is Non-Negotiable

- Hiring and recruitment
- Lending and credit
- Healthcare
- Criminal justice
- Education

In these domains, *accuracy alone is irresponsible*.

---

## 15. Why Fairness in ML Matters

Fairness explains:

- Why models fail society
- Why interpretability is essential
- Why metrics must go beyond accuracy
- Why ML is not value-neutral

Fairness is the **moral layer of ML systems**.

---

## Usage Notes

- Link this note from:
  - Model Interpretability
  - Class Imbalance
  - Threshold Tuning
  - Ethics & Governance
- Treat fairness as an ongoing process, not a checkbox
