---
type: concept
domain: machine-learning
category: hyperparameter-tuning
status: evergreen
---

# Hyperparameter Sensitivity

> Hyperparameter sensitivity describes how **strongly model performance changes** in response to small variations in hyperparameter values.

---

## 1. Core Idea

A model is **hyperparameter-sensitive** if:
- Small changes in hyperparameters
- Cause large swings in performance

Low sensitivity → stable, robust models  
High sensitivity → fragile, tuning-heavy models

---

## 2. Why Hyperparameter Sensitivity Matters

High sensitivity leads to:
- Unstable validation scores
- Poor reproducibility
- Overfitting to validation sets
- Models that fail in production

Sensitivity determines **how much tuning effort is needed**.

---

## 3. Sensitivity vs Importance

Important distinction:

- **Important hyperparameter** → affects performance
- **Sensitive hyperparameter** → small changes cause large effects

A parameter can be important but not sensitive.

---

## 4. Sources of Hyperparameter Sensitivity

Sensitivity increases due to:

- High model complexity
- Strong non-linearity
- Small datasets
- Noisy objective functions
- Poor feature scaling
- Weak regularization

🔗 Related:
- [[Model Complexity]]
- [[Bias–Variance Tradeoff]]

---

## 5. Algorithm-Wise Sensitivity (Intuition)

| Algorithm | Sensitivity Level |
|--------|-------------------|
| Linear Regression | Low |
| Ridge / Lasso | Medium |
| Logistic Regression | Medium |
| Decision Tree | High |
| Random Forest | Low |
| Gradient Boosting | High |
| XGBoost | Very High |
| LightGBM | Very High |
| CatBoost | Medium |
| k-NN | High |
| SVM (RBF) | High |
| Naive Bayes | Very Low |

---

## 6. Sensitivity and Bias–Variance

- High sensitivity ↔ high variance
- Low sensitivity ↔ higher bias, more stability

Tuning often trades:
> performance peak vs robustness

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 7. Hyperparameters Commonly Sensitive

Highly sensitive parameters include:

- Learning rate
- Regularization strength
- Tree depth
- Number of leaves
- Kernel parameters
- Neighborhood size (k)

Poor choices here dominate performance.

---

## 8. Detecting Hyperparameter Sensitivity

Signs of high sensitivity:

- Large CV variance
- Sharp performance peaks
- Different best parameters across folds
- Unstable leaderboard scores

Tools:
- Validation curves
- Random Search
- Bayesian Optimization diagnostics

🔗 Related:
- [[Learning Curves]]
- [[Cross Validation]]

---

## 9. Hyperparameter Sensitivity and Search Strategy

| Sensitivity | Recommended Strategy |
|-----------|---------------------|
| Low | Grid Search |
| Medium | Random Search |
| High | Bayesian Optimization |
| Very High | Bayesian + Early Stopping |

🔗 Related:
- [[Grid Search]]
- [[Random Search]]
- [[Bayesian Optimization]]

---

## 10. Sensitivity and Feature Engineering

Good features:
- Reduce sensitivity
- Smooth objective landscape
- Increase robustness

Poor features amplify sensitivity.

🔗 Related:
- [[Feature Engineering]]
- [[Feature Scaling]]

---

## 11. Sensitivity and Regularization

Regularization:
- Reduces sensitivity
- Smooths performance surface
- Improves generalization

🔗 Related:
- [[Regularization — MOC]]
- [[Early Stopping]]

---

## 12. Production Perspective

In production, prefer:
- Slightly worse but stable models
- Wide performance plateaus
- Low tuning dependency

Highly sensitive models are **operationally risky**.

---

## 13. Common Mistakes

- ❌ Chasing the absolute best CV score  
- ❌ Ignoring performance variance  
- ❌ Over-tuning sensitive parameters  
- ❌ Using sensitive models on small data  

Robustness > peak score.

---

## 14. Why Hyperparameter Sensitivity Matters

Hyperparameter sensitivity explains:

- Why boosting models are hard to tune
- Why defaults sometimes work surprisingly well
- Why some models fail outside Kaggle
- Why tuning strategy matters

It is a **meta-concept for practical ML success**.

---

## Usage Notes

- Link this note from:
  - Hyperparameter Tuning — MOC
  - Model Selection
  - Regularization
  - Bayesian Optimization
- Use this concept to justify *simpler models* in practice
