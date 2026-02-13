---
type: algorithm
domain: machine-learning
category: unsupervised-learning
model_family: pattern-mining
supervision: unsupervised
primary_use: association_rule_mining
status: evergreen
---

# Apriori Algorithm

> Apriori is a classic **frequent itemset mining algorithm** used to discover **association rules** in transactional datasets.

---

## 1. One-Line Intuition

> If an itemset is frequent, then all of its subsets must also be frequent.

This simple idea enables massive pruning.

---

## 2. Problem Setting

Given:
- A dataset of transactions
- Each transaction contains a set of items

Goal:
1. Find frequently occurring itemsets
2. Generate association rules from them

Example:

Transaction data:

| Transaction | Items |
|-------------|--------|
| T1 | {Milk, Bread} |
| T2 | {Milk, Diapers} |
| T3 | {Bread, Diapers} |
| T4 | {Milk, Bread, Diapers} |

We want patterns like:

- {Milk → Bread}
- {Bread → Diapers}

---

## 3. Key Concepts

---

### 3.1 Support

Frequency of an itemset:

\[
Support(A) = \frac{\text{Transactions containing A}}{\text{Total transactions}}
\]

---

### 3.2 Confidence

Conditional probability:

\[
Confidence(A \rightarrow B) = \frac{Support(A \cup B)}{Support(A)}
\]

---

### 3.3 Lift

Measures independence:

\[
Lift(A \rightarrow B) = \frac{Support(A \cup B)}{Support(A) \cdot Support(B)}
\]

Lift > 1 → positive association.

🔗 Related:
- [[Probability Theory]]
- [[Evaluation Metrics — MOC]]

---

## 4. Core Idea of Apriori

Apriori uses:

> Downward Closure Property (Apriori Property)

If:
- An itemset is frequent

Then:
- All its subsets must also be frequent.

Conversely:
- If a subset is infrequent,
- Supersets cannot be frequent.

This allows aggressive pruning.

---

## 5. Algorithm Steps

---

### Step 1: Find Frequent 1-Itemsets

- Count frequency of each item
- Keep those above minimum support

---

### Step 2: Generate Candidate k-Itemsets

- Join frequent (k-1)-itemsets
- Prune those whose subsets are infrequent

---

### Step 3: Count Support

- Scan dataset
- Keep only those above minimum support

Repeat until:
- No more frequent itemsets found

---

### Step 4: Generate Association Rules

For each frequent itemset:
- Generate all possible rules
- Filter by minimum confidence

---

## 6. Example Intuition

If:
- {Milk, Bread} is frequent
- {Milk, Diapers} is frequent

Then:
- {Milk, Bread, Diapers} is a candidate

But if:
- {Bread, Diapers} is infrequent

Then:
- {Milk, Bread, Diapers} cannot be frequent

Huge search space reduction.

---

## 7. Computational Complexity

The search space is:

\[
2^n
\]

Where:
- n = number of unique items

Apriori reduces this via pruning,
but it can still be expensive for large datasets.

---

## 8. Strengths

- Simple and interpretable
- Effective pruning
- Easy to implement
- Generates human-readable rules

---

## 9. Weaknesses

- Multiple dataset scans
- Poor scalability with large itemsets
- Explosion in candidate generation
- Not suited for dense datasets

---

## 10. Apriori vs FP-Growth

| Aspect | Apriori | FP-Growth |
|---------|----------|-------------|
| Candidate generation | Yes | No |
| Dataset scans | Many | Few |
| Speed | Slower | Faster |
| Memory | Moderate | Higher (tree structure) |

FP-Growth is generally preferred in practice.

---

## 11. Apriori vs Supervised Learning

Apriori:
- No labels
- No prediction
- Pattern discovery

Supervised learning:
- Uses labels
- Optimizes loss
- Predicts outcomes

Apriori is **descriptive**, not predictive.

---

## 12. Applications

- Market basket analysis
- Recommendation heuristics
- Cross-selling
- Fraud pattern discovery
- Web clickstream analysis

🔗 Related:
- [[Recommender Systems]]
- [[Graph Machine Learning]]

---

## 13. Failure Modes

- ❌ Very low minimum support → explosion
- ❌ Very high support → no patterns
- ❌ Rare but important rules ignored
- ❌ Spurious correlations

Association ≠ causation.

---

## 14. When Apriori Works Well

- Small to medium transactional datasets
- Sparse transactions
- Need interpretable rules
- Business insight discovery

---

## 15. When Apriori Is a Bad Idea

- Very large datasets
- Real-time systems
- Continuous features
- Dense data

---

## 16. Relationship to Other Concepts

Apriori connects strongly to:

- [[Unsupervised Learning — MOC]]
- [[Recommender Systems]]
- [[Graph Machine Learning]]
- [[Probability Theory]]
- [[Evaluation Metrics — MOC]]

---

## 17. Why Apriori Matters

Apriori teaches:

- How combinatorial search works
- How pruning reduces complexity
- Why frequency matters in pattern mining
- Difference between descriptive and predictive ML

It is foundational to **data mining**.
