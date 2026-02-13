- **Date of Entry:** 2025-12-29
- **Tags:** #statistics 

### Visual Aid :
![[00_stats_types_of_data.png]]

Understanding the *Data Type* of a feature is an important first step in Statistics.
- Helps in the visual display
- Meaningful Data Analysis
- Associated [[Statistical Modelling]]

Since the Statistical Analysis happens on the computer software, it also helps in
- Storage Optimization inside RAM
- Proper plots based on Data Types

| **Primary Type**              | **Sub-Type**          | **Description**                                       | **Examples**                                              | **Software Interpretation**                                   |
| ----------------------------- | --------------------- | ----------------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------- |
| **Numeric** (Quantitative)    | **Continuous**        | Any value within a range; infinite decimals possible. | Wind speed, time, price, weight.                          | Stored as `float`. Operations: Mean, Variance, Regression.    |
|                               | **Discrete**          | Only whole numbers; representing counts.              | Number of children, goal count, website visits.           | Stored as `int`. Operations: Counting, Poisson modeling.      |
| **Categorical** (Qualitative) | **Binary**            | Only two possible mutually exclusive states.          | Yes/No, 0/1, Spam/Not Spam, Pass/Fail.                    | Stored as `bool` or `int`. Operations: Logistic Regression.   |
|                               | **Ordinal**           | Categories with a clear, logical rank or order.       | Rating (1-5), Size (S, M, L), Seniority (Junior, Senior). | Stored as `ordered factor`. Operations: Rank correlation.     |
|                               | **Nominal** (General) | Fixed set of values with no inherent ranking.         | State name, Color, Product Category.                      | Stored as `string` or `factor`. Operations: One-Hot Encoding. |