---
type: zettel
domain: machine-learning
category: linear-models
topic: log-log-regression
status: evergreen
---

# Log-Log Regression Model

> A log-log regression models both the dependent and independent variables in logarithmic form, allowing coefficients to be interpreted as elasticities.

---

## 1. Model Form

$$
\log(y) = \beta_0 + \beta_1 \log(x_1) + \beta_2 \log(x_2) + ... + \epsilon
$$

Both:
- Dependent variable (y)
- Independent variables (x)

are log-transformed.

---

## 2. One-Line Intuition

> A 1% change in x leads to a β% change in y.

---

## 3. Interpretation of Coefficients

If:

$$
\log(y) = \beta \log(x)
$$

Then:

$$
\beta
$$

is the elasticity.

Meaning:

- 1% increase in x
- leads to β% change in y

This makes interpretation scale-free.

---

## 4. Why Log-Log Is Powerful

It naturally models:

- Multiplicative relationships
- Percentage growth
- Diminishing returns
- Power-law relationships

Instead of:

$$
y = ax
$$

It models:

$$
y = ax^\beta
$$

---

## 5. Deriving the Elasticity Interpretation

Start with:

$$
\log(y) = \beta \log(x)
$$

Rewrite:

$$
y = e^{\beta \log(x)} = x^\beta
$$

Take derivative:

$$
\frac{dy}{dx} = \beta x^{\beta - 1}
$$

Elasticity:

$$
\frac{dy}{dx} \cdot \frac{x}{y} = \beta
$$

Thus coefficient equals elasticity.

---

## 6. When to Use Log-Log Models

- Marketing mix modeling
- Price elasticity estimation
- Demand modeling
- Growth modeling
- Economic data
- Revenue vs advertising spend

Especially useful when:

- Relationships are multiplicative.
- Variables grow proportionally.

---

## 7. Assumptions

Standard linear regression assumptions apply to:

$\log(y)$

So assumptions are:

- Linearity (in log-space)
- Independence of errors
- Homoscedasticity in log-space
- No perfect multicollinearity

🔗 Related:
- [[Linearity Assumption]]
- [[Homoscedasticity]]

---

## 8. Practical Considerations

### 8.1 Variables Must Be Positive

Since:

$\log(x)$

is undefined for:

- Zero
- Negative values

Common workaround:
- Add small constant (carefully).

---

### 8.2 Interpretation in Original Scale

Predictions:

$\hat{y} = e^{\hat{\log(y)}}$

Note:
- Back-transforming introduces bias.
- Sometimes need correction factor.

---

## 9. Comparison to Other Transformations

| Model Type | Equation | Interpretation |
|------------|----------|----------------|
| Linear | y = βx | Absolute change |
| Log-linear | log(y) = βx | % change in y |
| Linear-log | y = βlog(x) | Unit change in y |
| Log-log | log(y) = βlog(x) | % change in y for % change in x |

Log-log gives elasticity directly.

---

## 10. Bias–Variance Perspective

Log transformation often:

- Stabilizes variance.
- Reduces heteroscedasticity.
- Makes relationships more linear.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Homoscedasticity]]

---

## 11. Relationship to Other Concepts

Log-Log Regression connects strongly to:

- [[Linear Regression]]
- [[Coefficient Interpretation in Linear Models]]
- [[Linearity Assumption]]
- [[Maximum Likelihood Estimation]]
- [[Elastic Net]]
- [[Homoscedasticity]]

---

## 12. Why Log-Log Regression Matters

It teaches:

- How transformations change interpretation.
- How multiplicative systems become linear.
- How elasticity is estimated directly.
- Why scaling matters in modeling.

It is central to:
> Economic modeling and marketing analytics.
