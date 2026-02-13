---
type: concept
domain: machine-learning
category: ensemble-learning
status: evergreen
---

# Bagging (Bootstrap Aggregating)

> Bagging is an ensemble technique that reduces variance by training multiple models on bootstrapped datasets and averaging their predictions.

---

## 1. One-Line Intuition

> Train many slightly different models and average them to cancel out noise.

---

## 2. Why Bagging Exists

Some models are:

- High variance
- Sensitive to small data changes
- Unstable

Example:
- Decision Trees

A small data change → completely different tree.

Bagging stabilizes such models.

---

## 3. Core Idea

Bagging has two main components:

1. Bootstrap Sampling  
2. Aggregation  

---

## 4. Step 1 — Bootstrap Sampling

Given dataset of size n:

- Sample n points **with replacement**
- Create new dataset
- Repeat multiple times

Each model sees:
- Slightly different training data

Some points:
- Repeated
- Some not included (Out-of-Bag samples)

---

## 5. Step 2 — Train Base Learners

Train one model per bootstrap sample.

Typically used with:
- Decision Trees
- High variance models

---

## 6. Step 3 — Aggregate Predictions

For regression:
\[
\hat{y} = \frac{1}{T} \sum_{t=1}^{T} f_t(x)
\]

For classification:
- Majority vote

Aggregation reduces variance.

---

## 7. Bias–Variance Perspective

Bagging:

- Does NOT reduce bias significantly
- Strongly reduces variance

Variance reduction works because:

\[
Var\left(\frac{1}{T} \sum f_t\right) = \frac{1}{T^2} \sum Cov(f_i, f_j)
\]

If models are weakly correlated:
→ Variance drops significantly.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 8. When Bagging Works Best

Bagging is most effective when:

- Base learner has high variance
- Base learner is unstable
- Dataset is noisy

Example:
- Decision Trees

Not very useful for:
- Linear Regression (already low variance)

---

## 9. Out-of-Bag (OOB) Error

Since bootstrap leaves out ~36% of samples:

- These can act as validation data.
- OOB error estimates generalization.

No need for separate validation set.

---

## 10. Bagging vs Boosting

| Aspect | Bagging | Boosting |
|----------|----------|----------|
| Goal | Reduce variance | Reduce bias |
| Training | Independent models | Sequential |
| Data | Bootstrap sampling | Reweighted data |
| Overfitting risk | Lower | Higher |
| Example | Random Forest | AdaBoost, XGBoost |

Bagging stabilizes.
Boosting corrects errors.

---

## 11. Bagging vs Random Forest

Random Forest is:

> Bagging + Random Feature Selection

Randomness is introduced in:

- Data sampling
- Feature selection per split

This reduces correlation further.

🔗 Related:
- [[Random Forest Classifier]]
- [[Random Forest Regressor]]

---

## 12. Mathematical Insight

If base models are independent:

\[
Var_{ensemble} = \frac{Var_{single}}{T}
\]

If correlated:

\[
Var_{ensemble} \approx \rho Var_{single}
\]

Where:
- ρ = correlation between models

Reducing correlation is key.

---

## 13. Strengths

- Simple
- Parallelizable
- Reduces overfitting
- Works well with trees
- OOB validation

---

## 14. Weaknesses

- Increased computation
- Limited bias reduction
- Large memory usage

---

## 15. When Bagging Is a Bad Idea

- When base learner already low variance
- When bias dominates error
- Very small datasets

---

## 16. Relationship to Other Concepts

Bagging connects strongly to:

- [[Ensemble Learning — MOC]]
- [[Random Forest Classifier]]
- [[Decision Tree Classifier]]
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 17. Why Bagging Matters

Bagging teaches:

- Variance reduction via averaging
- Stability of learning algorithms
- Importance of model correlation
- Foundations of Random Forest

It is the cleanest example of:
> Strength through diversity.
