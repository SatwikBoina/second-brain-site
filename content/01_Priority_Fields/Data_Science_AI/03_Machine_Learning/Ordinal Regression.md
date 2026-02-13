---
type: algorithm
domain: machine-learning
category: supervised-learning
task: ordinal-regression
status: evergreen
---

# Ordinal Regression

> Ordinal Regression is a supervised learning approach used when the target variable consists of **ordered categories**, where the order matters but the exact distances between categories do not.

---

## 1. Core Idea

Ordinal regression handles targets like:

- Low < Medium < High  
- Poor < Average < Good < Excellent  
- 1 ⭐ < 2 ⭐ < 3 ⭐ < 4 ⭐ < 5 ⭐  

Key property:
> **Classes are ordered, but not numeric.**

---

## 2. Why Ordinal Regression Is Special

Ordinal problems sit **between**:

- Classification → ignores order  
- Regression → assumes numeric distances  

Ordinal regression:
- Uses order information
- Avoids assuming equal spacing

---

## 3. What Goes Wrong If You Ignore Ordinality

### Treating as Classification ❌
- Predicting “Low” instead of “High” is treated same as “Medium” vs “High”
- Loses severity information

### Treating as Regression ❌
- Assumes distance(1→2) = distance(4→5)
- Often unjustified

Ordinal regression respects **rank but not scale**.

---

## 4. Intuition

Think of ordinal regression as:

> Learning **boundaries on a latent continuous scale**, then mapping them to ordered categories.

The model predicts a hidden score, then decides which interval it falls into.

---

## 5. Latent Variable View

Most ordinal models assume:

- There exists a latent continuous variable \( z \)
- Observed label depends on which interval \( z \) falls into

\[
y =
\begin{cases}
1 & z \le \theta_1 \\
2 & \theta_1 < z \le \theta_2 \\
\vdots \\
K & z > \theta_{K-1}
\end{cases}
\]

Where:
- \( \theta_i \) are learned thresholds
- Order is enforced explicitly

---

## 6. Common Ordinal Regression Models

---

### 6.1 Ordinal Logistic Regression (Proportional Odds)

- Most common ordinal model
- Assumes same effect of features across thresholds

🔗 Related:
- [[Logistic Regression]]
- [[Probabilistic Models — MOC]]

---

### 6.2 Ordinal Probit Regression

- Uses Gaussian latent variable
- Similar to ordinal logistic but different link function

---

### 6.3 Threshold-Based Neural Models

- Neural network predicts latent score
- Thresholds map score → ordered classes

---

### 6.4 Tree-Based Ordinal Methods

- Modified tree splits respecting order
- Less common, more heuristic

---

## 7. Loss Functions for Ordinal Regression

Ordinal losses penalize **order violations**.

Common approaches:
- Cumulative link likelihood
- Ordinal cross-entropy
- Distance-weighted classification loss

🔗 Related:
- [[Custom Loss Functions]]
- [[Classification Loss Functions — MOC]]

---

## 8. Evaluation Metrics for Ordinal Regression

Accuracy alone is insufficient.

Better metrics:
- Mean Absolute Error on class indices
- Quadratic Weighted Kappa
- Spearman Rank Correlation
- Ordinal-aware confusion matrix

🔗 Related:
- [[Evaluation Metrics — MOC]]

---

## 9. Bias–Variance Perspective

- Ordinal models reduce bias vs classification
- Lower variance than regression
- Strong inductive bias via ordering constraint

Ordering acts as **regularization**.

---

## 10. Relationship to Other Tasks

| Task | Order Used | Distance Used |
|---|---|---|
| Classification | ❌ | ❌ |
| Ordinal Regression | ✅ | ❌ |
| Regression | ✅ | ✅ |

Ordinal regression is its **own problem type**.

---

## 11. When Ordinal Regression Works Best

- Ratings and surveys
- Risk levels
- Severity grading
- Quality assessments
- Human judgment labels

---

## 12. When Ordinal Regression Is a Poor Choice

- Truly categorical labels (no order)
- Continuous numeric targets
- When class distances are meaningful and known

---

## 13. Common Mistakes

- ❌ Treating ordinal data as nominal  
- ❌ Using accuracy as sole metric  
- ❌ Ignoring monotonicity  
- ❌ Assuming equal spacing between classes  

Ordinal problems require **ordinal thinking**.

---

## 14. Why Ordinal Regression Matters

Ordinal regression explains:

- Why ratings behave strangely in classifiers
- Why regression sometimes overfits ratings
- Why respecting structure improves generalization

It is a **structural inductive bias**, not a hack.

---

## Usage Notes

- Link this note from:
  - Classification — MOC
  - Regression — MOC
  - Evaluation Metrics — MOC
  - Custom Loss Functions
- Treat ordinal regression as its own task, not a variant
