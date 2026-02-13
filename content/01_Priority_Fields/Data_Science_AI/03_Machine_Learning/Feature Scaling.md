---
type: concept
domain: machine-learning
category: preprocessing
status: evergreen
---

# Feature Scaling

> Feature scaling is the process of transforming features so they exist on a **comparable numerical scale**, preventing certain features from dominating others due to magnitude alone.

---

## 1. Core Idea

Many ML algorithms rely on **distance, gradients, or similarity**.

If features are on different scales:
- Large-scale features dominate
- Model behavior becomes distorted
- Optimization becomes unstable

Feature scaling fixes this.

---

## 2. Why Feature Scaling Is Needed

Without scaling:

- Distance-based models break
- Gradient-based optimization slows or diverges
- Regularization behaves unevenly

Tree-based models are the **main exception**.

---

## 3. Common Feature Scaling Techniques

### 3.1 Standardization (Z-score Scaling)

Transforms data to:
- Mean = 0
- Standard deviation = 1

Best for:
- Linear models
- SVM
- Logistic Regression
- PCA

🔗 Related:
- [[Standardization]]

---

### 3.2 Normalization (Min–Max Scaling)

Scales data to a fixed range (usually [0, 1]).

Best for:
- k-NN
- Neural networks
- Distance-based models

🔗 Related:
- [[Normalization]]

---

### 3.3 Robust Scaling

Uses:
- Median
- Interquartile Range (IQR)

Best for:
- Data with outliers

🔗 Related:
- [[Outliers]]

---

## 4. Algorithms That REQUIRE Feature Scaling

Feature scaling is **mandatory** for:

- [[k-Nearest Neighbors Regressor]]
- [[k-Nearest Neighbors Classifier]]
- [[Support Vector Machine]]
- [[Support Vector Regression]]
- [[Logistic Regression]]
- [[Linear Regression]] (with regularization)
- [[PCA]]

---

## 5. Algorithms That Do NOT Need Feature Scaling

Feature scaling is **not required** for:

- [[Decision Tree Classifier]]
- [[Decision Tree Regressor]]
- [[Random Forest Classifier]]
- [[Random Forest Regressor]]
- [[Gradient Boosting Classifier]]
- [[XGBoost Classifier]]
- [[LightGBM Classifier]]
- [[CatBoost Classifier]]

Reason:
- Tree splits are scale-invariant

---

## 6. Feature Scaling and Regularization

Regularization penalties depend on feature magnitude.

Without scaling:
- L1 / L2 penalties become inconsistent
- Coefficient interpretation breaks

🔗 Related:
- [[Regularization — MOC]]

---

## 7. Feature Scaling and Distance Metrics

Distance metrics assume comparable scales.

Unscaled features:
- Distort Euclidean distance
- Break cosine similarity
- Ruin neighborhood structure

🔗 Related:
- [[Distance Metrics — MOC]]
- [[Distance-Based Models — MOC]]

---

## 8. Feature Scaling and Optimization

Scaling improves:
- Gradient descent convergence
- Numerical stability
- Training speed

🔗 Related:
- [[Gradient Descent]]

---

## 9. Feature Scaling and Data Leakage ⚠️

❌ Wrong:
- Scaling before train–test split

✅ Correct:
1. Split data
2. Fit scaler on training set
3. Apply scaler to validation/test set

🔗 Core concept:
- [[Data Leakage]]

---

## 10. Choosing the Right Scaling Method

| Scenario | Recommended Scaling |
|------|-------------------|
| Distance-based models | Normalization |
| Linear models | Standardization |
| SVM (RBF) | Standardization |
| Outliers present | Robust scaling |
| Tree-based models | None |

---

## 11. Common Misconceptions

- ❌ Scaling improves tree models  
- ❌ Scaling changes data distribution meaningfully  
- ❌ Scaling fixes poor features  

Scaling improves **geometry**, not information.

---

## 12. Why Feature Scaling Matters

Feature scaling explains:

- Why k-NN suddenly works or fails
- Why SVM performance changes drastically
- Why regularization behaves oddly
- Why optimization sometimes explodes

It is **non-negotiable preprocessing** for many models.

---

## Usage Notes

- Link this note from:
  - k-NN
  - SVM / SVR
  - Logistic Regression
  - Regularization
  - Distance Metrics
- Do NOT duplicate scaling explanations elsewhere
