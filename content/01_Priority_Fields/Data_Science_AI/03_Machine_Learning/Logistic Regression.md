---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: classification
model-family: linear-models
status: evergreen
---

# Logistic Regression

> A linear classification algorithm that models the probability of class membership using a logistic (sigmoid) function and maximum likelihood estimation.

---

## 1. Core Idea

Logistic Regression predicts the **probability** of a class rather than a continuous value by:

- Modeling a linear combination of features
- Passing it through a sigmoid function
- Applying a decision threshold

🔗 Model family:
- [[Linear Models — MOC]]

---

## 2. Intuition

Instead of fitting a line to targets, Logistic Regression:
- Fits a line to **log-odds**
- Converts scores into probabilities
- Classifies based on probability thresholds

---

## 3. Analogy

Think of a **dimmer switch**:
- Output is not ON/OFF directly
- It smoothly transitions from 0 to 1
- A cutoff decides the final state

---

## 4. Mathematical Perspective

- Linear predictor: \( w^T x \)
- Sigmoid function maps to (0, 1)
- Parameters estimated via maximum likelihood

🔗 Concepts:
- [[Sigmoid Function]]
- [[Log-Odds]]
- [[Maximum Likelihood Estimation]]

---

## 5. Loss Function

Logistic Regression uses **log loss (cross-entropy)**:

- Penalizes confident wrong predictions heavily
- Smooth and convex loss

🔗 See:
- [[Log Loss]]
- [[Cross Entropy]]
- [[Loss Functions — MOC]]

---

## 6. Optimization Perspective

- Convex optimization problem
- Solved via gradient-based methods
- No closed-form solution

🔗 Links:
- [[Gradient Descent]]
- [[Convex Optimization]]

---

## 7. Decision Boundary

- Linear decision boundary in feature space
- Non-linear boundaries via feature engineering or kernels

🔗 Related:
- [[Decision Boundary]]
- [[Polynomial Features]]
- [[Kernel Methods — MOC]]

---

## 8. Bias–Variance Tradeoff

- High bias with simple features
- Low variance compared to complex classifiers
- Regularization controls overfitting

🔗 See:
- [[Bias–Variance Tradeoff]]

---

## 9. Assumptions

Logistic Regression assumes:

- Linear relationship between features and log-odds
- Independent observations
- Little multicollinearity

🔗 Contrast:
- [[Tree-Based Models — MOC]]

---

## 10. Regularization

Logistic Regression supports:

- L2 regularization (Ridge-style)
- L1 regularization (feature selection)
- Elastic Net regularization

🔗 Links:
- [[Regularization — MOC]]
- [[Ridge Regression]]
- [[Lasso Regression]]

---

## 11. Hyperparameters

Key hyperparameters include:

- Regularization strength (C)
- Penalty type (L1, L2, Elastic Net)
- Solver choice

🔗 See:
- [[Hyperparameter Tuning — MOC]]

---

## 12. Feature Scaling Requirement

Logistic Regression benefits from:

- Feature standardization
- Especially when using regularization

🔗 Links:
- [[Feature Scaling]]
- [[Standardization]]

---

## 13. Evaluation Metrics

Common classification metrics:

- Accuracy
- Precision / Recall
- F1-score
- ROC–AUC
- Log loss

🔗 See:
- [[Classification Metrics — MOC]]

---

## 14. Interpretability

- Coefficients indicate log-odds change
- Easy to explain and debug
- Strong baseline classifier

🔗 Links:
- [[Model Interpretability]]
- [[Coefficient Interpretation in Linear Models]]

---

## 15. When Logistic Regression Works Well

- Linearly separable classes
- Small to medium datasets
- Need for interpretability
- Probabilistic outputs required

---

## 16. When It Fails

- Strong non-linear class boundaries
- Complex feature interactions
- Severe class imbalance (without adjustments)

🔗 Concepts:
- [[Class Imbalance]]
- [[Threshold Tuning]]

---

## 17. Relationship to Other Models

- Classification counterpart of Linear Regression
- Competes with SVM (linear kernel)
- Baseline for many classifiers

🔗 Related:
- [[Support Vector Machine]]
- [[Naive Bayes]]

---

## 18. Position in the ML Landscape

- Foundational linear classifier
- Strong statistical grounding
- First-choice baseline for classification
