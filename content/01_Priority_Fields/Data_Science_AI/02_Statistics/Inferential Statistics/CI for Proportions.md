- **Date of Entry:** 2026-01-31  
- **Tags:** #statistics #inference  

# Confidence Interval for Proportions

## One-line idea
A confidence interval for a proportion estimates the true population proportion using the sampling distribution of the sample proportion.

---

## What we are estimating

- Population proportion → p  
- Sample proportion → p̂  

Examples:

- conversion rate  
- defect rate  
- approval percentage  

---

## Sampling distribution

For large samples:

p̂ ≈ Normal( p , √ p(1 − p) / n  )


This result comes from the Central Limit Theorem.

---

## Standard error

\[
SE_{\hat{p}} = \sqrt{\frac{\hat{p}(1-\hat{p})}{n}}
\]

This measures uncertainty in the estimated proportion.

---

## Confidence interval form

\[
\hat{p} \pm z_{\alpha/2} \cdot SE_{\hat{p}}
\]

---

## Normal approximation condition

The normal approximation is valid when:

- n p̂ ≥ 10  
- n (1 − p̂) ≥ 10  

This ensures enough successes and failures.

---

## Interpretation

- center → sample proportion  
- width → estimation uncertainty  

---

## Why proportions use z, not t

Because variance is estimated directly from the Bernoulli model.

No extra uncertainty layer is introduced.

---

## In short

> Proportion confidence intervals rely on normal approximation of the sampling distribution.

---
