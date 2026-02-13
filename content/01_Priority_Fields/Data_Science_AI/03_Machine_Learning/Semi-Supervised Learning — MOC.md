---
type: concept
domain: machine-learning
category: learning-paradigm
status: evergreen
---

# Semi-Supervised Learning

> Semi-supervised learning is a learning paradigm where a model is trained using a **small amount of labeled data** together with a **large amount of unlabeled data**.

---

## 1. Core Idea

In semi-supervised learning, we have:

- A small labeled dataset \( (X_l, Y_l) \)
- A large unlabeled dataset \( X_u \)

The goal is to leverage **unlabeled data** to improve learning beyond what labeled data alone can achieve.

Key assumption:
> Unlabeled data contains useful structure that aligns with the prediction task.

---

## 2. Why Semi-Supervised Learning Matters

Labels are:
- Expensive
- Slow to obtain
- Sometimes subjective

But **data itself is abundant**.

Semi-supervised learning allows us to:
- Reduce labeling cost
- Improve generalization
- Learn better representations
- Scale ML systems realistically

---

## 3. Where Semi-Supervised Learning Appears in Practice

- Medical imaging (few expert labels)
- Speech recognition
- NLP (massive unlabeled text)
- Web data classification
- Recommendation systems

In industry, *fully supervised learning is often the exception*.

---

## 4. Position in the ML Landscape

Unsupervised Learning  
↑  
Semi-Supervised Learning ← this  
↓  
Supervised Learning

Semi-supervised learning **borrows ideas from both sides**.

---

## 5. Core Assumptions Behind Semi-Supervised Learning

Semi-supervised methods rely on at least one of these assumptions:

---

### 5.1 Smoothness Assumption

- Points close in feature space should have similar labels

Used in:
- Graph-based methods

---

### 5.2 Cluster Assumption

- Data forms clusters
- Points in same cluster share labels

Used in:
- Self-training
- Pseudo-labeling

---

### 5.3 Manifold Assumption

- Data lies on a low-dimensional manifold
- Labels vary smoothly along the manifold

Used in:
- Representation learning
- Neural SSL methods

---

## 6. Major Approaches to Semi-Supervised Learning

---

### 6.1 Self-Training / Pseudo-Labeling

Process:
1. Train model on labeled data
2. Predict labels for unlabeled data
3. Add confident predictions as labels
4. Retrain

✔ Simple  
❌ Error reinforcement risk

---

### 6.2 Consistency Regularization

Idea:
- Model predictions should be consistent under perturbations

Used in:
- Modern deep learning SSL

---

### 6.3 Graph-Based Methods

Idea:
- Build similarity graph
- Propagate labels across graph

Examples:
- Label propagation
- Label spreading

---

### 6.4 Generative Models

Idea:
- Model data distribution using unlabeled data
- Use labeled data to guide prediction

Examples:
- Semi-supervised VAEs
- Probabilistic models

🔗 Related:
- [[Probabilistic Models — MOC]]

---

### 6.5 Representation Learning + Supervision

Idea:
- Learn representations unsupervised
- Fine-tune with limited labels

Examples:
- Autoencoders + classifier
- Pretraining + fine-tuning

🔗 Related:
- [[Neural Networks — MOC]]
- [[Unsupervised Learning — MOC]]

---

## 7. Semi-Supervised Learning vs Related Paradigms

| Paradigm | Labeled Data | Unlabeled Data |
|-------|--------------|----------------|
| Supervised | All | Ignored |
| Unsupervised | None | All |
| Semi-supervised | Some | Used |
| Self-supervised | None (synthetic labels) | All |

---

## 8. Evaluation Challenges

Challenges:
- Small labeled validation sets
- Risk of confirmation bias
- Overconfidence in pseudo-labels

Best practices:
- Careful validation
- Conservative confidence thresholds

🔗 Related:
- [[Model Selection]]

---

## 9. Bias–Variance Perspective

Semi-supervised learning:
- Reduces variance by using more data
- Can increase bias if assumptions are wrong

Unlabeled data helps **only if assumptions hold**.

---

## 10. Risks and Failure Modes

- ❌ Propagating wrong labels
- ❌ Overconfident pseudo-labels
- ❌ Distribution mismatch
- ❌ Ignoring label noise

More data does **not** always mean better learning.

---

## 11. When Semi-Supervised Learning Works Best

- Labeled data is scarce
- Unlabeled data is abundant
- Data distribution is stable
- Clear cluster or manifold structure

---

## 12. When It Works Poorly

- Highly noisy data
- Weak feature representations
- Non-smooth decision boundaries
- Distribution shift between labeled and unlabeled data

---

## 13. Relationship to Other Concepts

Semi-supervised learning connects strongly to:

- [[Unsupervised Learning — MOC]]
- [[Supervised Learning — MOC]]
- [[Representation Learning]]
- [[Neural Networks — MOC]]
- [[Model Selection]]

---

## 14. Common Misconceptions

- ❌ Semi-supervised learning always helps  
- ❌ Unlabeled data is always beneficial  
- ❌ Pseudo-labels are ground truth  
- ❌ SSL removes need for good features  

Semi-supervised learning is **assumption-driven**, not magic.

---

## 15. Why Semi-Supervised Learning Matters

Semi-supervised learning explains:

- How modern ML scales with limited labels
- Why representation learning is powerful
- Why unlabeled data can act as regularization
- Why real-world ML rarely fits clean paradigms

It is the **pragmatic middle ground of ML**.

---

## Usage Notes

- Link this note from:
  - Unsupervised Learning — MOC
  - Supervised Learning — MOC
  - Neural Networks — MOC
  - Representation Learning
- Treat unlabeled data as a modeling assumption, not a free gift
