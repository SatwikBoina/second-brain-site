 
- **Date of Entry:** 30-12-2025
- **Tags:** #statistics #descriptive_stats 


### 1️⃣ Definition
- It should be interpreted as the typical error seen when identifying a typical value (mean) of a feature.
- It is the square root of the [[Variance]]
- To improve the interpretability, The square root is introduced to bring it down to the same units of the feature.
- It should not be misinterpreted as an average deviation from the mean.
- Works well with Normal Distribution.
---

###  2️⃣ Analogy / Intuition

### Visual Aid : 

![[Pasted image 20251230174732.png]]

**Examples:**
- In the manufacturing sector, A product made with high standard deviation is not good as it produces defective products which is not enough to make profits or sales.
- In the mutual funds investments, We want stocks which return more than the index

---

### 3️⃣ Formula
| **Metric**        | **Symbol** | **Formula (LaTeX)**                                 | **Core Interpretation**                                                   |
| ----------------- | ---------- | --------------------------------------------------- | ------------------------------------------------------------------------- |
| **Population SD** | $\sigma$   | $$\sigma = \sqrt{\frac{\sum (x_i - \mu)^2}{N}}$$    | The "True Spread" of every single member in the group.                    |
| **Sample SD**     | $s$        | $$s = \sqrt{\frac{\sum (x_i - \bar{x})^2}{n - 1}}$$ | An **estimate** of the spread, "boosted" to account for missing outliers. |
**Notes**:
- A low SD doesn't necessary mean it is bad. It depends on the case we are handling.
- **Prediction :** If we want to predict, We must aim for low SD as it increases our chance of being closer to the results we anticipate.
- **Algorithm Trading :**
	- People look for higher returns here. They want to handle risks and improve their returns. In these cases, High SD is expected.
- **Feature Selection in Machine Learning :**
	- Features with hight SD contribute to prediction better than the features with low SD
- **A/B Testing :**
	- How people react to the change in your sample? if it is diverse, It gives us the better understanding about the decision we are about to make.