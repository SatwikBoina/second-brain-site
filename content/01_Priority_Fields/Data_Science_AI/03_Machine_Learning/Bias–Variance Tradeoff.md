---
type: concept
domain: machine-learning
category: model-evaluation
status: evergreen
---

## 1. Core Definition

The **Bias–Variance Tradeoff** describes the balance between a model’s ability to learn the **true underlying pattern** (bias) and its **sensitivity to variations in training data** (variance).

Reducing one typically increases the other.

---

## 2. Error Decomposition

The expected prediction error can be decomposed as:

$$
\text{Prediction Error} = \text{Bias}^2 + \text{Variance} + \text{Irreducible Error}
$$

- **Bias** and **Variance** are model-dependent
- **Irreducible Error** comes from noise in the data and cannot be eliminated

---

## 3. Bias vs Variance

| Aspect           | Bias                            | Variance                    |
| ---------------- | ------------------------------- | --------------------------- |
| Definition       | Error from wrong assumptions    | Error from data sensitivity |
| Model Nature     | Too simple or Wrong assumptions | Too complex                 |
| Typical Outcome  | [[Underfitting]]                | [[Overfitting]]             |
| Pattern Learning | Misses signal                   | Learns noise                |
| Stability        | Stable across datasets          | Varies with data            |

---

## 4. Effect of Model Complexity

| Model Complexity | Bias     | Variance | Behavior            |
| ---------------- | -------- | -------- | ------------------- |
| Low              | High     | Low      | [[Underfitting]]    |
| Medium           | Balanced | Balanced | Best generalization |
| High             | Low      | High     | [[Overfitting]]     |

Increasing complexity generally reduces bias but increases variance.

---

## 5. Practical Control

| Goal            | Technique                                  | Effect                  |
| --------------- | ------------------------------------------ | ----------------------- |
| Reduce variance | More data, [[Regularization — MOC]]        | ↑ Bias                  |
| Reduce bias     | [[Feature Engineering]], complex models    | ↑ Variance              |
| Diagnose        | [[Cross Validation]] , [[Learning Curves]] | Identify dominant error |

---

### Related Notes
- [[Model Complexity]]

---
## My Understanding
1. **Trade-Off :** Two parties compromise in exchange of something.
2.   $Prediction Error = Bias^2 + Variance + Irreducible Error (noise)$
3. Usually, The Trade-off happens among Bias and Variance in an attempt to reduce the Prediction Error Caused by the Model
4. A model's simplicity usually leads to failure in capturing the real relationship among the data - Bias.
5. A Model's complexity usually leads to failure in ignoring the noise within the data - Variance.


---
## Conceptual Clarity
1. Does Bias-Variance Trade off exist only in Supervised Learning?
	>Bias–variance tradeoff is mathematically grounded in supervised learning, but its intuition extends to unsupervised and reinforcement learning through model rigidity versus sensitivity to data or rewards.
	
	