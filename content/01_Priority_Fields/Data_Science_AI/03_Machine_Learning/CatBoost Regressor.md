---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: regression
model-family: ensemble-tree-models
ensemble-method: gradient-boosting
implementation: catboost
status: evergreen
---

# CatBoost Regressor

> A Gradient Boosting algorithm that handles categorical features natively and reduces prediction shift using ordered boosting and symmetric trees.

---

## 1. Core Idea

CatBoost (Categorical Boosting) is designed to **work well on real-world tabular data** by:

- Handling categorical features without one-hot encoding
- Reducing target leakage during training
- Providing stable and well-regularized boosting

🔗 Parent model:
- [[Gradient Boosting Regressor]]

🔗 Related:
- [[XGBoost Regressor]]
- [[LightGBM Regressor]]

---

## 2. What Makes CatBoost Different

CatBoost introduces three major innovations:

1. **Ordered Boosting**  
2. **Target Statistics for categorical features**  
3. **Symmetric (oblivious) trees**

These choices improve stability and reduce overfitting.

---

## 3. Intuition

CatBoost ensures that when a model learns from a data point, it **does not peek at its own target value** during feature encoding, preventing subtle leakage.

---

## 4. Analogy

Imagine grading exams:
- You grade one paper at a time
- You’re not allowed to see future answers while grading current ones

That’s ordered boosting.

---

## 5. Handling Categorical Features

CatBoost converts categorical variables into numerical statistics:

- Target mean encoding
- Ordered to prevent leakage
- Robust to high cardinality

🔗 Concepts:
- [[Target Encoding]]
- [[Data Leakage]]

---

## 6. Ordered Boosting

- Trees are built using a random permutation of data
- Each data point is predicted using only past information
- Prevents prediction shift

🔗 Concepts:
- [[Ordered Boosting]]
- [[Prediction Shift]]

---

## 7. Tree Structure: Symmetric Trees

CatBoost uses **oblivious (symmetric) trees**:

- Same split at each level
- Faster inference
- More regularized structure

🔗 See:
- [[Symmetric Trees]]

---

## 8. Mathematical Perspective

- Optimizes gradient boosting objective
- Incorporates ordered statistics
- Strong regularization via structure

---

## 9. Bias–Variance Tradeoff

- Slightly higher bias
- Lower variance
- More stable than LightGBM

🔗 See:
- [[Bias–Variance Tradeoff]]

---

## 10. Hyperparameters (Simpler Set)

Key hyperparameters include:

- iterations
- learning_rate
- depth
- l2_leaf_reg
- loss_function

CatBoost generally requires **less tuning**.

🔗 See:
- [[Hyperparameter Tuning — MOC]]

---

## 11. Regularization Techniques

CatBoost controls overfitting via:

- Tree symmetry
- Ordered boosting
- L2 regularization on leaf values

🔗 Links:
- [[Regularization — MOC]]

---

## 12. Handling Missing Values

- Handles missing values internally
- Learns default split directions

🔗 Links:
- [[Handling Missing Data]]

---

## 13. Feature Handling

- No feature scaling required
- Excellent with categorical-heavy datasets
- Handles non-linear interactions well

---

## 14. Evaluation Metrics

Uses standard regression metrics:

- RMSE
- MAE
- R²

🔗 See:
- [[Regression Metrics — MOC]]

---

## 15. Interpretability

- Strong SHAP integration
- Stable feature importance
- Easier debugging than other GBMs

🔗 Links:
- [[Model Interpretability]]
- [[SHAP Values]]

---

## 16. When CatBoost Works Well

- Many categorical features
- Small to medium datasets
- Minimal feature engineering
- Quick strong baseline

---

## 17. When It Fails

- Very large datasets (slower than LightGBM)
- Purely numerical data with simple structure
- Limited GPU availability

---

## 18. Relationship to Other Models

- Most user-friendly GBM
- Complements XGBoost and LightGBM

🔗 Related:
- [[XGBoost Regressor]]
- [[LightGBM Regressor]]

---

## 19. Position in the ML Landscape

- Production-ready boosting model
- Preferred when categorical data dominates
- Strong default for real-world ML
