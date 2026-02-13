- **Date of Entry:** 2026-01-31  
- **Tags:** #statistics #estimation  


## One-line idea
Reducing bias usually increases variance, and reducing variance usually increases bias.

---

## Why the tradeoff exists

Estimators make assumptions.

- Strong assumptions → low variance, high bias  
- Weak assumptions → low bias, high variance  

You cannot minimize both simultaneously.

---

## Conceptual view

Simple estimator:  
↑ bias  
↓ variance

Flexible estimator:  
↓ bias  
↑ variance


---

## Example intuition

- Very simple model → stable but inaccurate  
- Very complex model → accurate but unstable  

The optimal estimator balances both.

---

## Total estimation error

Estimation error depends on both components:

Total error = bias² + variance

Reducing total error requires tradeoff.

---

## Why this matters

Bias–variance tradeoff explains:

- overfitting vs underfitting  
- model complexity selection  
- regularization techniques  
- why perfect models do not exist  

---

## Important insight

An unbiased estimator with huge variance can be worse than a biased estimator with small variance.

---

## In short

> Good estimation is about balance, not perfection.

---
