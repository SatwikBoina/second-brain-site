# 📌 MOC — Optimization Methods for Machine Learning

> Central hub for **Optimization Methods used in Machine Learning**.
> Optimization methods are algorithms that **minimize (or maximize) an objective function**, enabling models to learn parameters from data.

---

## 1. Core Idea

At its heart, machine learning is an optimization problem:

\[
\min_{\theta} \; \mathcal{L}(\theta)
\]

Where:
- \( \theta \) = model parameters
- \( \mathcal{L} \) = loss (objective) function

Learning = **searching parameter space for good solutions**.

---

## 2. Why Optimization Matters in ML

Optimization determines:
- Whether a model learns at all
- How fast it converges
- Whether it generalizes or overfits
- Whether training is stable or chaotic

Many ML failures are actually **optimization failures**, not modeling ones.

---

## 3. Optimization vs Learning

Important distinction:

| Aspect | Optimization | Learning |
|---|---|---|
| Focus | Minimizing loss | Generalizing from data |
| Tool | Algorithms | Models + data |
| Guarantees | Mathematical | Statistical |

Good optimization does **not** guarantee good learning.

---

## 4. Objective Functions in ML

Optimization depends entirely on the objective.

Objectives come from:
- Loss functions
- Regularization terms
- Constraints

\[
\mathcal{L}_{total} = \mathcal{L}_{data} + \lambda \mathcal{L}_{reg}
\]

🔗 Related:
- [[Loss Functions — MOC]]
- [[Regularization — MOC]]

---

## 5. Types of Optimization Problems

---

### 5.1 Convex Optimization

- Single global minimum
- Easier to optimize
- Strong guarantees

Examples:
- Linear regression
- Logistic regression (convex loss)

---

### 5.2 Non-Convex Optimization

- Multiple local minima / saddle points
- Harder to analyze
- Common in deep learning

Examples:
- Neural networks
- Matrix factorization

🔗 Related:
- [[Neural Networks — MOC]]

---

## 6. Gradient-Based Optimization

Most ML uses **gradient-based methods**.

Key idea:
> Move parameters in direction of steepest descent.

\[
\theta \leftarrow \theta - \eta \nabla \mathcal{L}(\theta)
\]

---

### 6.1 Gradient Descent Variants

- Batch Gradient Descent
- Stochastic Gradient Descent (SGD)
- Mini-batch Gradient Descent

🔗 Related:
- [[Gradient Descent]]

---

### 6.2 Momentum-Based Methods

- Momentum
- Nesterov Accelerated Gradient

Purpose:
- Smooth updates
- Escape shallow regions

---

### 6.3 Adaptive Learning Rate Methods

- AdaGrad
- RMSProp
- Adam
- AdamW

Used heavily in deep learning.

---

## 7. Second-Order Optimization

Uses curvature (Hessian).

Examples:
- Newton’s Method
- Quasi-Newton (BFGS, L-BFGS)

Pros:
- Faster convergence near optimum

Cons:
- Expensive in high dimensions

---

## 8. Optimization and Geometry

Optimization depends on:
- Loss landscape shape
- Conditioning
- Curvature

Flat minima often generalize better than sharp minima.

🔗 Related:
- [[Loss Landscape]]
- [[Linear Algebra for Machine Learning — MOC]]

---

## 9. Optimization and Regularization

Regularization changes the optimization landscape:
- Adds constraints
- Smooths solutions
- Prevents overfitting

🔗 Related:
- [[Regularization — MOC]]
- [[Bias–Variance Tradeoff]]

---

## 10. Optimization and Constraints

Some problems include constraints:
- Non-negativity
- Sparsity
- Monotonicity

Handled via:
- Penalty methods
- Projected gradients

---

## 11. Optimization in Different ML Models

---

### Linear Models
- Closed-form or convex optimization
- Stable and predictable

---

### Tree-Based Models
- Greedy optimization
- Not gradient-based

---

### Neural Networks
- High-dimensional, non-convex
- Sensitive to initialization and learning rate

---

### Probabilistic Models
- Likelihood maximization
- Often approximate inference

🔗 Related:
- [[Probabilistic Models — MOC]]

---

## 12. Hyperparameters in Optimization

Optimization introduces its own hyperparameters:
- Learning rate
- Momentum
- Batch size
- Weight decay

Poor choices can completely break training.

🔗 Related:
- [[Hyperparameter Tuning — MOC]]

---

## 13. Optimization and Numerical Stability

Practical issues:
- Exploding gradients
- Vanishing gradients
- Floating-point precision

Stability matters as much as theory.

---

## 14. Common Optimization Failure Modes

- ❌ Learning rate too high / too low  
- ❌ Poor initialization  
- ❌ Ill-conditioned data  
- ❌ Wrong loss scaling  
- ❌ Ignoring gradient diagnostics  

Most fixes are **systematic**, not magical.

---

## 15. How Optimization Fits in ML

Model + Loss  
↓  
Optimization Method ← this  
↓  
Learned Parameters  
↓  
Predictions
Optimization is the **mechanism of learning**.

---

## 16. Relationship to Other Concepts

Optimization methods connect strongly to:

- [[Loss Functions — MOC]]
- [[Hyperparameter Tuning — MOC]]
- [[Linear Algebra for ML — MOC]]
- [[Neural Networks — MOC]]
- [[Model Selection]]

---

## 17. Why Optimization Methods Matter

Optimization explains:

- Why deep learning works (and fails)
- Why training is unstable
- Why some models converge fast
- Why theory and practice differ

It is the **bridge between math and learning**.

---

## Usage Rules

- This MOC is a conceptual + navigational hub
- Each optimizer lives in its own atomic note
- Always connect optimizers to loss geometry
- Ask: *why does this optimizer work here?*
