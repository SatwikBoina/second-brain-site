# 📌 MOC — Graph Machine Learning (GML)

> Central hub for **Graph Machine Learning**.
> Graph ML focuses on learning from **entities (nodes) and their relationships (edges)**, where structure and connectivity carry critical information.

---

## 1. Core Idea

Graph Machine Learning operates on **graphs**:

\[
G = (V, E)
\]

Where:
- \(V\) = nodes (entities)
- \(E\) = edges (relationships)

Key idea:
> **Meaning is encoded not only in data points, but in how they are connected.**

---

## 2. Why Graph ML Is Needed

Traditional ML assumes:
- Independent rows
- Fixed feature vectors

Graphs violate this:
- Data points depend on neighbors
- Structure matters
- Influence propagates

Graph ML is essential when **relationships define behavior**.

---

## 3. Where Graph ML Appears in Practice

- Social networks (friends, followers)
- Recommendation systems (user–item graphs)
- Fraud detection (transaction networks)
- Knowledge graphs
- Biological networks
- Supply chains

Many “tabular” problems are secretly **graph problems**.

---

## 4. Types of Graphs

---

### 4.1 Directed vs Undirected

- Directed: follower → followee
- Undirected: friendship

---

### 4.2 Weighted vs Unweighted

- Weighted edges carry strength
- Unweighted indicate existence

---

### 4.3 Homogeneous vs Heterogeneous

- Homogeneous: one node type
- Heterogeneous: multiple node/edge types

---

### 4.4 Dynamic Graphs

- Nodes / edges evolve over time

🔗 Related:
- [[Time Series MOC]]

---

## 5. Core Graph ML Tasks

---

### 5.1 Node-Level Tasks

- Node classification
- Node regression

Examples:
- Fraudulent account detection
- User segmentation

---

### 5.2 Edge-Level Tasks

- Link prediction
- Edge classification

Examples:
- Friend recommendation
- Fraudulent transaction detection

---

### 5.3 Graph-Level Tasks

- Graph classification
- Graph regression

Examples:
- Molecule property prediction

---

## 6. Classical Graph Algorithms (Pre-ML)

Before learning, graphs were analyzed using:

- PageRank
- Shortest paths
- Centrality measures
- Community detection

These are still powerful **features**.

---

## 7. Feature Engineering for Graphs

Common graph features:
- Degree
- Centrality
- Clustering coefficient
- Neighborhood statistics

Graph ML often combines:
> **Graph features + ML models**

---

## 8. Graph Embeddings

Goal:
- Map nodes or graphs to vectors

Techniques:
- Random-walk based (e.g. node embeddings)
- Matrix factorization approaches

Embeddings enable:
- Distance-based learning
- Downstream ML tasks

🔗 Related:
- [[Dimensionality Reduction — MOC]]
- [[Linear Algebra for Machine Learning — MOC]]

---

## 9. Graph Neural Networks (GNNs)

Paradigm shift:
> Learn representations by **message passing** between neighbors.

General idea:
- Aggregate neighbor information
- Update node representations
- Stack multiple layers

This enables **structure-aware learning**.

🔗 Related:
- [[Neural Networks — MOC]]

---

## 10. Message Passing Intuition

Each node:
1. Receives messages from neighbors
2. Aggregates them
3. Updates its state

After \(k\) layers:
- Node “knows” about \(k\)-hop neighborhood

---

## 11. Loss Functions in Graph ML

Depends on task:
- Cross entropy (node classification)
- Ranking losses (link prediction)
- Regression losses (graph-level tasks)

🔗 Related:
- [[Loss Functions — MOC]]

---

## 12. Evaluation in Graph ML

Challenges:
- Data leakage via edges
- Temporal dependency
- Class imbalance

Metrics depend on task:
- Accuracy / F1 (node tasks)
- AUC / Precision@K (link prediction)

🔗 Related:
- [[Evaluation Metrics — MOC]]
- [[Data Leakage]]

---

## 13. Graph ML and Inductive Bias

Graphs introduce strong inductive bias:
- Locality
- Relational smoothness
- Homophily / heterophily

This helps fight the curse of dimensionality.

🔗 Related:
- [[Curse of Dimensionality]]

---

## 14. Graph ML vs Tabular ML

| Aspect | Tabular ML | Graph ML |
|---|---|---|
| Data assumption | IID | Dependent |
| Features | Explicit | Structural + learned |
| Leakage risk | Moderate | High |
| Complexity | Lower | Higher |

Graph ML is **harder but richer**.

---

## 15. Graph ML and Recommender Systems

Many recommenders are:
- Bipartite graphs
- Interaction networks

Graph ML provides:
- Better cold-start handling
- Richer representations

🔗 Related:
- [[Recommender Systems]]

---

## 16. Graph ML in Production

Challenges:
- Scalability
- Dynamic updates
- Latency
- Distributed training

Graph ML is often **system-heavy**.

🔗 Related:
- [[Deployment Basics]]

---

## 17. Common Failure Modes

- ❌ Ignoring graph leakage  
- ❌ Over-smoothing in deep GNNs  
- ❌ Treating graphs as static  
- ❌ Blindly applying GNNs  

Graph structure can **hurt** if misused.

---

## 18. How Graph ML Fits in ML

Entities + Relationships  
↓  
Graph Representation  
↓  
Graph ML Models ← this  
↓  
Predictions / Decisions


Graph ML is **learning with structure**.

---

## 19. Relationship to Other Concepts

Graph ML connects strongly to:

- [[Recommender Systems]]
- [[Neural Networks — MOC]]
- [[Dimensionality Reduction — MOC]]
- [[Optimization Methods — MOC]]
- [[Time Series MOC]]
- [[Experiment Tracking]]

---

## Usage Notes

- This MOC is a domain + structure hub
- Separate graph construction from modeling
- Always check leakage through edges
- Ask: *what relational signal is being exploited?*
