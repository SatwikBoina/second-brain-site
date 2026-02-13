- **Date of Entry:** 2026-01-31  
- **Tags:** #statistics #estimation  


(Consistency • Efficiency • Sufficiency)

## One-line idea
A good estimator should converge to the truth, use information efficiently, and retain all relevant information from the data.

---

## The three fundamental properties

Classical estimation theory evaluates estimators using three core properties:

1. **Consistency**  
2. **Efficiency**  
3. **Sufficiency**

Each answers a different question.

---

## Conceptual comparison

| Property | Core Question | What it Measures |
|--------|----------------|------------------|
| Consistency | Does it converge to the true parameter? | Long-run accuracy |
| Efficiency | How precise is it compared to others? | Variance |
| Sufficiency | Does it use all information in the data? | Information retention |

---

## 1️⃣ Consistency

An estimator is **consistent** if:

- as sample size increases  
- the estimate approaches the true parameter  

More data → better estimate.

Consistency concerns **asymptotic behaviour**.

---

## 2️⃣ Efficiency

Among unbiased estimators:

- the one with the smallest variance is most efficient  

Efficiency determines:

- precision  
- narrow confidence intervals  
- optimal use of data  

It is a relative concept.

---

## 3️⃣ Sufficiency

A statistic is sufficient if:

- it captures all information in the sample about the parameter  
- no additional data improves estimation  

Once known, raw data is unnecessary.

---

## Key differences

| Aspect | Consistency | Efficiency | Sufficiency |
|------|-------------|-------------|-------------|
| Focus | Convergence | Precision | Information |
| Depends on sample size | Yes | Yes | No |
| Long-run concept | Yes | No | No |
| Variance-related | Indirect | Direct | Indirect |
| Data compression | No | No | Yes |

---

## Important insight

An estimator can be:

- consistent but inefficient  
- efficient but not sufficient  
- sufficient but biased  

No single property guarantees optimal estimation alone.

---

## In short

> Good estimation requires convergence, precision, and full use of information.

---

# Common Estimators and Their Properties

## One-line idea
Different estimators possess different combinations of consistency, efficiency, and sufficiency depending on how they use sample information.

---

## Estimator Comparison Table


| Estimator                              | Formula                                    | Consistent | Efficient    | Sufficient   | Why                                                                            |
| -------------------------------------- | ------------------------------------------ | ---------- | ------------ | ------------ | ------------------------------------------------------------------------------ |
| **Sample Mean**                        | $\bar{x} = \frac{1}{n}\sum x_i$<br>        | ✅ Yes      | ✅ Yes*       | ✅ Yes*       | Converges by LLN; minimum variance under normality; sufficient for μ in normal |
| **Sample Median**                      | middle value                               | ✅ Yes      | ❌ No         | ❌ No         | Converges to median but has higher variance                                    |
| **Sample Variance (s²)**               | $( \frac{1}{n-1}\sum(x_i-\bar{x})^2 )$<br> | ✅ Yes      | ❌ No         | ✅ Yes*       | Consistent; not minimum variance; sufficient with mean in normal               |
| **Sample Proportion**                  | $( \hat{p} = \frac{X}{n} )$<br>            | ✅ Yes      | ✅ Yes*       | ✅ Yes        | MLE for Bernoulli; attains CRLB                                                |
| **Method of Moments Estimator**        | equate moments                             | ✅ Yes      | ❌ Usually no | ❌ Usually no | Simple but inefficient                                                         |
| **Maximum Likelihood Estimator (MLE)** | maximize likelihood                        | ✅ Yes      | ✅ Yes        | ✅ Often      | Asymptotically efficient and sufficient                                        |
| **Unbiased Variance Estimator**        | \( s^2 \)                                  | ✅ Yes      | ❌ No         | ❌ No         | Trades variance for unbiasedness                                               |
| **Biased Variance Estimator**          | $( \frac{1}{n}\sum(x_i-\bar{x})^2 )$       | ✅ Yes      | ✅ Yes        | ❌ No         | Lower variance but biased                                                      |
| **Trimmed Mean**                       | drop extremes                              | ✅ Yes      | ❌ No         | ❌ No         | Robust but loses efficiency                                                    |
| **Sample Maximum**                     | max(x)                                     | ❌ No       | ❌ No         | ❌ No         | Does not converge to mean                                                      |

\* under normal-distribution assumptions

---

## Key insights

### ✅ Consistency
- Most reasonable estimators are consistent.
- Consistency depends on **LLN**.

---

### ⚖️ Efficiency
- Efficiency depends on estimator variance.
- MLEs are asymptotically efficient.
- Median is less efficient than mean.

---

### 📦 Sufficiency
- Rare property.
- Holds mainly for exponential-family distributions.
- Normal distribution is special.

---

## Important patterns

| Pattern | Observation |
|------|------|
| Mean vs Median | Mean is efficient; median is robust |
| MOM vs MLE | MOM is simple; MLE is optimal |
| Unbiased vs Biased | Slight bias can reduce variance |
| Sufficiency | Mostly occurs in normal models |

---

## Master insight

> There is no universally best estimator — only estimators optimized for different goals.

---

## One-line memory anchor
Consistency → eventually correct  
Efficiency → most precise  
Sufficiency → no information wasted
