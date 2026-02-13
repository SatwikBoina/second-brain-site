---
type: concept
domain: machine-learning
category: classification
status: evergreen
---

# Class Imbalance

> Class imbalance occurs when one or more classes are **significantly under-represented** compared to others, causing standard models and metrics to behave misleadingly.

---

## 1. Core Idea

In imbalanced datasets:
- Majority class dominates learning
- Minority class is often ignored
- High accuracy can coexist with poor real-world performance

> The model learns what is *frequent*, not what is *important*.

---

## 2. Why Class Imbalance Is a Problem

Class imbalance leads to:
- Biased decision boundaries
- Poor recall for minority class
- Misleading evaluation metrics
- Overconfident but useless models

Example:
- 99% accuracy by predicting only the majority class

---

## 3. Common Real-World Examples

- Fraud detection (fraud is rare)
- Medical diagnosis (disease is rare)
- Churn prediction
- Defect detection
- Spam filtering

Class imbalance is the **default**, not the exception.

---

## 4. Class Imbalance vs Data Imbalance

Important distinction:

- **Class imbalance** → imbalance in target labels  
- **Feature imbalance** → skewed feature distributions  

Only class imbalance affects **classification objectives directly**.

---

## 5. Why Accuracy Fails

Accuracy assumes:
- Equal importance of all classes
- Balanced class distribution

In imbalanced data, accuracy hides failure.

🔗 Related:
- [[Evaluation Metrics — MOC]]

---

## 6. Better Metrics for Imbalanced Data

Preferred metrics include:

- Precision
- Recall
- F1-score
- ROC–AUC
- PR–AUC
- Confusion Matrix

🔗 Related:
- [[Classification Metrics — MOC]]
- [[Confusion Matrix]]

---

## 7. Strategies to Handle Class Imbalance

---

### 7.1 Data-Level Approaches (Resampling)

#### Oversampling
- Duplicate or synthesize minority samples
- Examples: SMOTE, ADASYN

✔ Improves recall  
❌ Risk of overfitting

---

#### Undersampling
- Remove majority class samples

✔ Fast  
❌ Loss of information

---

#### Hybrid Sampling
- Combine over + under sampling

🔗 Related:
- [[Sampling Techniques]]

---

### 7.2 Algorithm-Level Approaches

#### Class Weights
- Penalize misclassification of minority class more

Used in:
- Logistic Regression
- SVM
- Tree-based models
- Boosting models

🔗 Related:
- [[Cost-Sensitive Learning]]

---

#### Specialized Loss Functions
- Focal Loss
- Weighted Cross Entropy

🔗 Related:
- [[Classification Loss Functions — MOC]]
- [[Custom Loss Functions]]

---

### 7.3 Prediction-Level Approaches

#### Threshold Tuning
- Change decision threshold
- Trade precision vs recall

🔗 Related:
- [[Threshold Tuning]]

---

## 8. Algorithm Sensitivity to Class Imbalance

| Algorithm | Sensitivity |
|--------|-------------|
| Logistic Regression | High |
| k-NN | High |
| SVM | High |
| Decision Tree | Medium |
| Random Forest | Medium |
| Gradient Boosting | Medium |
| XGBoost | Medium |
| LightGBM | Medium |
| CatBoost | Lower |
| Naive Bayes | Low |

---

## 9. Class Imbalance and Loss Functions

Loss choice strongly affects imbalance handling:

- Log Loss → biased toward majority
- Weighted Loss → balanced learning
- Focal Loss → focuses on hard minority samples

🔗 Related:
- [[Classification Loss Functions — MOC]]
- [[Margin-Based Losses]]

---

## 10. Class Imbalance and Probability Calibration

Imbalanced data often produces:
- Poorly calibrated probabilities
- Overconfident majority predictions

Calibration may be required post-training.

🔗 Related:
- [[Probability Calibration]]

---

## 11. Class Imbalance and Cross Validation

Best practices:
- Use stratified sampling
- Preserve class ratios across folds

🔗 Related:
- [[Stratified Sampling]]
- [[Cross Validation]]

---

## 12. Common Mistakes

- ❌ Using accuracy as primary metric  
- ❌ Resampling before train–test split  
- ❌ Ignoring business cost of errors  
- ❌ Blind oversampling  

Class imbalance handling is **context-dependent**.

---

## 13. When NOT to “Fix” Class Imbalance

Do NOT rebalance when:
- Real-world class distribution matters
- Probabilities must reflect reality
- Deployment distribution matches training

Sometimes imbalance is **the signal**.

---

## 14. Why Class Imbalance Matters

Class imbalance explains:
- Why models fail silently
- Why recall collapses
- Why loss functions matter
- Why metrics must change

It is a **core classification survival skill**.

---

## Usage Notes

- Link this note from:
  - Classification Metrics — MOC
  - Classification Loss Functions — MOC
  - Threshold Tuning
  - Model Selection
- Do NOT treat imbalance as a preprocessing afterthought
