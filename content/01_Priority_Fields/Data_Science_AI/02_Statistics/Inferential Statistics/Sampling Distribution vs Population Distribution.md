- **Date of Entry:** 2026-01-31  
- **Tags:** #statistics #probability  

## One-line idea
A population distribution describes individual data points, while a sampling distribution describes a statistic computed from many samples.

---

## Population distribution

- Distribution of **individual observations**
- Comes directly from the data generating process
- Each data point is one realization

Examples:

- heights of people  
- incomes of households  
- daily sales values  

It answers:

> How are individual values distributed?

---

## Sampling distribution

- Distribution of a **statistic**, not raw data
- Built by repeatedly sampling from the population
- Most commonly based on the sample mean

Each point in this distribution is:

> one statistic from one sample

---

## Conceptual view

![[pop dist vs samp dist.png]]
---

## Key differences

| Population Distribution | Sampling Distribution |
|------------------------|-----------------------|
| Individual values | Statistics |
| One dataset | Many samples |
| Describes data | Describes estimators |
| Spread = population variance | Spread = standard error |
| Shape can be anything | Often normal (CLT) |

---

## Why inference happens here

Inference does **not** operate on raw data.

It operates on:

> the distribution of statistics across samples.

Confidence intervals, p-values, and tests are all derived from the sampling distribution.

---

## Core insight

> Data lives in the population distribution.  
> Inference lives in the sampling distribution.

---

## In short

> Population distribution describes reality.  
> Sampling distribution describes our uncertainty about reality.

---
