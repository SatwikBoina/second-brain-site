- **Date of Entry:** 2026-01-31  
- **Tags:** #statistics #sampling  


## One-line idea
The sampling distribution of the proportion describes how sample proportions vary across repeated samples.

---

## What it is

Instead of computing sample means, we:

- repeatedly draw samples of size n  
- compute the sample proportion each time  

The distribution of these proportions forms the sampling distribution.

---

## Conceptual view

Population with true proportion p  
↓ sample  
Sample 1 → p̂₁  
Sample 2 → p̂₂  
Sample 3 → p̂₃  
↓  
Sampling distribution of p̂


---

## What it describes

It captures:

- variability of sample proportions  
- uncertainty in estimating the true proportion  

Each point is one sample proportion.

---

## Key properties

- Center = population proportion (p)  
- Spread = standard error √[ p(1 − p) / n ]  
- Shape ≈ normal (for large n)  

---

## Normal approximation condition

Sampling distribution of proportion is approximately normal when:

- np ≥ 10  
- n(1 − p) ≥ 10  

This ensures sufficient successes and failures.

---

## Why it matters

Inference about:

- conversion rates  
- defect rates  
- approval percentages  

is entirely based on this distribution.

---

## Important clarification

It is not the distribution of binary outcomes.

It is the distribution of the **proportion statistic**.

---

## In short

> Proportion inference works because sample proportions follow a predictable sampling distribution.

---
