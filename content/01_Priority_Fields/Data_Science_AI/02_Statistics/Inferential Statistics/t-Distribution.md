- **Date of Entry:** 2026-01-31  
- **Tags:** #statistics #inference  


## One-line idea
The t-distribution accounts for extra uncertainty introduced when the population variance is unknown.

---

## Why the t-distribution exists

If population variance were known:

- sampling distribution of the mean would be normal  

But in reality:

- σ is unknown  
- we estimate it using sample standard deviation s  

This estimation adds uncertainty.

---

## What goes wrong with normal distribution

When we replace σ with s:

- the denominator becomes random  
- variability increases  

Normal distribution no longer applies exactly.

---

## Solution

The t-distribution corrects for this additional uncertainty.

---

## Key characteristics

- symmetric like the normal distribution  
- heavier tails  
- wider spread  

Heavier tails reflect higher uncertainty.

---

## Degrees of freedom

The shape of the t-distribution depends on:

df = n − 1

- small df → very wide tails  
- large df → close to normal  

---

## Conceptual view

Small sample → more uncertainty → wider tails  
Large sample → less uncertainty → normal


---

## Convergence to normal

As sample size increases:

t-distribution → normal distribution


This is why z and t intervals become identical for large n.

---

## Why it matters

The t-distribution ensures:

- correct coverage probability  
- honest confidence intervals  
- valid hypothesis tests  

when variance is unknown.

---

## In short

> The t-distribution exists because we estimate uncertainty from the same data.

---
