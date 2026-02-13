# 📌 MOC — Loss Functions

> Central hub for **Loss Functions in Machine Learning**.
> A loss function defines **what it means to be wrong** and guides how a model learns by translating errors into a numerical signal optimized during training.

---

## 1. Core Idea

A loss function answers one question:

> *How bad is a prediction?*

It converts:
- True outcome \(y\)
- Predicted outcome \(\hat{y}\)

into a **scalar penalty** that optimization algorithms try to minimize.

Loss functions define:
- Learning behavior
- Model priorities
- Sensitivity to errors
- Robustness and fairness

---

## 2. Loss Functions vs Evaluation Metrics

Important distinction:

| Aspect | Loss Function | Evaluation Metric |
|----|----|----|
| Used during training | ✅ | ❌ |
| Differentiable (usually) | ✅ | ❌ |
| Optimized directly | ✅ | ❌ |
| Business-facing | ❌ | ✅ |

Loss ≠ Metric (by design).

🔗 Related:
- [[Evaluation Metrics — MOC]]

---

## 3. Why Loss Functions Matter So Much

Loss functions determine:
- Which errors matter more
- How outliers are treated
- Whether probabilities are meaningful
- How bias–variance tradeoff is navigated
- Whether the model aligns with business goals

> Changing the loss often changes the *entire behavior* of the model.

---

## 4. Major Families of Loss Functions

---

## 4.1 Regression Loss Functions

Used when targets are **continuous**.

Examples:
- Mean Squared Error
- Mean Absolute Error
- Huber Loss
- RMSLE
- Quantile Loss

🔗 Hub:
- [[Regression Loss Functions — MOC]]

---

## 4.2 Classification Loss Functions

Used when targets are **categorical**.

Examples:
- Log Loss / Cross Entropy
- Hinge Loss
- Focal Loss
- Weighted Losses

🔗 Hub:
- [[Classification Loss Functions — MOC]]

---

## 4.3 Margin-Based Losses

Focus on **decision boundaries**, not probabilities.

Examples:
- Hinge Loss
- Squared Hinge Loss

Used heavily in SVMs.

🔗 Related:
- [[Margin-Based Losses]]

---

## 4.4 Probabilistic (Likelihood-Based) Losses

Derived from **negative log-likelihood**.

Examples:
- MSE ↔ Gaussian likelihood
- Log loss ↔ Bernoulli / Categorical likelihood

🔗 Related:
- [[Probabilistic Models — MOC]]

---

## 4.5 Robust Loss Functions

Designed to handle:
- Outliers
- Noisy labels

Examples:
- MAE
- Huber Loss
- Log-Cosh Loss

🔗 Related:
- [[Outliers]]

---

## 4.6 Asymmetric / Cost-Sensitive Losses

Penalize different mistakes differently.

Examples:
- Weighted Cross Entropy
- Quantile Loss
- Custom asymmetric losses

🔗 Related:
- [[Cost-Sensitive Learning]]
- [[Custom Loss Functions]]

---

## 4.7 Custom Loss Functions

User-defined objectives to reflect:
- Business cost
- Risk
- Constraints

🔗 Related:
- [[Custom Loss Functions]]

---

## 5. Loss Functions and Bias–Variance

Loss choice affects bias–variance behavior:

- L2-type losses → lower bias, higher variance
- L1-type losses → higher bias, lower variance
- Hybrid losses → controlled tradeoff

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 6. Loss Functions and Outliers

Outlier sensitivity depends heavily on loss shape:

| Loss | Outlier Sensitivity |
|----|---------------------|
| MSE | Very High |
| MAE | Low |
| Huber | Medium |
| Log-based | Low |

🔗 Related:
- [[Outliers]]

---

## 7. Loss Functions and Optimization

Loss functions must be:
- Differentiable (or sub-differentiable)
- Smooth enough for gradient descent
- Numerically stable

Poorly designed losses:
- Break training
- Cause exploding gradients
- Lead to unstable convergence

🔗 Related:
- [[Gradient Descent]]
- [[Optimization Algorithms]]

---

## 8. Loss Functions and Probability

Some losses produce **calibrated probabilities**, others do not.

- Log loss → good calibration
- Hinge loss → poor calibration

Probability quality matters for:
- Threshold tuning
- Cost-sensitive decisions
- Fairness evaluation

🔗 Related:
- [[Probability Calibration]]
- [[Threshold Tuning]]

---

## 9. Loss Functions and Class Imbalance

Standard losses assume balanced data.

Imbalanced data requires:
- Reweighting
- Specialized losses
- Threshold tuning

🔗 Related:
- [[Class Imbalance]]

---

## 10. Loss Functions and Model Choice

Different models naturally pair with different losses:

| Model | Typical Loss |
|----|-------------|
| Linear Regression | MSE |
| Logistic Regression | Log Loss |
| SVM | Hinge Loss |
| Gradient Boosting | Custom |
| Neural Networks | Cross Entropy / Custom |

Loss choice is **part of model design**.

---

## 11. Loss Functions and Interpretability

Loss functions influence:
- Coefficient meaning
- Feature importance
- Explanation stability

Robust losses often improve interpretability.

🔗 Related:
- [[Model Interpretability]]

---

## 12. Common Mistakes

- ❌ Treating accuracy as a loss  
- ❌ Using MSE with heavy outliers  
- ❌ Ignoring business costs  
- ❌ Optimizing loss without checking metrics  
- ❌ Blindly using defaults  

Loss functions encode **values**, not just math.

---

## 13. How Loss Functions Fit in ML

Data  
↓  
Features  
↓  
Model  
↓  
Loss Function ← defines learning  
↓  
Optimization  
↓  
Predictions


Everything downstream is shaped by the loss.

---

## Usage Rules

- This MOC is a conceptual + navigation hub
- Individual losses live in atomic notes
- Always link models to the loss they optimize
- Ask: *what behavior does this loss encourage?*
