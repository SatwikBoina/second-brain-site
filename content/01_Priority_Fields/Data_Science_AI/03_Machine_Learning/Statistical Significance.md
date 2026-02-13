---
type: concept
domain: machine-learning
category: statistical-inference
status: evergreen
---

# Statistical Significance

> Statistical significance measures whether an observed effect is unlikely to have occurred by random chance under a null hypothesis.

---

# 1. One-Line Intuition

> If the effect is very unlikely under “no effect,” we call it statistically significant.

---

# 2. Hypothesis Testing Framework

For a regression coefficient \( \beta_j \):

Null hypothesis:

\[
H_0: \beta_j = 0
\]

Alternative hypothesis:

\[
H_1: \beta_j \neq 0
\]

We test whether the data provides strong evidence against \(H_0\).

---

# 3. Test Statistic (t-statistic)

\[
t = \frac{\hat{\beta}_j}{SE(\hat{\beta}_j)}
\]

Where:

- \( \hat{\beta}_j \) = estimated coefficient
- \( SE(\hat{\beta}_j) \) = standard error

Large |t| → strong evidence against null.

---

# 4. p-value

The p-value measures:

> Probability of observing a result at least as extreme as this one, assuming the null hypothesis is true.

Small p-value:

- Evidence against null.
- Typically threshold: 0.05.

---

# 5. Statistical Significance ≠ Practical Importance

A coefficient can be:

- Statistically significant
- But practically tiny

Large datasets:
- Even small effects become significant.

Always consider:
- Effect size
- Domain relevance

---

# 6. Connection to Confidence Intervals

If 95% confidence interval for \( \beta_j \):

- Does NOT include 0 → significant at 5% level.

Confidence interval:

\[
\hat{\beta}_j \pm t^* \cdot SE(\hat{\beta}_j)
\]

---

# 7. Assumptions Required

Statistical significance in linear regression requires:

- Linearity
- Independence
- Homoscedasticity
- No perfect multicollinearity
- (For exact inference) Normality of errors

🔗 Related:
- [[Gauss–Markov Assumptions]]
- [[Normality of Errors]]

---

# 8. Why Standard Errors Matter

Coefficient estimate may be large.

But if variance is large:
- SE increases.
- t-stat decreases.
- May not be significant.

Multicollinearity inflates SE.

🔗 Related:
- [[Multicollinearity]]

---

# 9. Significance in Logistic Regression

Uses:

- Wald test
- Likelihood ratio test

Still based on:

\[
\frac{\hat{\beta}}{SE(\hat{\beta})}
\]

But derived from MLE.

---

# 10. Statistical Significance vs Predictive Performance

In ML:

- We care about prediction accuracy.
- Not necessarily coefficient significance.

Tree models:
- No p-values.
- Focus on validation performance.

Inference vs prediction is different.

---

# 11. Multiple Testing Problem

If testing many features:

- Some appear significant by chance.

Solutions:
- Bonferroni correction
- False Discovery Rate (FDR)

---

# 12. Type I and Type II Errors

Type I error:
- Reject true null.
- False positive.

Type II error:
- Fail to reject false null.
- False negative.

Significance level α controls Type I error rate.

---

# 13. Statistical Significance and Sample Size

Larger sample size:

- Smaller standard errors.
- More likely to find significance.

Small sample size:
- Harder to detect effects.

---

# 14. Relationship to Maximum Likelihood

Under normal errors:

- OLS = MLE
- t-tests derived from sampling distribution of estimator.

🔗 Related:
- [[Maximum Likelihood Estimation]]

---

# 15. Common Misinterpretations

p-value does NOT mean:

- Probability that null is true.
- Probability that effect is important.
- Proof of causality.

It only measures evidence under assumed model.

---

# 16. When Statistical Significance Matters Most

- Scientific research
- Policy analysis
- Causal modeling
- Small-sample inference

Less critical in:
- Pure predictive ML systems.

---

# 17. Relationship to Other Concepts

Statistical Significance connects strongly to:

- [[Linear Regression]]
- [[Gauss–Markov Assumptions]]
- [[Normality of Errors]]
- [[Multicollinearity]]
- [[Maximum Likelihood Estimation]]
- [[Bias–Variance Tradeoff]]

---

# 18. Why Statistical Significance Matters

It teaches:

- Difference between estimation and inference.
- Why assumptions matter.
- How uncertainty is quantified.
- Why coefficients may not mean what we think.

It is central to:
> Classical statistical modeling.
