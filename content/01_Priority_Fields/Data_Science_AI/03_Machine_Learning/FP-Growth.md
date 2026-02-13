---
type: algorithm
domain: machine-learning
category: unsupervised-learning
model_family: pattern-mining
supervision: unsupervised
primary_use: frequent_itemset_mining
status: evergreen
---

# FP-Growth (Frequent Pattern Growth)

> FP-Growth is an efficient algorithm for mining frequent itemsets without explicit candidate generation, using a compact data structure called the FP-Tree.

---

## 1. One-Line Intuition

> Instead of generating all possible item combinations like Apriori, FP-Growth compresses the dataset into a tree and mines patterns directly from it.

---

## 2. Why FP-Growth Exists

Apriori:
- Generates massive candidate sets
- Requires multiple database scans
- Becomes slow for large datasets

FP-Growth:
- Avoids candidate generation
- Scans database only twice
- Uses pattern compression

🔗 Related:
- [[Apriori Algorithm]]

---

## 3. Problem Setting

Given:
- A transactional dataset
- Minimum support threshold

Goal:
- Discover all frequent itemsets

Example:
Transactions:

T1: {Milk, Bread}  
T2: {Milk, Diapers}  
T3: {Bread, Diapers}  
T4: {Milk, Bread, Diapers}

---

## 4. Core Idea

FP-Growth uses:

1. **Compression** (FP-Tree)
2. **Divide and conquer mining**

It avoids brute-force combination generation.

---

## 5. Step 1 — First Database Scan

- Count frequency of each item
- Remove infrequent items
- Sort frequent items by descending support

This ensures:
- Frequent items are near the root
- Better compression

---

## 6. Step 2 — Build FP-Tree

For each transaction:

1. Remove infrequent items
2. Sort remaining items by global frequency
3. Insert into tree structure

The FP-Tree:
- Shares common prefixes
- Compresses dataset
- Stores counts

Result:
A compact representation of all transactions.

---

## 7. Step 3 — Mining Frequent Patterns

Mining works recursively:

For each item (from least frequent upward):

1. Extract conditional pattern base
2. Build conditional FP-Tree
3. Recursively mine new patterns

This is a divide-and-conquer process.

---

## 8. Why It’s Faster Than Apriori

Apriori:
- Generates candidate sets
- Multiple dataset scans
- Expensive combinatorics

FP-Growth:
- No candidate generation
- Only two dataset scans
- Exploits prefix compression

It shifts cost from:
- Combination generation
to
- Tree traversal

---

## 9. FP-Tree Structure

An FP-Tree contains:

- Root node (null)
- Branches representing transactions
- Node counts
- Header table linking identical items

Header table enables:
- Efficient traversal of item occurrences

---

## 10. FP-Growth vs Apriori

| Aspect | Apriori | FP-Growth |
|---------|----------|------------|
| Candidate generation | Yes | No |
| Database scans | Many | Two |
| Speed | Slower | Faster |
| Memory usage | Lower | Higher |
| Suitable for large data | Limited | Better |

FP-Growth dominates in practice.

---

## 11. Strengths

- Efficient
- Scalable
- No combinatorial explosion
- Fewer dataset scans
- Handles large itemsets better

---

## 12. Weaknesses

- Tree can grow large in dense datasets
- Harder to understand than Apriori
- Requires memory for tree structure
- Less intuitive debugging

---

## 13. Failure Modes

- ❌ Very dense datasets → large tree
- ❌ Very low minimum support → explosion
- ❌ Rare but important patterns missed
- ❌ Highly uniform distributions

Support threshold remains critical.

---

## 14. Applications

- Market basket analysis
- Retail analytics
- Web clickstream mining
- Recommendation heuristics
- Fraud detection pattern discovery

🔗 Related:
- [[Recommender Systems]]
- [[Graph Machine Learning]]

---

## 15. FP-Growth and Association Rules

After finding frequent itemsets:
- Generate rules
- Evaluate using:
  - Support
  - Confidence
  - Lift

🔗 Related:
- [[Apriori Algorithm]]
- [[Probability Theory]]

---

## 16. FP-Growth vs Supervised ML

FP-Growth:
- Descriptive
- Finds co-occurrence patterns
- No prediction

Supervised ML:
- Predictive
- Optimizes loss
- Uses labels

FP-Growth is about:
> Discovering structure, not predicting outcomes.

---

## 17. Computational Perspective

FP-Growth trades:

- Combinatorial explosion
for
- Tree-based compression and recursion

It demonstrates:
> How data structures can dramatically change algorithm complexity.

---

## 18. Relationship to Other Concepts

FP-Growth connects to:

- [[Apriori Algorithm]]
- [[Unsupervised Learning — MOC]]
- [[Recommender Systems]]
- [[Graph Machine Learning]]
- [[Probability Theory]]

---

## 19. Why FP-Growth Matters

FP-Growth teaches:

- Efficient pattern mining
- Prefix-tree compression
- Divide-and-conquer mining
- How algorithm design beats brute force

It is foundational to modern data mining systems.
