# 📌 MOC — Hyperparameter Tuning

> Central hub for **Hyperparameter Tuning** in Machine Learning.
> Hyperparameter tuning is the process of selecting values for model settings that control **learning behavior, model complexity, and generalization**, but are **not learned from data directly**.

---

## 1. Core Idea

Hyperparameters define *how a model learns*, not *what it learns*.

They control:
- Model capacity
- Regularization strength
- Optimization dynamics
- Decision boundaries

Poor hyperparameters can ruin a good model.  
Good hyperparameters can rescue a weak one.

---

## 2. Parameters vs Hyperparameters

| Aspect | Parameters | Hyperparameters |
|----|----|----|
| Learned from data | ✅ | ❌ |
| Optimized during training | ✅ | ❌ |
| Examples | Weights, coefficients | Learning rate, depth, C |

Hyperparameters are **chosen**, not learned.

---

## 3. Why Hyperparameter Tuning Matters

Hyperparameter tuning affects:
- Bias–variance tradeoff
- Overfitting vs underfitting
- Training stability
- Final model performance
- Reproducibility

In practice:
> Performance differences often come more from tuning than model choice.

---

## 4. Common Hyperparameters Across Models

### Model Complexity
- Tree depth
- Number of estimators
- Number of layers / neurons

### Regularization
- L1 / L2 strength
- Dropout rate
- Early stopping patience

### Optimization
- Learning rate
- Batch size
- Optimizer choice

🔗 Related:
- [[Model Complexity]]
- [[Regularization — MOC]]

---

## 5. Hyperparameter Sensitivity

Not all hyperparameters matter equally.

- Some have **large performance impact**
- Some are highly **sensitive**
- Some barely matter

Understanding sensitivity determines **tuning strategy**.

🔗 Related:
- [[Hyperparameter Sensitivity]]

---

## 6. Hyperparameter Search Strategies

---

### 6.1 Grid Search

- Exhaustive search over fixed grid
- Simple, but inefficient

🔗 Related:
- [[Grid Search]]

---

### 6.2 Random Search

- Random sampling from distributions
- Much more efficient in high dimensions

🔗 Related:
- [[Random Search]]

---

### 6.3 Bayesian Optimization

- Learns from previous trials
- Sample-efficient
- Expensive but powerful

🔗 Related:
- [[Bayesian Optimization]]

---

### 6.4 Early-Stopping–Aware Methods

- Stop bad configurations early
- Allocate budget adaptively

Used heavily in deep learning.

🔗 Related:
- [[Early Stopping]]

---

## 7. Validation Strategy for Tuning

Hyperparameter tuning must be done with **proper validation**.

Correct flow:
1. Train–test split
2. Hyperparameter tuning on training (via CV)
3. Final evaluation on test set

Never tune on the test set.

🔗 Related:
- [[Cross Validation]]
- [[Data Leakage]]

---

## 8. Hyperparameter Tuning and Bias–Variance

- Strong regularization → higher bias, lower variance
- Weak regularization → lower bias, higher variance

Tuning is the *mechanism* to navigate this tradeoff.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Overfitting vs Underfitting]]

---

## 9. Model-Specific Tuning Difficulty

| Model | Tuning Difficulty |
|----|------------------|
| Linear Models | Low |
| Logistic Regression | Low |
| Decision Trees | Medium |
| Random Forest | Medium |
| Gradient Boosting | High |
| XGBoost / LightGBM | Very High |
| Neural Networks | Very High |

Complex models demand **careful tuning**.

---

## 10. Hyperparameter Tuning and Loss Functions

Tuning optimizes performance **relative to a loss / metric**.

Changing the loss:
- Changes the optimal hyperparameters
- Changes model behavior

🔗 Related:
- [[Regression Loss Functions — MOC]]
- [[Classification Loss Functions — MOC]]

---

## 11. Hyperparameter Tuning and Compute Budget

Tuning is a **resource allocation problem**.

Trade-offs:
- Fewer trials × better strategy
- More trials × simpler strategy

Efficiency matters more than exhaustiveness.

---

## 12. Common Failure Modes

- ❌ Tuning too many parameters at once  
- ❌ Overfitting to validation set  
- ❌ Ignoring variance across folds  
- ❌ Blindly copying defaults from tutorials  
- ❌ Treating tuning as an afterthought  

Tuning is a **design step**, not cleanup.

---

## 13. Practical Tuning Heuristics

- Start with simple models
- Tune the most sensitive parameters first
- Use random search before Bayesian methods
- Prefer robust plateaus over sharp optima
- Track both mean and variance of metrics

---

## 14. Hyperparameter Tuning in Production

Production considerations:
- Stability > peak performance
- Reproducibility
- Monitoring drift
- Re-tuning schedules

A fragile model is a liability.

---

## 15. Relationship to Other Concepts

Hyperparameter tuning connects strongly to:

- [[Model Selection]]
- [[Evaluation Metrics — MOC]]
- [[Neural Networks — MOC]]
- [[Ensemble Learning — MOC]]
- [[Probability Calibration]]

---

## 16. Why Hyperparameter Tuning Matters

Hyperparameter tuning explains:

- Why defaults rarely work best
- Why two identical models behave differently
- Why “best CV score” often fails in production
- Why robustness beats leaderboard chasing

It is the **control system of machine learning**.

---

## Usage Rules

- This MOC is a navigation + reasoning hub
- Search strategies live in separate notes
- Always pair tuning with proper validation
- Prefer understanding sensitivity over brute force
