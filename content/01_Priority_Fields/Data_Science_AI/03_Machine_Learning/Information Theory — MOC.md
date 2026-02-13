# 📌 MOC — Information Theory for Machine Learning

> Central hub for **Information Theory concepts used in Machine Learning**.
> Information theory provides a framework to **quantify uncertainty, information, and compression**, which directly underpins loss functions, probabilistic modeling, feature selection, and representation learning.

---

## 1. Core Idea

Information theory asks a fundamental question:

> *How much information does a variable contain?*

In ML, this becomes:
- How uncertain is a prediction?
- How much does a feature reduce uncertainty?
- How efficiently can data be represented?
- How surprised is the model by the data?

Most ML objectives are **information objectives in disguise**.

---

## 2. Why Information Theory Matters for ML

Information theory explains:
- Why cross-entropy works
- Why log loss is preferred
- Why decision trees split the way they do
- Why representation learning compresses data
- Why generalization relates to compression

> ML is not just prediction — it is **information processing**.

---

## 3. Random Variables and Uncertainty

Information theory starts with:
- Random variables
- Probability distributions
- Uncertainty

More uncertainty → more information gained when resolved.

🔗 Related:
- [[Probability Theory]]
- [[Probabilistic Models — MOC]]

---

## 4. Entropy

Entropy measures **uncertainty**.

\[
H(X) = - \sum_x P(x)\log P(x)
\]

Intuition:
- High entropy → unpredictable
- Low entropy → predictable

Used in:
- Decision trees
- Compression
- Uncertainty estimation

---

## 5. Conditional Entropy

Measures remaining uncertainty after observing another variable.

\[
H(Y \mid X)
\]

Used to quantify:
- How informative features are
- How much uncertainty remains after prediction

---

## 6. Mutual Information

Mutual information measures **shared information** between variables.

\[
I(X;Y) = H(Y) - H(Y \mid X)
\]

Interpretation:
> How much knowing \(X\) reduces uncertainty about \(Y\)

Used in:
- Feature selection
- Dependency detection
- Representation learning

🔗 Related:
- [[Feature Selection]]

---

## 7. Information Gain

Information gain is **reduction in entropy**.

Used heavily in:
- Decision Trees
- Random Forests

Splits are chosen to **maximize information gain**.

🔗 Related:
- [[Decision Tree Classifier]]

---

## 8. Cross Entropy

Cross entropy measures **mismatch between true distribution and predicted distribution**.

\[
H(p, q) = - \sum p(x)\log q(x)
\]

Used as:
- Primary loss for classification
- Objective for probabilistic models

🔗 Related:
- [[Classification Loss Functions — MOC]]

---

## 9. KL Divergence (Relative Entropy)

KL divergence measures **distance between distributions**.

\[
D_{KL}(p \| q)
\]

Interpretation:
> How much extra information is needed when using \(q\) instead of \(p\)

Used in:
- Variational inference
- Regularization
- Model comparison

🔗 Related:
- [[Probabilistic Models — MOC]]

---

## 10. Likelihood and Information

Maximizing likelihood is equivalent to:
- Minimizing cross entropy
- Minimizing KL divergence (up to constants)

This unifies:
- Loss functions
- Probabilistic modeling
- Optimization

---

## 11. Information Theory and Loss Functions

Many losses are information-theoretic:

| Loss | Interpretation |
|---|---|
| Log loss | Cross entropy |
| MSE | Gaussian negative log-likelihood |
| MAE | Laplace negative log-likelihood |

🔗 Related:
- [[Loss Functions — MOC]]

---

## 12. Information Theory and Model Complexity

Information theory explains:
- Overfitting as memorization
- Generalization as compression
- Regularization as information constraint

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Regularization — MOC]]

---

## 13. Information Bottleneck Principle

Key idea:
> Learn representations that retain **only information relevant to the target**.

Used in:
- Representation learning
- Deep learning theory

🔗 Related:
- [[Representation Learning]]
- [[Neural Networks — MOC]]

---

## 14. Information Theory and Feature Engineering

Good features:
- Reduce uncertainty about the target
- Increase mutual information
- Avoid redundant information

Bad features:
- Add noise
- Increase entropy without signal

---

## 15. Information Theory and Evaluation

Evaluation metrics often measure:
- Uncertainty reduction
- Surprise
- Probability quality

Examples:
- Log loss
- Brier score

🔗 Related:
- [[Evaluation Metrics — MOC]]
- [[Probability Calibration]]

---

## 16. Common Misconceptions

- ❌ Information ≠ data volume  
- ❌ Entropy ≠ randomness alone  
- ❌ Mutual information implies causation  
- ❌ Lower entropy is always better  

Information is **contextual and relative**.

---

## 17. How Information Theory Fits in ML

Probability  
↓  
Information Theory  
↓  
Loss Functions  
↓  
Optimization  
↓  
Learning


It is the **objective foundation** of ML.

---

## Usage Rules

- This MOC is a conceptual backbone
- Each measure lives in its own atomic note
- Always connect formulas to intuition
- Ask: *what uncertainty is being reduced?*
