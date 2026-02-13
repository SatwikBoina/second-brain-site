- **Date of Entry:** 2025-12-30
- **Tags:** #statistics 

### Visual Aid :

![[statistical Modelling.png]]


It's about fitting the data in real world as a form of *mathematical equation* under assumptions.
$$
y = f(x)+ Error
$$
- $f(x)$ represents the pattern or rule of the data.
- $y$ is the dependent variable.

The chosen equation $f(x)$ is based on what $y$ looks like.

| **Model Type**             | **Outcome $y$ Nature** | **The "Shape" of $f(x)$** | **Real-World Example**                                    | Why Linear Regression Fails Here                                                                           |
| -------------------------- | ---------------------- | ------------------------- | --------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Linear Regression**      | Continuous & Unbounded | **Straight Line**         | Predicting **Temperature** based on humidity.             | It works fine here; no "bending" needed.                                                                   |
| **Logistic Regression**    | Binary (0 or 1)        | **S-Curve (Sigmoid)**     | Predicting if a customer will **Churn (Yes/No)**.         | Linear would predict values like 1.5 or -0.2, which are impossible for a "Yes/No" outcome.                 |
| **Poisson Regression**     | Counts (0, 1, 2...)    | **Exponential Curve**     | Predicting the **Number of clicks** on an ad.             | Linear can predict negative clicks, and it assumes the variance is constant (which isn't true for counts). |
| **Multinomial Regression** | Categories (A, B, C)   | **Multiple S-Curves**     | Predicting which **Marketing Segment** a user belongs to. | You can't put "Gold," "Silver," and "Bronze" on a single straight line.                                    |
| **Cox Regression**         | Time-to-Event          | **Hazard Ratio**          | Predicting **Days until a machine fails**.                | It accounts for "Censoring"—the fact that some machines haven't failed _yet_ when you stop the study.      |

### Why is it preferred over ML? 
- **Interpretability :** Understand why things happen in a certain way by "how much" factor
	- Why a particular candidate is denied a loan?
	- Why is price important?