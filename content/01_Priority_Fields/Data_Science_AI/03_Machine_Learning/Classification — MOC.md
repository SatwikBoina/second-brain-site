# 📌 MOC — Classification

> Central hub for **classification problems in Machine Learning**.
> Classification is the task of predicting **discrete labels or classes**, often with associated probabilities, under uncertainty and asymmetric costs.

---

## 1. Core Idea

In classification, the goal is to learn a mapping:

$$
X \rightarrow Y \quad \text{where } Y \in \{\text{discrete classes}\}
$$

Most modern classifiers actually learn:
$$
X \rightarrow P(Y \mid X)
$$

Decisions are made **after** probabilities are produced.

---

## 2. Types of Classification Problems

---

### 2.1 Binary Classification
- Two classes (0 / 1)
- Examples: fraud detection, churn

---

### 2.2 Multi-Class Classification
- More than two classes
- Examples: digit recognition, document topic

---

### 2.3 Multi-Label Classification
- Multiple labels per instance
- Examples: tags, genres, symptoms

---

### 2.4 Ordinal Classification
- Ordered classes
- Examples: ratings (low / medium / high)

---

## 3. Classification Model Families

---

### 3.1 Linear Classifiers
- [[Logistic Regression]]
- Linear SVM

Characteristics:
- Simple
- Interpretable
- Limited non-linearity

---

### 3.2 Distance-Based Classifiers
- [[k-NN Classifier]]

Characteristics:
- No explicit training
- Very sensitive to scaling and outliers

---

### 3.3 Probabilistic / Generative Models
- [[Naive Bayes — MOC]]

Characteristics:
- Fast
- Strong assumptions
- Good with small data

---

### 3.4 Tree-Based Models
- [[Decision Tree Classifier]]
- [[Random Forest Classifier]]

Characteristics:
- Non-linear
- Handle interactions automatically
- Interpretable (to a degree)

---

### 3.5 Boosting-Based Models
- [[Gradient Boosting Classifier]]
- [[XGBoost Classifier]]
- [[LightGBM Classifier]]
- [[CatBoost Classifier]]

Characteristics:
- High accuracy
- Sensitive to hyperparameters
- Less interpretable

---

### 3.6 Margin-Based Models
- [[Support Vector Machine]]

Characteristics:
- Geometry-driven
- Strong generalization
- Poor probability calibration (by default)

---

### 3.7 Neural Network Models
- [[Neural Network Classifier]]

Characteristics:
- Very high capacity
- Data-hungry
- Black-box

---

## 4. Classification Loss Functions

Loss functions define **what the model learns**.

- [[Classification Loss Functions — MOC]]
- Log Loss
- Cross Entropy
- Hinge Loss
- Focal Loss
- Custom Loss Functions

Loss ≠ metric.

---

## 5. Evaluation Metrics for Classification

Metrics define **how models are judged**.

- Accuracy
- Precision / Recall
- F1-score
- ROC–AUC
- PR–AUC
- Confusion Matrix

🔗 Related:
- [[Evaluation Metrics — MOC]]

---

## 6. Probability, Thresholds, and Decisions

Classification is a **two-step process**:

1. Predict probabilities
2. Convert probabilities → labels

Key concepts:
- [[Threshold Tuning]]
- [[Probability Calibration]]

---

## 7. Class Imbalance

Most real-world classification problems are imbalanced.

Core issues:
- Accuracy becomes misleading
- Minority class performance collapses

🔗 Related:
- [[Class Imbalance]]
- [[Cost-Sensitive Learning]]

---

## 8. Cost-Sensitive Classification

Not all errors cost the same.

Classification decisions should often minimize:
- Expected business cost
- Risk, not error count

🔗 Related:
- [[Cost-Sensitive Learning]]
- [[Custom Loss Functions]]

---

## 9. Bias–Variance Perspective

- Simple classifiers → high bias, low variance
- Complex classifiers → low bias, high variance

Regularization and data size determine success.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 10. Hyperparameter Tuning in Classification

Key tuning tools:
- [[Grid Search]]
- [[Random Search]]
- [[Bayesian Optimization]]

Sensitivity varies widely across classifiers.

🔗 Related:
- [[Hyperparameter Sensitivity]]

---

## 11. Interpretability in Classification

Interpretability determines **trust and adoption**.

- Inherently interpretable models
- Post-hoc explanations for black-box models

🔗 Related:
- [[Model Interpretability]]

---

## 12. Fairness and Ethics in Classification

Classification decisions often affect people.

Key risks:
- Disparate impact
- Proxy discrimination
- Unequal error rates

🔗 Related:
- [[Fairness in Machine Learning]]

---

## 13. Common Failure Modes

- ❌ Using accuracy on imbalanced data  
- ❌ Ignoring thresholds  
- ❌ Optimizing wrong loss  
- ❌ No calibration  
- ❌ No fairness checks  

Classification failures are often **decision failures**, not model failures.

---

## 14. How Classification Fits in ML


Classification connects to:
- Loss functions
- Metrics
- Probabilistic modeling
- Decision theory
- Ethics

---

## Usage Rules

- This MOC is a navigation and reasoning hub
- Algorithms live in separate notes
- Losses, metrics, thresholds are first-class
- Always think: *probability → decision*
