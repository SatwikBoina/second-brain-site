# 📌 MOC — Natural Language Processing (NLP)

> Central hub for **Natural Language Processing** in Machine Learning.
> NLP focuses on enabling machines to **understand, represent, and generate human language** in a way that is useful, scalable, and statistically grounded.

---

## 1. Core Idea

Natural Language Processing is about mapping:

$\text{Language (text, speech)} \rightarrow \text{Structure, Meaning, or Action}$


Language is:
- Discrete
- Ambiguous
- Contextual
- Hierarchical

Which makes NLP fundamentally different from tabular ML.

---

## 2. Why NLP Is Hard

Language introduces challenges not present in other ML domains:

- Ambiguity (same word, different meaning)
- Synonymy (different words, same meaning)
- Polysemy (one word, many meanings)
- Long-range dependencies
- Sparse, high-dimensional representations

NLP breaks many naïve ML assumptions.

---

## 3. NLP in the ML Landscape

NLP intersects multiple ML paradigms:

- Supervised learning (classification, tagging)
- Unsupervised learning (topic modeling, embeddings)
- Semi-supervised learning (pretraining + fine-tuning)
- Self-supervised learning (language modeling)
- Reinforcement learning (dialog, feedback-based tuning)

🔗 Related:
- [[Supervised Learning — MOC]]
- [[Unsupervised Learning — MOC]]
- [[Semi-Supervised Learning]]
- [[Reinforcement Learning — MOC]]

---

## 4. Levels of Language Representation

---

### 4.1 Character-Level

- Individual characters
- Useful for morphology, spelling, noisy text

---

### 4.2 Word-Level

- Tokens / words
- Traditional NLP foundation

Problems:
- Vocabulary explosion
- Out-of-vocabulary words

---

### 4.3 Subword-Level

- Byte Pair Encoding (BPE)
- WordPiece
- SentencePiece

Balances:
- Vocabulary size
- Generalization

---

### 4.4 Sentence / Document-Level

- Aggregated representations
- Used for classification, search, retrieval

---

## 5. Core NLP Tasks

---

### 5.1 Text Classification

Examples:
- Sentiment analysis
- Spam detection
- Topic labeling

🔗 Related:
- [[Classification — MOC]]

---

### 5.2 Sequence Labeling

Examples:
- POS tagging
- Named Entity Recognition
- Chunking

---

### 5.3 Language Modeling

Goal:
- Predict next token

Foundation of modern NLP.

---

### 5.4 Information Retrieval

Examples:
- Search
- Document ranking

🔗 Related:
- [[Recommender Systems]]

---

### 5.5 Text Generation

Examples:
- Summarization
- Translation
- Chatbots

---

## 6. Classical NLP Approaches

---

### 6.1 Rule-Based NLP

- Linguistic rules
- Grammars

Pros:
- Interpretable

Cons:
- Brittle
- Not scalable

---

### 6.2 Statistical NLP

- N-grams
- Hidden Markov Models
- CRFs

Relies on:
- Probability theory
- Feature engineering

🔗 Related:
- [[Probabilistic Models — MOC]]

---

### 6.3 Bag-of-Words & TF-IDF

- Sparse vector representations
- Strong baselines

Problems:
- Ignore word order
- Lose semantics

---

## 7. Representation Learning for NLP

---

### 7.1 Word Embeddings

- Word2Vec
- GloVe
- FastText

Idea:
> Words with similar meanings have similar vectors

🔗 Related:
- [[Linear Algebra for Machine Learning — MOC]]

---

### 7.2 Contextual Embeddings

- Context-dependent word meanings
- Same word → different vectors in different contexts

Foundation of modern NLP.

---

## 8. Deep Learning in NLP

Deep learning transformed NLP by enabling:

- Automatic feature learning
- Long-range dependency modeling
- End-to-end systems

Architectures:
- RNN / LSTM / GRU
- CNNs for text
- Transformers

🔗 Related:
- [[Neural Networks — MOC]]
- [[Optimization Methods — MOC]]

---

## 9. Transformers (Paradigm Shift)

Transformers introduced:
- Self-attention
- Parallel processing
- Global context modeling

They dominate:
- Language understanding
- Language generation

Transformers turned NLP into **representation learning at scale**.

---

## 10. Pretraining and Fine-Tuning

Modern NLP workflow:

1. Pretrain on massive unlabeled text
2. Fine-tune on task-specific data

This is **semi/self-supervised learning** in practice.

🔗 Related:
- [[Semi-Supervised Learning]]

---

## 11. Loss Functions in NLP

Common objectives:
- Cross entropy (language modeling)
- Token-level losses
- Sequence-level losses

Loss design affects:
- Fluency
- Diversity
- Faithfulness

🔗 Related:
- [[Loss Functions — MOC]]

---

## 12. Evaluation in NLP

Evaluation is difficult due to:
- Subjectivity
- Multiple valid outputs

Metrics:
- Accuracy / F1 (classification)
- BLEU / ROUGE (generation)
- Perplexity (language modeling)

🔗 Related:
- [[Evaluation Metrics — MOC]]

---

## 13. Error Analysis in NLP

Key questions:
- Are errors linguistic or semantic?
- Are errors due to context length?
- Are errors domain-specific?

Manual inspection is critical.

🔗 Related:
- [[Error Analysis]]

---

## 14. NLP and the Curse of Dimensionality

Text data:
- Extremely high dimensional
- Sparse
- Noisy

NLP relies heavily on:
- Embeddings
- Dimensionality reduction
- Regularization

🔗 Related:
- [[Curse of Dimensionality]]
- [[Dimensionality Reduction — MOC]]

---

## 15. NLP in Production

Challenges:
- Latency
- Memory usage
- Model size
- Data drift
- Bias and toxicity

NLP systems must be **monitored carefully**.

🔗 Related:
- [[Deployment Basics]]

---

## 16. Ethics and Fairness in NLP

Language models can:
- Amplify bias
- Hallucinate facts
- Produce harmful content

Fairness and safety are first-class concerns.

🔗 Related:
- [[Fairness in Machine Learning]]

---

## 17. How NLP Fits in ML

