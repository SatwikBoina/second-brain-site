---
type: zettel
domain: statistics
category: inferential-statistics
topic: sampling
tags: [selection-bias, inference, causality, data-generating-process]
---

# Selection Bias

## One-line idea
> Selection bias occurs when inclusion in the dataset depends on the outcome or variables related to the outcome.

---

## Intuition
You only observe people who survived.

But survival itself depends on what you are trying to study.

This creates distorted relationships in the data.

---

## Formal definition
Selection bias occurs when:

\[
P(\text{observed} \mid X, Y) \neq P(\text{observed})
\]

meaning the probability of appearing in the dataset depends on explanatory variables or outcomes.

---

## Where it occurs
- Self-selection
- Attrition or dropout
- Platform opt-in data
- Conditioning on post-treatment variables
- Observing only successful cases

---

## Example
Studying whether training improves performance using:

> only employees who completed training

Employees who dropped out are excluded — and dropout is related to performance.

---

## Why it breaks inference
Selection bias creates:

- spurious correlations
- biased regression coefficients
- false causal conclusions

Even with random sampling, selection bias can still occur.

---

## Key insight
> Selection bias changes **who remains in the dataset** after the process starts.

---

## Famous example
Survivorship bias in World War II aircraft analysis.

Only planes that returned were analyzed — missing those that were shot down.

---

## Common mistakes
- Controlling for variables affected by treatment
- Analyzing only “successful” users
- Ignoring churned customers
- Using platform activity data as behavior truth

---

## Relationship to other concepts
- Occurs **after sampling**
- Related to causal inference
- Often invisible in raw data
- Cannot be detected from data alone

---

## Related zettels
- [[Sampling Bias]]

Sampling bias → who gets sampled  
Selection bias → who remains observed
