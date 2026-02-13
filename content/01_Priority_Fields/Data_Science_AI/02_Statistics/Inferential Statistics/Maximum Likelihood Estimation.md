- **Date of Entry:** 2026-01-31  
- **Tags:** #statistics #estimation  

# (MLE)

## One-line idea
Maximum Likelihood Estimation chooses parameter values that make the observed data most probable.

---

## Core question MLE asks

Given the data we observed:

> Which parameter values would most likely have generated it?

---

## Conceptual view

Parameters → probability model  
↓  
Observed data  
↓  
Likelihood of data


MLE selects the parameters that maximize this likelihood.

---

## What likelihood means

Likelihood is:

- probability of the data  
- viewed as a function of parameters  

Data is fixed.  
Parameters vary.

---

## Example intuition

If a parameter value explains the data well:

- likelihood is high  

If it explains poorly:

- likelihood is low  

MLE chooses the best explanation.

---

## Why MLE is powerful

MLE:

- uses full probability model  
- exploits entire data distribution  
- produces consistent estimators  
- is asymptotically efficient  

---

## Properties of MLE

- consistent  
- asymptotically normal  
- asymptotically efficient  
- often sufficient  

This is why MLE dominates estimation theory.

---

## Important note

MLE is not guaranteed to be unbiased for small samples.

Its strength lies in large-sample behavior.

---

## In short

> MLE finds the parameter values under which the observed data is most plausible.

---
Probability: P(data | parameters)
Likelihood:  same expression, different viewpoint


# Maximum Likelihood Estimation — Unified View

## One-line idea
Maximum Likelihood Estimation chooses parameter values that make the observed data most plausible under a statistical model.

---

## Core estimation question

Given:

- observed data (fixed)  
- a probabilistic model with unknown parameters  

Which parameter values best explain the data?

MLE answers this by maximizing likelihood.

---

## Probability vs likelihood

| Concept | Varies | Meaning |
|------|------|------|
| Probability | Data | P(data \| parameters) |
| Likelihood | Parameters | L(parameters \| data) |

Same formula.  
Different interpretation.

---

## Likelihood intuition

- Data is fixed  
- Parameters move  

Higher likelihood means:

> the model explains the observed data better.

---

## Log-likelihood

Because likelihoods multiply:

- products become numerically unstable  

We take logarithms:

maximize likelihood  
≡ maximize log-likelihood


Log-likelihood:

- converts products → sums  
- simplifies optimization  
- preserves maxima  

---

## Why MLE works

MLE works because:

- sample likelihood concentrates near true parameters  
- wrong parameters assign low probability to observed data  
- likelihood surface peaks at the truth  

As sample size increases:


---

## Statistical guarantees

Under mild conditions, MLE is:

- consistent  
- asymptotically normal  
- asymptotically efficient  

It reaches the lowest possible variance.

---

## Relationship to sampling distributions

MLE operates on:

- the sampling distribution of the data  

Inference is derived from:

- curvature of the log-likelihood  
- Fisher information  

---

## Key insight

> MLE does not find the most probable parameter —  
> it finds the parameter under which the observed data is most probable.

---

## In short

> Maximum likelihood turns probability models into parameter-learning machines.

---
