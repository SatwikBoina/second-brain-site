# 📌 MOC — Recommender Systems

> Central hub for **Recommender Systems** in Machine Learning.
> Recommender systems predict **user–item interactions** to personalize content, products, or decisions under uncertainty, scale, and feedback loops.

---

## 1. Core Idea

A recommender system learns a function:

\[
(User, Item, Context) \rightarrow Relevance
\]

Where relevance may mean:
- Click
- Purchase
- Watch time
- Rating
- Engagement probability

Key challenge:
> Predicting preferences for **unseen interactions**.

---

## 2. Why Recommender Systems Matter

Recommenders drive:
- User engagement
- Revenue
- Retention
- Discovery

They power:
- E-commerce
- Streaming platforms
- News feeds
- Ads
- Social networks

In many companies, **recommendation IS the product**.

---

## 3. Core Challenges in Recommendation

- Extreme sparsity
- Cold start
- Feedback loops
- Scalability
- Delayed and noisy labels
- Multi-objective optimization

Recommenders are **harder than standard ML**.

---

## 4. Types of Recommendation Tasks

---

### 4.1 Rating Prediction

Predict explicit feedback.

Examples:
- Movie ratings
- Product ratings

---

### 4.2 Top-K Recommendation / Ranking

Predict best items to show.

Examples:
- Homepage feeds
- Search results
- Watch next

---

### 4.3 Next-Item Prediction

Predict next interaction in a sequence.

Examples:
- Music playlists
- Video recommendations

---

## 5. Main Families of Recommender Systems

---

## 5.1 Content-Based Filtering

Idea:
- Recommend items similar to what user liked

Uses:
- Item features
- User profiles

Pros:
- Works with cold items
- Interpretable

Cons:
- Limited discovery
- Overspecialization

---

## 5.2 Collaborative Filtering

Idea:
- Users with similar behavior like similar items

Types:
- User-based CF
- Item-based CF

Pros:
- Strong personalization

Cons:
- Cold start
- Sparsity

---

## 5.3 Matrix Factorization

Core idea:
- Factorize user–item interaction matrix

Examples:
- SVD
- ALS
- Implicit MF

This is **representation learning**.

🔗 Related:
- [[Linear Algebra for Machine Learning — MOC]]
- [[Dimensionality Reduction — MOC]]

---

## 5.4 Factorization Machines

Extend MF by:
- Modeling feature interactions

Used when:
- User/item metadata exists

---

## 5.5 Deep Learning–Based Recommenders

Use neural networks to:
- Learn embeddings
- Model non-linear interactions
- Capture sequences

Examples:
- Neural CF
- Two-tower models
- Transformers for recommendation

🔗 Related:
- [[Neural Networks — MOC]]

---

## 5.6 Graph-Based Recommenders

Model interactions as graphs:
- User–item bipartite graphs
- Knowledge graphs

Capture:
- Higher-order relationships

---

## 6. Implicit vs Explicit Feedback

### Explicit
- Ratings
- Likes

### Implicit
- Clicks
- Views
- Purchases
- Dwell time

Implicit feedback is:
- Noisy
- Biased
- More common

🔗 Related:
- [[Cost-Sensitive Learning]]

---

## 7. Loss Functions in Recommendation

Common objectives:
- MSE (ratings)
- Binary cross entropy (clicks)
- Pairwise ranking loss (BPR)
- Softmax / sampled softmax

Loss choice defines **what “good recommendation” means**.

🔗 Related:
- [[Loss Functions — MOC]]

---

## 8. Evaluation of Recommender Systems

Offline metrics:
- Precision@K
- Recall@K
- MAP
- NDCG

Online metrics:
- CTR
- Conversion
- Watch time

Offline ≠ Online performance.

🔗 Related:
- [[Evaluation Metrics — MOC]]

---

## 9. Cold Start Problem

Occurs when:
- New users
- New items

Solutions:
- Content features
- Hybrid models
- Exploration strategies

---

## 10. Exploration vs Exploitation

Recommenders face a continuous trade-off:
- Exploit known preferences
- Explore new items

This connects directly to RL.

🔗 Related:
- [[Reinforcement Learning — MOC]]

---

## 11. Feedback Loops and Bias

Recommenders shape the data they learn from.

Risks:
- Popularity bias
- Filter bubbles
- Rich-get-richer effects

🔗 Related:
- [[Fairness in Machine Learning]]
- [[Bias–Variance Tradeoff]]

---

## 12. Context-Aware Recommendation

Recommendations depend on:
- Time
- Location
- Device
- Mood / intent

Adds another dimension to modeling.

---

## 13. Scalability and Systems Constraints

Production recommenders must handle:
- Millions of users/items
- Low latency
- Frequent retraining
- Distributed systems

Algorithm choice is often constrained by **engineering reality**.

---

## 14. Interpretability in Recommenders

Challenges:
- Embeddings are opaque
- Rankings are hard to explain

But explanations matter for:
- Trust
- Regulation
- User experience

🔗 Related:
- [[Model Interpretability]]

---

## 15. Common Failure Modes

- ❌ Optimizing offline metrics blindly  
- ❌ Ignoring feedback loops  
- ❌ No exploration strategy  
- ❌ Treating recommendation as static prediction  
- ❌ Ignoring fairness and diversity  

Recommenders fail at the **system level**, not model level.

---

## 16. How Recommender Systems Fit in ML

