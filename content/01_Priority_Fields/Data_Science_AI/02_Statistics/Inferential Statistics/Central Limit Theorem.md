- **Date of Entry:** 2026-01-31  
- **Tags:** #statistics #probability  

# Central Limit Theorem (CLT)

## One-line idea
The distribution of sample means becomes normal as sample size increases, regardless of the population distribution.

---

## The problem CLT solves

Real-world data is rarely normal:

- income is skewed  
- demand is uneven  
- customer behavior is messy  

Yet statistical inference almost always uses the normal distribution.

CLT explains why this works.

---

## What the theorem states

If we:

- repeatedly draw samples of size n  
- compute the sample mean each time  

then:
- distribution of sample means → normal

as n becomes large.

---

## Conceptual view

Population distribution (any shape)  
↓  
Repeated sampling  
↓  
Sample means  
↓  
Normal Distribution


---

## Important conditions

CLT holds when:

- samples are independent  
- sample size is sufficiently large  
- variance is finite  

The population itself does **not** need to be normal.

---

## What becomes normal

Not the data.

Not the population.

Only the **sampling distribution of the mean**.

---

## Why CLT is powerful

Because of CLT, we can:

- compute probabilities  
- build confidence intervals  
- perform hypothesis tests  
- use z-scores  

even when the original data is not normal.

---

## In short

> The Central Limit Theorem explains why normal distributions dominate statistical inference.

---
LLN → sample mean converges to μ
CLT → sample mean becomes normally distributed
![[LLN VS CLT.png]]