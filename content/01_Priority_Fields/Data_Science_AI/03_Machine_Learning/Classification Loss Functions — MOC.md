# 📌 MOC — Classification Loss Functions

> Central hub for **loss functions used in classification problems**.
> Classification loss functions define *how misclassification is penalized* and directly influence probability calibration, class imbalance handling, and decision boundaries.

---

## 1. Core Idea

A classification loss function measures the discrepancy between:

- True class label \(y\)
- Predicted class or probability \(\hat{y}\)

The choice of loss function determines:
- How probabilities are learned
- Sensitivity to class imbalance
- Margin behavior
- Robustness to noisy labels

---

## 2. Probability-Based Losses

Loss functions that operate on **predicted probabilities**.

Characteristics:
- Encourage probability calibration
- Differentiable
- Common in modern classifiers

### Losses
- [[Log Loss]]
- [[Binary Cross Entropy]]
- [[Categorical Cross Entropy]]

🔗 Related:
- [[Probability Calibration]]
- [[Softmax Function]]
- [[Sigmoid Function]]

---

## 3. Margin-Based Losses

Loss functions that enforce a **margin of separation** between classes.

Characteristics:
- Focus on decision boundaries
- Less emphasis on calibrated probabilities
- Strong generalization properties

### Losses
- [[Hinge Loss]]
- [[Squared Hinge Loss]]

🔗 Related:
- [[Support Vector Machine]]
- [[Maximum Margin Classifier]]

---

## 4. Robust Classification Losses

Loss functions designed to handle:
- Label noise
- Outliers
- Mislabelled data

Characteristics:
- Reduced sensitivity to extreme errors

### Losses
- [[Modified Huber Loss]]
- [[Savage Loss]]

🔗 Related:
- [[Outliers]]
- [[Robust Statistics]]

---

## 5. Asymmetric / Cost-Sensitive Losses

Loss functions that penalize **false positives and false negatives differently**.

Characteristics:
- Business- or risk-driven
- Useful for imbalanced problems

### Losses
- [[Weighted Cross Entropy]]
- [[Focal Loss]]
- [[Cost-Sensitive Loss]]

🔗 Related:
- [[Class Imbalance]]
- [[Cost-Sensitive Learning]]

---

## 6. Loss Functions for Imbalanced Classification

Specialized losses to focus learning on minority classes.

Characteristics:
- Reduce majority-class dominance
- Improve recall on rare classes

### Losses
- [[Focal Loss]]
- [[Balanced Cross Entropy]]

🔗 Related:
- [[Class Imbalance]]
- [[Threshold Tuning]]

---

## 7. Multi-Class Classification Losses

Losses designed for more than two classes.

Characteristics:
- Normalize across classes
- Often softmax-based

### Losses
- [[Categorical Cross Entropy]]
- [[Sparse Categorical Cross Entropy]]

---

## 8. Loss Functions and Decision Boundaries

| Loss Type | Boundary Behavior |
|---------|------------------|
| Log Loss | Smooth, probabilistic |
| Hinge Loss | Sharp, margin-based |
| Focal Loss | Focused on hard samples |

Loss choice changes **how the boundary is shaped**.

---

## 9. Loss Functions and Probability Calibration

- Log loss → good calibration
- Hinge loss → poor calibration
- Focal loss → often miscalibrated

🔗 Related:
- [[Probability Calibration]]
- [[Platt Scaling]]

---

## 10. Bias–Variance Perspective

- Strong penalties → lower bias, higher variance
- Smooth losses → better stability
- Robust losses → higher bias, lower variance

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 11. Algorithm-Specific Preferences

| Algorithm | Common Loss |
|--------|-------------|
| Logistic Regression | Log Loss |
| Naive Bayes | Log Loss (implicit) |
| SVM | Hinge Loss |
| Neural Networks | Cross Entropy |
| Gradient Boosting | Log Loss |
| XGBoost | Log Loss / Custom |
| LightGBM | Log Loss |
| CatBoost | Log Loss |

---

## 12. Loss Functions vs Evaluation Metrics

- **Loss functions** → optimized during training
- **Metrics** → used for evaluation and reporting

They may intentionally differ.

🔗 Related:
- [[Evaluation Metrics — MOC]]

---

## 13. Business Alignment Perspective

Loss functions encode **what kind of mistakes matter**:

- Fraud detection → false negatives costly
- Medical diagnosis → recall-focused
- Ads → probability calibration important

Wrong loss ⇒ wrong optimization.

---

## 14. Common Misconceptions

- ❌ Accuracy is a loss function  
- ❌ One loss works for all classifiers  
- ❌ Better loss always means better business outcome  
- ❌ Loss and metric must be the same  

Loss functions reflect **priorities**, not truth.

---

## Usage Rules

- No derivations in this MOC
- Each loss lives in its own atomic note
- Algorithms link to the loss they optimize
- Extend via links, not explanations
