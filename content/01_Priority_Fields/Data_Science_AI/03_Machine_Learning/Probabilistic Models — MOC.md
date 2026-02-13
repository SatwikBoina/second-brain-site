# 📌 MOC — Probabilistic Models

> Central hub for **probabilistic approaches in Machine Learning**.
> Probabilistic models explicitly model **uncertainty** using probability distributions and reason about data through likelihoods, priors, and posteriors.

---

## 1. Core Idea

Probabilistic models describe data generation using probabilities.

Instead of predicting a single value, they model:
- Uncertainty in data
- Uncertainty in parameters
- Uncertainty in predictions

They answer:
> *How likely is this outcome, given what we know?*

---

## 2. What Makes a Model Probabilistic

A model is probabilistic if it:
- Models \( P(Y \mid X) \), \( P(X \mid Y) \), or both
- Uses probability distributions explicitly
- Is trained by maximizing likelihood or posterior probability

🔗 Core foundations:
- [[Probability Theory]]
- [[Bayes Theorem]]

---

## 3. Discriminative vs Generative Models

### Discriminative Models
Model the conditional probability:
$P(Y \mid X)$


Examples:
- [[Logistic Regression]]
- Neural Networks (probabilistic outputs)

---

### Generative Models
Model the joint distribution:
$P(X, Y) = P(X \mid Y) P(Y)$

Examples:
- [[Naive Bayes]]
- [[Gaussian Mixture Models]]

Generative models can **simulate data**.

---

## 4. Bayesian vs Frequentist Perspective

### Frequentist Models
- Parameters are fixed
- Data is random
- Optimize likelihood

Examples:
- Linear Regression (MLE)
- Logistic Regression (MLE)

---

### Bayesian Models
- Parameters are random variables
- Use priors + likelihood → posterior

Examples:
- [[Bayesian Linear Regression]]
- [[Bayesian Logistic Regression]]

🔗 Related:
- [[Bayesian Inference]]
- [[Maximum Likelihood Estimation]]
- [[MAP Estimation]]

---

## 5. Core Components of Probabilistic Models

### 5.1 Likelihood
- How probable the data is given parameters

### 5.2 Prior
- Beliefs before seeing data

### 5.3 Posterior
- Updated beliefs after seeing data

### 5.4 Evidence
- Normalizing constant

🔗 Related:
- [[Likelihood Function]]
- [[Prior Distribution]]
- [[Posterior Distribution]]

---

## 6. Major Families of Probabilistic Models

---

### 6.1 Naive Bayes Family

- [[Naive Bayes — MOC]]
- [[Gaussian Naive Bayes]]
- [[Multinomial Naive Bayes]]
- [[Bernoulli Naive Bayes]]

---

### 6.2 Linear Probabilistic Models

- [[Linear Regression]] (Gaussian noise)
- [[Logistic Regression]] (Bernoulli outcome)

---

### 6.3 Mixture Models

- [[Gaussian Mixture Models]]
- [[Mixture Density Networks]]

Used for clustering and density estimation.

---

### 6.4 Graphical Models

- [[Bayesian Networks]]
- [[Markov Random Fields]]
- [[Hidden Markov Models]]

Represent dependencies explicitly via graphs.

---

### 6.5 Latent Variable Models

- [[Expectation Maximization]]
- [[Probabilistic PCA]]
- [[Latent Dirichlet Allocation]]

Hidden variables explain observed structure.

---

### 6.6 Bayesian Non-Parametric Models

- [[Gaussian Processes]]
- [[Dirichlet Processes]]

Model complexity grows with data.

---

## 7. Training Probabilistic Models

Common training principles:

- Maximum Likelihood Estimation (MLE)
- Maximum A Posteriori (MAP)
- Variational Inference
- Markov Chain Monte Carlo (MCMC)

🔗 Related:
- [[Optimization]]
- [[Inference Methods]]

---

## 8. Probabilistic Models and Loss Functions

Many loss functions arise from **negative log-likelihood**.

Examples:
- MSE ↔ Gaussian likelihood
- Log loss ↔ Bernoulli / Categorical likelihood

🔗 Related:
- [[Regression Loss Functions — MOC]]
- [[Classification Loss Functions — MOC]]

---

## 9. Probabilistic Models and Uncertainty

Types of uncertainty:

- **Aleatoric** → inherent data noise
- **Epistemic** → uncertainty in parameters

Probabilistic models can express both.

🔗 Related:
- [[Uncertainty Quantification]]

---

## 10. Probabilistic Models vs Deterministic Models

| Aspect | Probabilistic | Deterministic |
|-----|--------------|--------------|
| Output | Distribution | Point estimate |
| Uncertainty | Explicit | Implicit / None |
| Interpretability | High | Medium |
| Computation | Often expensive | Often cheaper |

---

## 11. When Probabilistic Models Shine

- Small datasets
- High uncertainty domains
- Decision-making under risk
- Interpretability requirements
- Scientific modeling

---

## 12. When Probabilistic Models Struggle

- Very large-scale data
- High-dimensional feature spaces
- Strict latency constraints

---

## 13. Relationship to Other ML Concepts

Probabilistic models connect strongly to:

- [[Loss Functions]]
- [[Model Interpretability]]
- [[Probability Calibration]]
- [[Cost-Sensitive Learning]]
- [[Fairness in Machine Learning]]

---

## 14. Common Misconceptions

- ❌ Probabilistic models are always Bayesian  
- ❌ Probabilities imply causality  
- ❌ Probabilistic models are always slower  
- ❌ Deterministic models cannot output probabilities  

Probabilistic thinking is a **modeling choice**, not a constraint.

---

## Usage Rules

- This is a conceptual hub, not an algorithm note
- Each family lives in its own MOC or atomic note
- Algorithms should backlink here when probabilistic
- Extend via links, not long explanations
