---
type: concept
domain: machine-learning
category: regression-theory
status: evergreen
---

# Gauss–Markov Assumptions

> The Gauss–Markov assumptions guarantee that the Ordinary Least Squares (OLS) estimator is the Best Linear Unbiased Estimator (BLUE).

---

# 1. One-Line Intuition

> If certain assumptions hold, OLS gives the lowest-variance unbiased linear estimator.

---

# 2. The Linear Model

We assume:

$$

y = X\beta + \epsilon 
$$
OLS estimator:
$$
\hat{\beta} = (X^T X)^{-1} X^T y
$$


Where:

- \(y\) = target vector
- \(X\) = design matrix
- \(\beta\) = coefficients
- \(\epsilon\) = error term

---

# 3. The Gauss–Markov Assumptions

There are five key assumptions.

---

## 3.1 Linearity in Parameters

The model is linear in coefficients:

$$
y = X\beta + \epsilon
$$
Not necessarily linear in features.

🔗 Related:
- [[Linearity Assumption]]

---

## 3.2 Random Sampling (IID Observations)

Observations are independently and identically distributed.

No systematic dependence.

🔗 Related:
- [[Independence of Errors]]

---

## 3.3 No Perfect Multicollinearity

Features are not perfectly linearly dependent.

$$
rank(X) = p
$$

Matrix \(X^T X\) must be invertible.

🔗 Related:
- [[Multicollinearity]]

---

## 3.4 Zero Conditional Mean

$$
E[\epsilon | X] = 0
$$

Errors are uncorrelated with predictors.

This ensures unbiasedness.

---

## 3.5 Homoscedasticity

$$
Var(\epsilon | X) = \sigma^2
$$

Constant variance of errors.

🔗 Related:
- [[Homoscedasticity]]

---

# 4. What the Gauss–Markov Theorem States

If assumptions 1–5 hold:

$$
\hat{\beta}_{OLS}
$$

is the:

> **Best Linear Unbiased Estimator (BLUE)**

Meaning:

- Linear estimator
- Unbiased
- Minimum variance among linear unbiased estimators

---

# 5. What “Best” Means

Best = Minimum Variance

Among all linear unbiased estimators:

$$
Var(\hat{\beta}_{OLS}) \le Var(\tilde{\beta})
$$

for any other linear unbiased estimator.

---

# 6. Important Clarification

Gauss–Markov does NOT require:

- Normality of errors

Normality is only needed for:

- Exact inference
- Hypothesis testing
- t-tests and F-tests

🔗 Related:
- [[Normality of Errors]]

---

# 7. What Happens If Assumptions Fail?

---

## Violate Linearity

→ Model misspecified  
→ Biased estimates  

---

## Violate Zero Conditional Mean

→ Omitted variable bias  
→ Endogeneity  

---

## Violate Homoscedasticity

→ OLS still unbiased  
→ Not minimum variance  
→ Use robust standard errors  

---

## Multicollinearity

→ High variance  
→ Unstable coefficients  

---

# 8. Geometric Interpretation

OLS projects:

\[
y
\]

onto the column space of:

\[
X
\]

Gauss–Markov guarantees:

- This projection has minimum variance among linear unbiased projections.

---

# 9. Gauss–Markov vs Maximum Likelihood

If errors are normal:

- OLS = Maximum Likelihood Estimator (MLE)

Without normality:

- OLS still BLUE
- But not necessarily MLE

🔗 Related:
- [[Maximum Likelihood Estimation]]

---

# 10. Bias–Variance Perspective

Gauss–Markov is fundamentally about:

- Variance minimization
- Under unbiased constraint

It is a variance-optimality theorem.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

# 11. Why It Matters in ML

In pure prediction tasks:

- Violations may not matter much.

In inference tasks:

- Assumptions are critical.
- Confidence intervals depend on them.

---

# 12. Relationship to Other Concepts

Gauss–Markov connects strongly to:

- [[Linear Regression]]
- [[Linearity Assumption]]
- [[Independence of Errors]]
- [[Homoscedasticity]]
- [[Multicollinearity]]
- [[Maximum Likelihood Estimation]]
- [[Bias–Variance Tradeoff]]

---

# 13. Why Gauss–Markov Matters

It teaches:

- Why OLS works
- What makes estimators optimal
- Difference between unbiasedness and efficiency
- Why regression assumptions exist

It is the theoretical foundation of:
> Classical linear regression.
