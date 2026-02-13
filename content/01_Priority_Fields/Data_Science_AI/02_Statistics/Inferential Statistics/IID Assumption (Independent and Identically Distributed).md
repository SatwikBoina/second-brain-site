- **Date of Entry:** 2026-01-31  
- **Tags:** #statistics #sampling  


## One-line idea
Observations are IID if they are independent of each other and drawn from the same population distribution.

---

## What IID means

IID has two components:

### 1. Independent  
- One observation does not influence another.

### 2. Identically distributed  
- All observations come from the same distribution.

Both conditions must hold.

---

## Conceptual view

X₁, X₂, X₃, ..., Xₙ ~ same distribution  
⟂  
independent


---

## Why IID matters

Most statistical results assume IID data, including:

- Law of Large Numbers  
- Central Limit Theorem  
- standard error formulas  
- confidence intervals  
- hypothesis tests  

If IID fails, inference may be invalid.

---

## Examples where IID holds

- simple random sampling  
- repeated controlled experiments  
- randomized A/B testing  

---

## Examples where IID fails

- time-series data (autocorrelation)  
- clustered data (schools, hospitals)  
- changing populations over time  
- network data  

---

## What happens if IID is violated

- biased estimates  
- incorrect uncertainty  
- false statistical significance  

Models may appear accurate but are not reliable.

---

## Important insight

Independence and identical distribution are separate assumptions.

You can violate one without violating the other.

---

## In short

> IID is the invisible foundation beneath almost all statistical inference.

---
