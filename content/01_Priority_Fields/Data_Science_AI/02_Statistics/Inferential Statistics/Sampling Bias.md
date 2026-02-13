---
type: zettel
domain: statistics
category: inferential-statistics
topic: sampling
tags: [sampling, bias, inference, data-collection]
---

# Sampling Bias

## One-line idea
> Sampling bias occurs when the sampling process systematically excludes parts of the population, making the sample unrepresentative.

---

## Intuition
Imagine trying to estimate average income by surveying people inside a luxury mall.

You are sampling correctly **within the mall**,  
but the mall itself does not represent the full population.

The bias arises **before data is even collected**.

---

## Formal definition
Sampling bias occurs when:

\[
P(\text{being sampled} \mid \text{unit}) \neq \text{constant}
\]

meaning some population members have a higher or lower probability of selection than others.

---

## Where it occurs
- Poor sampling frame
- Convenience sampling
- Undercoverage of groups
- Geography-based sampling
- Time-based sampling (only weekdays, only nights)

---

## Example
Population: all voters in a city  
Sample: landline phone survey

Young voters are underrepresented → biased estimate of voting preference.

---

## Why it breaks inference
Inferential statistics assumes:

> the sample is a random draw from the population.

Sampling bias violates this assumption, causing:

- biased estimators
- incorrect confidence intervals
- invalid hypothesis tests
- misleading model coefficients

No amount of modeling can fix a biased sample.

---

## Key insight
> Sampling bias changes **who enters the dataset**.

Once excluded, those observations cannot be recovered statistically.

---

## Common mistakes
- Thinking large sample size fixes bias
- Assuming random-looking data is random sampling
- Applying confidence intervals on biased samples
- Treating scraped or platform data as population data

---

## Relationship to other concepts
- Sampling bias ≠ selection bias
- Occurs at **data collection stage**
- Affects population representativeness
- Happens before modeling

---

## Related zettels
- [[Selection Bias]]
