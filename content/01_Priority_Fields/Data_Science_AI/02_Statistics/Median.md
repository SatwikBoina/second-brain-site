
- **Date of Entry:** 30-12-2025
- **Tags:** #statistics #descriptive_stats 


### 1️⃣ Definition

- A value that is present in the centre of the sorted data.
	- If the $n$ is odd, It is a single value which is at the centre of the sorted data.
	- If the $n$ is even, It is the Mean of two values situated at the centre.
- It splits the whole observation set into two parts
- Naturally, It is robust to the extreme values of a feature.
---

###  2️⃣ Analogy / Intuition
- It is the robust representation of mass market.
### Visual Aid :
![[median_visual_aid.png]]
**Examples:**
- FMCG Product Demand : It is often deviated by rare bulk orders, causing the shift of mean. But, the Median never fools us with what a typical user buys.

---

### 3️⃣ Formula
| **Case** | **Condition**         | **Formula**                                                                               | **Interpretation**                                            |
| -------- | --------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| **Odd**  | $n$ is an odd number  | $$\tilde{x} = x_{\left(\frac{n+1}{2}\right)}$$                                            | The value at the exact middle position of the sorted list.    |
| **Even** | $n$ is an even number | $$\tilde{x} = \frac{x_{\left(\frac{n}{2}\right)} + x_{\left(\frac{n}{2} + 1\right)}}{2}$$ | The average of the two middle-most values in the sorted list. |
