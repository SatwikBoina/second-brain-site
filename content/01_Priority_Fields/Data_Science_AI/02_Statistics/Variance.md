
- **Date of Entry:** 30-12-2025
- **Tags:** #statistics #descriptive_stats 


### 1️⃣ Definition

- This quantifies the total deviation present in the feature's sample from the [[Mean]].
- It takes all the data points into consideration unlike the IQR and Range.

![[VARIANCE_ELASTIC_BAND.png]]

---

###  2️⃣ Analogy / Intuition

**Political Policies :**
- Policies satisfying the needs of majority of the vote bank brings victory closer to the policy makers.
### Visual Aid : 
 

![[POLITICAL_POLICY_VARIANCE.png]]



Examples:
- Salaries in a company
- Marks in an exam
- Heights of people

---

### 3️⃣ Formula

| **Metric**              | **Symbol** | **Formula**                                    | **When to Use**                                                                                             |
| ----------------------- | ---------- | ---------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| **Population Variance** | $\sigma^2$ | $$\sigma^2 = \frac{\sum (x_i - \mu)^2}{N}$$    | You have data for **every single member** of the group (e.g., all students in a specific class).            |
| **Sample Variance**     | $s^2$      | $$s^2 = \frac{\sum (x_i - \bar{x})^2}{n - 1}$$ | You are using a **subset** to estimate the spread of a larger population (the standard in ML/Data Science). |
**Notes :**
- Outliers are heavily penalized due to squaring.
- Difficulty in Interpretation : Hence, We derive *standard deviation* from variance.
- **Bessel's Correction ** : 
	- **Idea** :  A sample doesn't cover the variation of a population. It sure misses out a lot of diversity which is evident in the Population.
	- Hence, it underestimates the sample variance when divided by $n$.
	- To make the sample a better representation of the population variance, the denominator $n-1$ is introduced.
	- Dive into [[Degrees of Freedom]]
	