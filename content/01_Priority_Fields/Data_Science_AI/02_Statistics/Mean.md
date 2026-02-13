
- **Date of Entry:** 30-12-2025
- **Tags:** #statistics #descriptive_stats 


### 1️⃣ Definition

- It is also called as average.
- It's ratio of sum of observations & the number of observations
**Note :** The formula for the sample and population mean is different. It's because the sample mean is over-estimated. It uses the concept of [[Degrees of Freedom]] to correct the mean.
---

###  2️⃣ Analogy / Intuition

**Newton's Law of Gravitation :** 
Think of mean as a "Centre of Gravity" of that feature. Every data point tries to pull the mean towards itself. But the data with high magnitude essentially wins, as it has the power to make any feature skewed.

#### Visual Aid :
![[Mean Tug of war.png]]

**Examples:**
- Bill Gates Effect : When you consider the average salary of the members of a book club who attended today. It will change when the "Bill Gates" is part of your club.
---

### 3️⃣ Formula
| **Feature**     | **Population Mean (μ)**                | **Sample Mean (xˉ)**                       |
| --------------- | -------------------------------------- | ------------------------------------------ |
| **Symbol**      | $\mu$ (Greek 'mu')                     | $\bar{x}$ (Latin 'x-bar')                  |
| **Status**      | **Parameter** (The Absolute Truth)     | **Statistic** (The Estimate)               |
| **Formula**     | $$\mu = \frac{\sum_{i=1}^{N} X_i}{N}$$ | $$\bar{x} = \frac{\sum_{i=1}^{n} x_i}{n}$$ |
| **Count Term**  | $N$ (Total population size)            | $n$ (Subset sample size)                   |
| **Data Source** | Census (Every single member)           | Survey/Experiment (A subset)               |
| **Uncertainty** | **Zero.** It is a fixed constant.      | **Present.** Varies from sample to sample. |
| **Usage**       | Used in theoretical distributions.     | Used in daily Data Science & Modeling.     |
### Variants
| **Mean Variation** | **Formula**                        | **When to Use?**                         | **Mental Model**         |
| ------------------ | ---------------------------------- | ---------------------------------------- | ------------------------ |
| **Standard**       | $\frac{\sum x}{n}$                 | Normal, symmetric data.                  | Everyone gets 1 vote.    |
| **Weighted**       | $\frac{\sum (w \cdot x)}{\sum w}$  | Imbalanced groups or sensor data.        | Some votes count more.   |
| **Trimmed**        | $\frac{\sum x_{inner}}{n_{inner}}$ | Data with heavy outliers (e.g. Finance). | Kick out the extremists. |
#### Trimmed Mean
- **Goal :** To increase the robustness by removing the impact of extreme values in the calculation. Sorting the observations of the feature is required to identify the extreme values
- **Formula :**$$\frac{\sum (w \cdot x)}{\sum w}$$


#### Weighted Mean
- **Goal :** To assign importance (weights) to individual data points
- **Formula :**$$\frac{\sum x_{inner}}{n_{inner}}$$