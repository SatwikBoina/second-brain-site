- **Date of Entry:** 2026-01-31  
- **Tags:** #statistics #inference  


## One-line idea
When population variance is known, the confidence interval for the mean is built using the normal distribution.

---

## When this case applies

This scenario assumes:

- population standard deviation (σ) is known  
- samples are random and independent  
- population is normal **or** sample size is large  

This is mostly a theoretical case.

---

## Why normal distribution is used

From the Central Limit Theorem:

- the sampling distribution of the mean is normal  

When σ is known, uncertainty is fully quantified.

---

## Sampling distribution

Sample mean ~ Normal(μ, σ / √n)
The spread is the standard error.

---

## Confidence interval structure

estimate ± margin of error
For the mean:

$$
\bar{x} \pm z_{\alpha/2} \frac{\sigma}{\sqrt{n}}
$$

---

## Interpretation

- center → sample mean  
- width → uncertainty from sampling  

The z-value controls confidence level.

---

## Why this case matters

It introduces:

- CI construction logic  
- relationship between estimator and SE  
- role of sampling distribution  

All later CIs follow this structure.

---

## In short

> Known-variance CI uses the normal distribution because uncertainty is fully specified.

---
