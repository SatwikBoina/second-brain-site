# 📌 MOC — Ensemble Learning

> Central hub for **Ensemble Learning** in Machine Learning.
> Ensemble learning combines multiple models to produce a **stronger, more robust predictor** than any single model alone.

---

## 1. Core Idea

Ensemble learning is based on a simple but powerful principle:

> **Many weak or diverse models, when combined correctly, outperform a single strong model.**

Instead of relying on one hypothesis, ensembles aggregate **multiple hypotheses**.

---

## 2. Why Ensemble Learning Works

Ensembles improve performance by:
- Reducing variance
- Reducing bias (in some cases)
- Increasing robustness to noise
- Mitigating model-specific weaknesses

The key requirement is **diversity** among models.

---

## 3. Bias–Variance Perspective

Ensemble methods can be understood through bias–variance tradeoff:

- [[Bagging]] → primarily reduces variance
- [[Boosting ]]→ primarily reduces bias
- Stacking → balances both

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 4. Types of Ensemble Learning

---

### 4.1 Bagging (Bootstrap Aggregating)

Idea:
- Train models independently on different bootstrap samples
- Aggregate predictions (average / vote)

Characteristics:
- Strong variance reduction
- Parallelizable
- Robust to overfitting

Examples:
- [[Random Forest]]

🔗 Related:
- [[Decision Trees]]

---

### 4.2 Boosting

Idea:
- Train models sequentially
- Each model focuses on previous errors

Characteristics:
- Strong bias reduction
- Sensitive to noise
- Highly expressive

Examples:
- [[Gradient Boosting]]
- [[XGBoost]]
- [[LightGBM]]
- [[CatBoost]]

---

### 4.3 Stacking (Stacked Generalization)

Idea:
- Combine heterogeneous models
- Learn how to weight their predictions using a meta-model

Characteristics:
- Very powerful
- High risk of overfitting if misused

Examples:
- Linear / tree-based meta-learners

🔗 Related:
- [[Model Selection]]

---

### 4.4 Voting Ensembles

Idea:
- Combine predictions via majority vote or averaging

Characteristics:
- Simple
- Effective baseline ensemble

---

## 5. Sources of Diversity in Ensembles

Ensemble strength comes from diversity:

- Different training samples
- Different feature subsets
- Different algorithms
- Different hyperparameters
- Different random seeds

No diversity → no benefit.

---

## 6. Ensemble Learning and Error Correlation

Ensembles work best when:
- Individual models make **uncorrelated errors**

Highly correlated models add little value.

---

## 7. Ensemble Learning in Regression vs Classification

### Regression
- Averaging predictions
- Reduces variance smoothly

### Classification
- Majority vote or probability averaging
- Improves decision boundaries

🔗 Related:
- [[Regression — MOC]]
- [[Classification — MOC]]

---

## 8. Loss Functions and Ensembles

Ensembles optimize loss **indirectly**:

- Individual models optimize their own loss
- Aggregation reduces expected loss

Boosting explicitly optimizes loss via additive modeling.

🔗 Related:
- [[Regression Loss Functions — MOC]]
- [[Classification Loss Functions — MOC]]

---

## 9. Ensemble Learning and Overfitting

- Bagging → strong defense against overfitting
- Boosting → can overfit noisy data
- Stacking → high overfitting risk

Proper validation is critical.

🔗 Related:
- [[Cross Validation]]
- [[Early Stopping]]

---

## 10. Hyperparameter Sensitivity

Ensemble methods often have:
- Many hyperparameters
- High sensitivity (especially boosting)

Tuning strategy matters more than algorithm choice.

🔗 Related:
- [[Hyperparameter Sensitivity]]
- [[Bayesian Optimization]]

---

## 11. Interpretability of Ensembles

Interpretability decreases as complexity increases:

| Model | Interpretability |
|----|----------------|
| Single tree | High |
| Random Forest | Medium |
| Boosting | Low |
| Stacking | Very Low |

Post-hoc methods are often required.

🔗 Related:
- [[Model Interpretability]]

---

## 12. Ensemble Learning and Fairness

Ensembles can:
- Reduce variance-driven bias
- Also amplify hidden data bias

Fairness must be evaluated explicitly.

🔗 Related:
- [[Fairness in Machine Learning]]

---

## 13. When Ensemble Learning Works Best

- Weak but diverse base learners
- Noisy datasets
- Non-linear decision boundaries
- Competitive modeling scenarios

---

## 14. When Ensemble Learning Is Overkill

- Very small datasets
- Strict interpretability requirements
- Low-latency systems
- Simple linear problems

---

## 15. Common Misconceptions

- ❌ More models always mean better performance  
- ❌ Boosting never overfits  
- ❌ Ensembles eliminate bias automatically  
- ❌ Random Forests don’t need tuning  

Ensembles amplify both **good and bad design choices**.

---

## 16. Relationship to Other Concepts

Ensemble learning connects strongly to:

- [[Decision Trees]]
- [[Neural Networks — MOC]]
- [[Model Selection]]
- [[Cross Validation]]
- [[Regularization — MOC]]

---

## 17. Why Ensemble Learning Matters

Ensemble learning explains:

- Why Random Forests are strong defaults
- Why boosting dominates tabular ML
- Why Kaggle winners use ensembles
- Why diversity beats complexity

It is a **systems-level learning strategy**, not just an algorithm.

---

## Usage Rules

- This MOC is a conceptual and navigational hub
- Individual ensemble methods live in separate notes
- Always reason about *diversity + aggregation*
- Prefer understanding over blindly stacking models
