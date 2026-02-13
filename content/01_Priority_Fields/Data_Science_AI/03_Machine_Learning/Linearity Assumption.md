---
type: concept
domain: machine-learning
category: modeling-assumptions
status: evergreen
---

# Linearity Assumption

> The linearity assumption states that the relationship between input features and the target is linear in the model parameters.

---

## 1. One-Line Intuition

> The model assumes the target can be expressed as a weighted sum of input features.

---

## 2. Mathematical Form

Linear model:

\[
y = w_0 + w_1 x_1 + w_2 x_2 + ... + w_p x_p
\]

Or vector form:

\[
y = w^T x
\]

This means:

- Output is linear in weights.
- Decision boundary is linear in feature space.

---

## 3. Important Clarification

Linearity assumption means:

> Linear in parameters — not necessarily linear in features.

Example:

Polynomial regression:

\[
y = w_0 + w_1 x + w_2 x^2
\]

Still linear in parameters \(w\).

Thus:

- Linear models can model nonlinear patterns via feature transformation.

🔗 Related:
- [[Linear Regression]]
- [[Polynomial Regression]]

---

## 4. Where Linearity Assumption Appears

---

### 4.1 Linear Regression

Assumes:

\[
E[y|x] = w^T x
\]

---

### 4.2 Logistic Regression

Assumes:

\[
\log \frac{p}{1-p} = w^T x
\]

Linearity applies to log-odds.

---

### 4.3 Linear SVM

Assumes linear decision boundary:

\[
w^T x + b = 0
\]

---

## 5. Geometric Interpretation

Linearity implies:

- Decision boundary is a hyperplane.
- In 2D → line.
- In 3D → plane.
- In higher dimensions → hyperplane.

---

## 6. What Happens If Linearity Is Violated?

If true relationship is nonlinear:

- Model underfits.
- High bias.
- Systematic residual patterns.

Signs of violation:

- Curved residual plots.
- Structured errors.
- Poor performance.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 7. Ways to Relax Linearity

---

### 7.1 Feature Engineering

Add:

- Polynomial terms
- Interaction terms
- Log transforms

---

### 7.2 Kernel Methods

Map to higher-dimensional space:

\[
K(x_i, x_j)
\]

Used in:

- [[Support Vector Machine]]
- [[Kernel Methods — MOC]]

---

### 7.3 Tree-Based Models

Decision Trees:

- No linearity assumption.
- Nonparametric.

🔗 Related:
- [[Decision Tree Classifier]]

---

### 7.4 Neural Networks

Hidden layers introduce nonlinear transformations.

---

## 8. Statistical Interpretation

In regression:

Linearity assumption refers to:

\[
E[y|x] = w^T x
\]

Not necessarily:

- Errors being linear.
- Features being independent.

---

## 9. Linearity vs Independence Assumption

Common confusion:

Linearity ≠ independence.

Features can be correlated.
Model can still be linear.

---

## 10. Linearity and Interpretability

Linear models:

- Easy to interpret.
- Coefficients represent marginal effect.

Tree/NN models:
- Harder to interpret.

🔗 Related:
- [[Model Interpretability]]

---

## 11. Linearity and Optimization

Linear models:

- Convex loss functions.
- Globally optimal solutions.
- Stable optimization.

Nonlinear models:
- Non-convex.
- Local minima.

---

## 12. Bias–Variance Perspective

Linear models:

- High bias
- Low variance
- Stable

Nonlinear models:

- Lower bias
- Higher variance
- Risk overfitting

🔗 Related:
- [[Model Complexity]]

---

## 13. When Linearity Assumption Works Well

- Small datasets
- High-dimensional sparse data
- Well-behaved relationships
- Text classification

---

## 14. When It Fails

- Complex nonlinear relationships
- Interactions between features
- Threshold effects
- Saturation behavior

---

## 15. Relationship to Other Concepts

Linearity Assumption connects strongly to:

- [[Linear Regression]]
- [[Logistic Regression]]
- [[Support Vector Machine]]
- [[Kernel Methods — MOC]]
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]
- [[Interaction Terms]]

---

## 16. Why Linearity Assumption Matters

Understanding linearity teaches:

- What your model is capable of representing.
- Why some models underfit.
- Why feature engineering matters.
- Why kernels and neural networks exist.

It is the foundation of:
> Parametric modeling in ML.
