---
type: algorithm
domain: machine-learning
paradigm: supervised
problem-type: classification
model-family: ensemble-tree-models
ensemble-method: gradient-boosting
implementation: catboost
status: evergreen
---

# CatBoost Classifier

> A Gradient Boosting classifier designed for real-world tabular data, with native categorical feature handling, ordered boosting, and symmetric trees to reduce overfitting and prediction shift.

---

## 1. Core Idea

CatBoost (Categorical Boosting) improves Gradient Boosting classification by:

- Handling categorical features natively
- Preventing target leakage via ordered boosting
- Using symmetric (oblivious) trees for stability

🔗 Parent model:
- [[Gradient Boosting Classifier]]

🔗 Related:
- [[XGBoost Classifier]]
- [[LightGBM Classifier]]

---

## 2. What Makes CatBoost Different

CatBoost introduces three defining ideas:

1. **Ordered Boosting**
2. **Target statistics for categorical features**
3. **Symmetric (oblivious) trees**

These design choices prioritize robustness and minimal tuning.

---

## 3. Intuition

CatBoost ensures that, while learning, the model **never uses a data point’s own label** to encode its categorical features—avoiding subtle leakage and overly optimistic training.

---

## 4. Analogy

Imagine learning from past exams:
- You’re allowed to use only *previous* answers
- You never peek at the current paper’s solution
- Learning stays fair and unbiased

That’s ordered boosting.

---

## 5. Handling Categorical Features

CatBoost converts categorical variables into numerical representations using:

- Target mean statistics
- Ordered permutations to prevent leakage
- Efficient handling of high-cardinality features

🔗 Concepts:
- [[Target Encoding]]
- [[Data Leakage]]

---

## 6. Ordered Boosting

- Data is processed using random permutations
- Each sample is predicted using only past information
- Prevents **prediction shift** common in boosting

🔗 Concepts:
- [[Ordered Boosting]]
- [[Prediction Shift]]

---

## 7. Tree Structure: Symmetric Trees

CatBoost uses **oblivious (symmetric) trees**:

- Same feature split at each depth level
- Faster inference
- Strong implicit regularization

🔗 See:
- [[Symmetric Trees]]

---

## 8. Mathematical Perspective

- Optimizes gradient boosting objective for classification
- Integrates ordered statistics into loss optimization
- Strong regularization via tree structure

---

## 9. Bias–Variance Tradeoff

- Slightly higher bias than LightGBM
- Lower variance and more stability
- Strong generalization on noisy, categorical data

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

CatBoost typically requires **less tuning** than other GBMs.

🔗 See:
- [[Hyperparameter Tuning — MOC]]

---

## 11. Regularization Techniques

CatBoost controls overfitting via:

- Ordered boosting
- Symmetric tree constraints
- L2 regularization on leaf values

🔗 Links:
- [[Regularization — MOC]]

---

## 12. Handling Missing Values

- Handles missing values internally
- Learns optimal default split directions

🔗 Links:
- [[Handling Missing Data]]

---

## 13. Feature Handling

- No feature scaling required
- Excellent for categorical-heavy datasets
- Automatically models feature interactions

---

## 14. Handling Class Imbalance

CatBoost supports:

- Class weights
- Custom loss functions
- Threshold tuning

🔗 Concepts:
- [[Class Imbalance]]
- [[Threshold Tuning]]

---

## 15. Evaluation Metrics

Common classification metrics:

- Accuracy
- Precision
- Recall
- F1-score
- ROC–AUC
- Log loss

🔗 See:
- [[Classification Metrics — MOC]]

---

## 16. Interpretability

- Strong SHAP integration
- Stable feature importance
- Easier debugging than other GBMs

🔗 Links:
- [[Model Interpretability]]
- [[SHAP Values]]

---

## 17. When CatBoost Classifier Works Well

- Datasets with many categorical features
- Small to medium-sized datasets
- Minimal feature engineering
- Quick, strong baseline classifier

---

## 18. When It Fails

- Very large datasets (slower than LightGBM)
- Purely numerical data with simple structure
- When GPU support is limited

---

## 19. Relationship to Other Models

- Most user-friendly boosting classifier
- Complements XGBoost and LightGBM

🔗 Related:
- [[XGBoost Classifier]]
- [[LightGBM Classifier]]

---

## 20. Position in the ML Landscape

- Production-ready gradient boosting classifier
- Preferred for categorical-heavy real-world data
- Strong default choice for tabular classification
