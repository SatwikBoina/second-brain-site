
- **Date of Entry:** 30-12-2025
- **Tags:** #statistics #descriptive_stats 


### 1️⃣ Definition
- It is the most frequent value of a feature.
- Sometimes, There can be a tie resulting multiple modes. 
- It is best used for Categorical Variables or Features.

---

###  2️⃣ Analogy / Intuition
- It's a Popularity Contest
- A mode is crowd favourite.
### Visual Aid :
![[Mode_visual_aid.png]]

**Examples:**
- FMCG SECTOR :To identify the most popular SKUs among the masses by the FMCG companies. They can further analyse the reasons for it's popularity and improve the other products in their portfolio.

---

### 3️⃣ Formula
|**Case**|**Logical "Formula"**|**Explanation**|
|---|---|---|
|**Unimodal**|$\text{Mode} = \arg\max_{x} (\text{freq}(x))$|The single value that appears with the highest frequency.|
|**Bimodal**|$\text{Modes} = \{x_1, x_2\}$|Two distinct values share the same maximum frequency.|
|**Multimodal**|$\text{Modes} = \{x_1, x_2, \dots, x_k\}$|Three or more values share the same maximum frequency.|
|**No Mode**|$\text{freq}(x_1) = \text{freq}(x_2) = \dots$|Every value appears exactly once (common in continuous data).|
