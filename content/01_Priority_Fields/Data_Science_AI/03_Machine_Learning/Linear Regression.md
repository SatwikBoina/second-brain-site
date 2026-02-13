---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: regression
model-family: linear-models
status: evergreen
tags:
  - "#ML"
  - fundamentals
---

# Linear Regression

> Models the relationship between input features and a continuous target by fitting a linear function that minimizes prediction error.

---

## 1. Intuition

Linear Regression assumes that the target variable can be expressed as a **weighted sum of input features**, plus noise.  
Learning means finding the best weights so predictions are as close as possible to true values.

---

## 2. Analogy

Think of **balancing weights on a scale**:  
each feature adds or subtracts influence, and the goal is to balance them so the scale (prediction) matches reality.

---

## 3. Mathematical Formulation

- Hypothesis function  
- Cost function based on squared error  
- Closed-form solution or iterative optimization  

🔗 See:
- [[Ordinary Least Squares]]
- [[Mean Squared Error]]
- [[Matrix Form of Linear Regression]]

---

## 4. Optimization Perspective

Linear Regression is an **optimization problem**:

- Objective: minimize empirical risk
- Loss: squared loss
- Optimization methods:
  - Normal Equation
  - Gradient Descent

🔗 Links:
- [[Gradient Descent]]
- [[Convex Optimization]]

---

## 5. Assumptions

Linear Regression relies on several assumptions:

- Linearity
- Independence of errors
- Homoscedasticity
- No multicollinearity
- Errors are normally distributed (for inference)

🔗 See:
- [[Gauss–Markov Assumptions]]
- [[Multicollinearity]]

---

## 6. Bias–Variance Tradeoff

- Low bias (simple but expressive enough)
- Can have **high variance** with many correlated features
- Sensitive to noise and outliers

🔗 Links:
- [[Bias–Variance Tradeoff]]
- [[Overfitting vs Underfitting]]

---

## 7. Evaluation Metrics

Common regression metrics:

- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- R² and Adjusted R²

🔗 See:
- [[Regression Metrics — MOC]]

---

## 8. Feature Requirements & Preprocessing

Linear Regression is sensitive to:

- Feature scaling (for gradient descent)
- Outliers
- Correlated features

🔗 Links:
- [[Feature Scaling]]
- [[Outliers]]
- [[Feature Engineering for Linear Models]]

---

## 9. Hyperparameters

Linear Regression itself has **no true hyperparameters**, but practical variants introduce:

- Learning rate (for gradient descent)
- Number of iterations
- Regularization strength (in extensions)

🔗 See:
- [[Ridge Regression]]
- [[Lasso Regression]]
- [[Elastic Net]]

---

## 10. Interpretability

- Coefficients represent marginal effect of features
- Easy to explain to non-technical stakeholders
- Used as a benchmark model

🔗 Links:
- [[Model Interpretability]]
- [[Coefficient Interpretation in Linear Models]]

---

## 11. When Linear Regression Works Well

- Linear relationship
- Low noise
- Small to medium feature space
- Need for interpretability

---

## 12. When It Fails

- Strong non-linear patterns
- High multicollinearity
- Many irrelevant features
- Presence of outliers

---

## 13. Extensions & Related Models

- [[Polynomial Regression]]
- [[Ridge Regression]]
- [[Lasso Regression]]
- [[Elastic Net]]
- [[Generalized Linear Models]]

---

## 14. Position in the ML Landscape

- Baseline supervised regression model
- Foundation for regularized models
- Reference point for bias–variance discussions
