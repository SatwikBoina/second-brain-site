
- **Date of Entry:** 30-12-2025
- **Tags:** #statistics #descriptive_stats 


### 1️⃣ Definition
- It is the range covered by the middle 50% of the feature's data sorted.
- It is robust to the impact of extremes and focusses only on the central data.
- It gives us the idea of spread around the [[Median]].
---

###  2️⃣ Analogy / Intuition

**Drama :**
When you attend a theatre or a drama, You observe what's happening under the spotlight rather than the whole stage.

![[Drama_iqr.png]]

**Examples:**
- Salaries in a company : The CEOs and other higher officials take up the huge chunk of the revenue(s) and the blue-collar job(s) don't make much. To see the real picture, we need to look at how the people within 50% central spread are making.

---

### 3️⃣ Formula

|**Quartile**|**Percentile**|**What it Represents**|**Analogy**|
|---|---|---|---|
|**$Q_1$**|25th|The "Lower Gate": 25% of data is below this value.|The start of the spotlight.|
|**$Q_2$**|50th|The **Median**: Splits the data exactly in half.|The center of the stage.|
|**$Q_3$**|75th|The "Upper Gate": 75% of data is below this value.|The end of the spotlight.|
|**$Q_4$**|100th|The **Maximum**: The highest value in the dataset.|The very edge of the stage.|
$$IQR = Q_3 - Q_1$$

**Notes :**
- A single value representing the width of the middle 50% of the data. If the width is less, the data are similar with less deviation.
- **Outlier Classification :** 
		$$Lower\ Fence = Q_1 - (1.5 \times IQR)$$
		$$Upper\ Fence = Q_3 + (1.5 \times IQR)$$
![[IQR_OUTLIER_DETECTION.png]]
