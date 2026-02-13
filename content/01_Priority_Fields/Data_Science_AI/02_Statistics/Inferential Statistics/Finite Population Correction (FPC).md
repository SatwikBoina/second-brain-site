- **Date of Entry:** 2026-01-31  
- **Tags:** #statistics #sampling  


## One-line idea
Finite population correction adjusts uncertainty when sampling without replacement from a small population.

---

## Why FPC exists

Most statistical formulas assume:

- very large (effectively infinite) populations  
- sampling with replacement  

But in reality:

- populations can be small  
- sampling is often without replacement  

This reduces uncertainty.

---

## What changes in small populations

When sampling without replacement:

- each selected unit removes variability  
- remaining units become more predictable  

Sampling becomes more informative.

---

## Conceptual view

Large population → minimal impact of each draw  
Small population → each draw matters


---

## When FPC is required

Finite population correction is used when:

- sampling without replacement  
- sample size is large relative to population  
- typically when n / N ≥ 5%

---

## Effect of FPC

FPC:

- reduces standard error  
- reflects reduced uncertainty  
- improves precision estimates  

Ignoring it overestimates uncertainty.

---

## Important insight

As sample size approaches population size:

- uncertainty approaches zero  

Because we are observing most of the population.

---

## In short

> When the population is small, sampling contains more information than standard formulas assume.

---
Infinite population → no correction
Finite population → reduced uncertainty
