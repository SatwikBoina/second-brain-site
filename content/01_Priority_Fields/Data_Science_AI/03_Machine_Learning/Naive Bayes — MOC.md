# 📌 MOC — Naive Bayes Models

> Central hub for all **Naive Bayes classifiers**.
> Naive Bayes models are probabilistic classifiers based on Bayes’ Theorem with a strong conditional independence assumption.

---

## 1. Core Idea

Naive Bayes models compute the **posterior probability of a class given features**:

> P(Class | Features)

by assuming that features are **conditionally independent** given the class.

🔗 Core foundation:
- [[Bayes Theorem]]
- [[Conditional Probability]]

---

## 2. Why “Naive”?

The model assumes:

- Features are independent **given the class**
- This assumption is rarely true
- But works surprisingly well in practice

🔗 Core concept:
- [[Conditional Independence]]

---

## 3. Naive Bayes Variants (Algorithms)

### 3.1 Gaussian Naive Bayes

- [[Gaussian Naive Bayes]]

Used when features are continuous and assumed to be normally distributed.

---

### 3.2 Multinomial Naive Bayes

- [[Multinomial Naive Bayes]]

Used for count-based features (e.g., word counts in text).

---

### 3.3 Bernoulli Naive Bayes

- [[Bernoulli Naive Bayes]]

Used for binary / boolean features.

---

## 4. Learning Paradigm

- Supervised learning
- Classification only
- Generative model (models P(X | Y))

🔗 Contrast:
- [[Logistic Regression]] (discriminative model)

---

## 5. Probability Distributions Used

Depending on the variant:

- [[Gaussian Distribution]]
- [[Multinomial Distribution]]
- [[Bernoulli Distribution]]

---

## 6. Parameter Estimation

Naive Bayes parameters are estimated using:

- Maximum Likelihood Estimation (MLE)
- Maximum A Posteriori (MAP) estimation

🔗 Concepts:
- [[Maximum Likelihood Estimation]]
- [[MAP Estimation]]

---

## 7. Smoothing Techniques

To handle zero probabilities:

- [[Laplace Smoothing]]
- [[Additive Smoothing]]

Smoothing is **critical** for text models.

---

## 8. Bias–Variance Perspective

- High bias (strong assumptions)
- Very low variance
- Rarely overfits

🔗 See:
- [[Bias–Variance Tradeoff]]

---

## 9. Feature Handling Characteristics

Naive Bayes models:

- Do NOT require feature scaling
- Handle high-dimensional data well
- Are sensitive to feature correlation

🔗 Concepts:
- [[Feature Correlation]]

---

## 10. Evaluation Metrics

Standard classification metrics apply:

- Accuracy
- Precision
- Recall
- F1-score
- ROC–AUC

🔗 See:
- [[Classification Metrics — MOC]]

---

## 11. Interpretability

- Probabilistic and transparent
- Easy to debug
- Feature likelihoods are explainable

🔗 Links:
- [[Model Interpretability]]

---

## 12. When to Use Naive Bayes

- Text classification (spam, sentiment)
- Very high-dimensional sparse data
- Small datasets
- As a fast baseline

---

## 13. When to Avoid Naive Bayes

- Strongly correlated features
- Complex decision boundaries
- When probability calibration matters

---

## 14. Relationship to Other Model Families

- Probabilistic counterpart to discriminative models
- Complements [[Support Vector Machine]]
- Baseline alternative to [[Logistic Regression]]

---

## Usage Rules

- No algorithm derivations here
- Each variant lives in its own note
- Concepts remain atomic
- Extend via links, not explanations
