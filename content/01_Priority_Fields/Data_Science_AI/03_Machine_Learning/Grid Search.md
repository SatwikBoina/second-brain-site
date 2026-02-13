---
type: concept
domain: machine-learning
category: hyperparameter-tuning
status: evergreen
---

# Grid Search

> Grid Search is a hyperparameter optimization technique that exhaustively evaluates **all combinations** of specified hyperparameter values using a chosen evaluation strategy.

---

## 1. Core Idea

Grid Search answers one question:

> *Which hyperparameter combination performs best according to a validation metric?*

It does this by:
- Defining a discrete search space
- Training models for every combination
- Selecting the best-performing configuration

---

## 2. What Grid Search Optimizes

Grid Search does **not** learn model parameters.  
It optimizes **hyperparameters**, such as:

- Regularization strength
- Tree depth
- Number of estimators
- Learning rate
- Kernel parameters

🔗 Related:
- [[Hyperparameter Tuning — MOC]]

---

## 3. How Grid Search Works (Methodology)

1. Define a parameter grid  
2. Select an evaluation strategy (usually CV)  
3. Train model for each combination  
4. Evaluate performance  
5. Select best configuration  

Grid Search is **brute-force but reliable**.

---

## 4. Grid Search + Cross Validation

Most Grid Search implementations use:

- k-fold cross validation
- Stratified k-fold for classification

This reduces evaluation noise.

🔗 Related:
- [[Cross Validation]]
- [[Stratified Sampling]]

---

## 5. Bias–Variance Perspective

Grid Search helps:
- Tune regularization
- Control model complexity
- Balance bias and variance

But it **does not prevent overfitting** by itself.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 6. Computational Cost

Grid Search cost grows as:

\[
O(\text{#params}^{\text{dimensions}} \times \text{CV folds})
\]

This makes it:
- Accurate
- Potentially very expensive

---

## 7. When Grid Search Works Well

- Small to medium datasets
- Few hyperparameters
- Low-cost models
- Final fine-tuning

Examples:
- Logistic Regression
- SVM
- Linear models

---

## 8. When Grid Search Works Poorly

- Large datasets
- Many hyperparameters
- Boosting models with large grids
- Deep learning models

Grid Search does **not scale well**.

---

## 9. Grid Search vs Random Search

| Aspect | Grid Search | Random Search |
|-----|------------|---------------|
| Coverage | Exhaustive | Stochastic |
| Efficiency | Low | High |
| Guarantees | Yes (within grid) | No |
| Scaling | Poor | Better |

🔗 Related:
- [[Random Search]]

---

## 10. Grid Resolution Matters

- Coarse grid → may miss optimum
- Fine grid → expensive
- Best practice:
  - Coarse search → narrow range
  - Fine search → local tuning

---

## 11. Grid Search and Data Leakage ⚠️

❌ Wrong:
- Grid search using test set

✅ Correct:
1. Train–validation (via CV)
2. Select best hyperparameters
3. Evaluate once on test set

🔗 Core concept:
- [[Data Leakage]]
- [[Train–Test Split]]

---

## 12. Grid Search and Pipelines

Using pipelines ensures:
- Preprocessing is included in tuning
- No leakage during CV
- Reproducible workflows

🔗 Related:
- [[Pipelines]]

---

## 13. Common Mistakes

- ❌ Searching too many parameters at once  
- ❌ Using overly fine grids early  
- ❌ Ignoring computational cost  
- ❌ Tuning on test set  

Grid Search is powerful but **not forgiving**.

---

## 14. Why Grid Search Matters

Grid Search explains:
- How regularization is tuned
- Why model performance varies wildly
- Why defaults are rarely optimal
- Why tuning strategy matters as much as the model

It is a **baseline hyperparameter optimizer**.

---

## Usage Notes

- Use Grid Search for:
  - Final tuning
  - Low-dimensional search spaces
- Prefer Random Search for:
  - Large or noisy spaces
- Link this note from:
  - Hyperparameter Tuning — MOC
  - Model Selection
