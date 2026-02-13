- **Date of Entry:** 2026-01-31  
- **Tags:** #statistics #sampling  

# Independence Assumption

## One-line idea
The independence assumption states that the selection or value of one observation does not influence another.

---

## What independence means

Two observations are independent if:

- knowing one gives no information about the other  
- the outcome of one does not affect the outcome of another  

Each observation stands on its own.

---

## Conceptual view

Observation A ⟂ Observation B


No dependence. No linkage.

---

## Why this assumption exists

Statistical theory relies on independence to:

- derive sampling distributions  
- compute variance correctly  
- apply LLN and CLT  
- calculate standard errors  

Without independence, formulas break.

---

## Examples of independence

- random draws with replacement  
- independent customer purchases  
- coin tosses  

Each event does not affect the next.

---

## Examples of violation

- time-series data  
- clustered observations  
- social network data  
- sampling without replacement (small populations)  

Here observations influence one another.

---

## What happens if independence fails

Violations cause:

- underestimated standard errors  
- false significance  
- overly confident conclusions  

Models appear better than they are.

---

## Important clarification

Independence is an assumption — not a guarantee.

Random sampling supports independence, but does not ensure it.

---

## In short

> Independence ensures that information is not duplicated across observations.

---
Random Sampling
        ↓
Independence Assumption
        ↓
IID Assumption
