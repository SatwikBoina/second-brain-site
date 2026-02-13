# 📌 MOC — Regularization

> Central hub for **regularization techniques** used to control model complexity, reduce overfitting, and improve generalization in Machine Learning.

---

## 1. Core Idea

Regularization introduces **constraints or penalties** during training to discourage overly complex models.

> Trade a small increase in bias for a large reduction in variance.

🔗 Core concepts:
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]
- [[Overfitting vs Underfitting]]

---

## 2. Why Regularization Is Needed

Regularization helps when models:
- Fit noise instead of signal
- Are unstable across datasets
- Have too many degrees of freedom

It is a **generalization control mechanism**, not a fix-all.

---

## 3. Regularization by Model Family

### 3.1 Linear Models

- [[L2 Regularization]] (Ridge)
- [[L1 Regularization]] (Lasso)
- [[Elastic Net Regularization]]

Algorithms:
- [[Ridge Regression]]
- [[Lasso Regression]]
- [[Elastic Net Regression]]
- [[Logistic Regression]] (L1 / L2)

---

### 3.2 Tree-Based Models

- [[Pruning]]
- [[Cost Complexity Pruning]]
- [[Tree Depth]]
- [[Minimum Samples per Leaf]]

Algorithms:
- [[Decision Tree Regressor]]
- [[Decision Tree Classifier]]
- [[Random Forest Regressor]]
- [[Random Forest Classifier]]

---

### 3.3 Boosting Models

- [[Learning Rate Shrinkage]]
- [[Early Stopping]]
- [[Subsampling]]
- [[Tree Depth Limitation]]

Algorithms:
- [[Gradient Boosting Regressor]]
- [[Gradient Boosting Classifier]]
- [[XGBoost Regressor]]
- [[LightGBM Regressor]]
- [[CatBoost Regressor]]

---

### 3.4 Kernel Methods

- [[Regularization Parameter C]]
- [[Margin Maximization]]

Algorithms:
- [[Support Vector Machine]]
- [[Support Vector Regression]]

---

### 3.5 Distance-Based Models

- [[Neighborhood Size (k)]]
- [[Distance Weighting]]

Algorithms:
- [[k-Nearest Neighbors Regressor]]
- [[k-Nearest Neighbors Classifier]]

---

### 3.6 Probabilistic Models

- [[Laplace Smoothing]]
- [[MAP Estimation]]

Algorithms:
- [[Gaussian Naive Bayes]]
- [[Multinomial Naive Bayes]]
- [[Bernoulli Naive Bayes]]

---

## 4. Explicit vs Implicit Regularization

### Explicit Regularization
- Penalty terms in loss
- Hyperparameters directly control strength

Examples:
- L1 / L2 penalties
- SVM margin control

### Implicit Regularization
- Arises from training dynamics or structure

Examples:
- Early stopping
- Ensemble averaging
- Symmetric trees (CatBoost)

---

## 5. Regularization Strength

Regularization strength controls **how aggressively complexity is penalized**:

- Too weak → overfitting
- Too strong → underfitting

🔗 Tools:
- [[Learning Curves]]
- [[Cross Validation]]

---

## 6. Bias–Variance Perspective

- Regularization ↑ bias
- Regularization ↓ variance
- Net effect → better generalization

🔗 Core concept:
- [[Bias–Variance Tradeoff]]

---

## 7. Interaction with Data Size

- Small datasets → strong regularization needed
- Large datasets → weaker regularization sufficient

More data reduces variance, complementing regularization.

---

## 8. Hyperparameter Tuning & Regularization

Regularization parameters must be tuned using:

- Cross-validation
- Validation curves
- Learning curves

🔗 See:
- [[Hyperparameter Tuning — MOC]]
- [[Model Selection]]

---

## 9. Common Misconceptions

- ❌ Regularization always improves performance  
- ❌ More regularization is safer  
- ❌ Only linear models need regularization  

All models regularize — some just hide it.

---

## 10. Why Regularization Matters

Regularization explains:

- Why ensembles work
- Why boosting needs shrinkage
- Why simpler models often generalize better
- Why training accuracy is not the goal

It is a **core lever in practical ML**.

---

## Usage Rules

- Do NOT place derivations here
- Algorithms link to this MOC
- Individual techniques live in atomic notes
- Extend via links, not explanations
