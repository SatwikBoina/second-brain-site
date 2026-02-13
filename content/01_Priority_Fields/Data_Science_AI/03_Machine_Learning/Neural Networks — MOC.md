# 📌 MOC — Neural Networks

> Central hub for **Neural Networks** in Machine Learning.
> Neural networks are function approximators that learn **hierarchical representations** through layers of linear transformations and non-linear activations.

---

## 1. Core Idea

A neural network learns a mapping:
$X \rightarrow Y$


by:
- Composing linear transformations
- Applying non-linear activation functions
- Optimizing a loss function via gradient-based methods

Key idea:
> **Depth enables representation learning**, not just prediction.

---

## 2. Why Neural Networks Matter

Neural networks excel at:
- Learning complex non-linear relationships
- Automatic feature learning
- High-dimensional data (images, text, audio)

They shift effort from **feature engineering → architecture design**.

---

## 3. Neural Networks as Function Approximators

Neural networks:
- Approximate arbitrary functions (Universal Approximation Theorem)
- Learn representations rather than rules
- Are highly expressive but sensitive to design choices

🔗 Related:
- [[Model Complexity]]
- [[Bias–Variance Tradeoff]]

---

## 4. Core Components of Neural Networks

---

### 4.1 Layers

- Input layer
- Hidden layers
- Output layer

Types:
- Fully connected (Dense)
- Convolutional
- Recurrent
- Attention-based

---

### 4.2 Weights and Biases

- Parameters learned during training
- Control the shape of the learned function

---

### 4.3 Activation Functions

Introduce non-linearity.

Common activations:
- ReLU
- Sigmoid
- Tanh
- Softmax
- GELU

🔗 Related:
- [[Activation Functions]]

---

### 4.4 Loss Functions

Define training objective.

Examples:
- MSE
- Cross Entropy
- Custom losses

🔗 Related:
- [[Regression Loss Functions — MOC]]
- [[Classification Loss Functions — MOC]]
- [[Custom Loss Functions]]

---

### 4.5 Optimization Algorithms

Update weights to minimize loss.

Examples:
- Gradient Descent
- SGD
- Adam
- RMSProp

🔗 Related:
- [[Gradient Descent]]
- [[Optimization Algorithms]]

---

## 5. Training Neural Networks

Training involves:
1. Forward pass
2. Loss computation
3. Backpropagation
4. Parameter update

This loop repeats until convergence.

🔗 Related:
- [[Backpropagation]]

---

## 6. Regularization in Neural Networks

Neural networks are **high-capacity models** and prone to overfitting.

Common regularization techniques:
- L1 / L2 regularization
- Dropout
- Early stopping
- Data augmentation
- Batch normalization

🔗 Related:
- [[Regularization — MOC]]
- [[Early Stopping]]

---

## 7. Neural Networks and Loss Landscapes

Neural network optimization involves:
- Non-convex loss surfaces
- Multiple local minima
- Flat vs sharp minima

Modern optimizers help navigate this space.

🔗 Related:
- [[Loss Landscape]]

---

## 8. Types of Neural Networks

---

### 8.1 Feedforward Neural Networks

- [[Multilayer Perceptron]]

Used for tabular data and basic tasks.

---

### 8.2 Convolutional Neural Networks (CNNs)

- [[Convolutional Neural Networks]]

Used for:
- Images
- Spatial data

---

### 8.3 Recurrent Neural Networks (RNNs)

- [[Recurrent Neural Networks]]
- [[LSTM]]
- [[GRU]]

Used for:
- Sequences
- Time series

---

### 8.4 Transformer-Based Models

- [[Transformers]]
- [[Attention Mechanism]]

Used for:
- NLP
- Vision
- Multimodal tasks

---

## 9. Neural Networks as Probabilistic Models

Many neural networks output probabilities:
- Softmax classifiers
- Bayesian neural networks

🔗 Related:
- [[Probabilistic Models — MOC]]
- [[Probability Calibration]]

---

## 10. Hyperparameters in Neural Networks

Highly sensitive hyperparameters include:
- Learning rate
- Network depth
- Batch size
- Weight initialization
- Optimizer choice

🔗 Related:
- [[Hyperparameter Sensitivity]]
- [[Bayesian Optimization]]

---

## 11. Interpretability and Neural Networks

Neural networks are often **black-box models**.

Interpretability techniques:
- Feature importance
- Saliency maps
- SHAP
- LIME

🔗 Related:
- [[Model Interpretability]]

---

## 12. Neural Networks and Data Requirements

Neural networks typically require:
- Large datasets
- Good feature scaling
- Clean labels

They perform poorly with:
- Small data
- High noise
- Poorly engineered targets

---

## 13. Neural Networks vs Classical ML

| Aspect | Neural Networks | Classical ML |
|-----|----------------|--------------|
| Feature engineering | Low | High |
| Data requirement | High | Medium |
| Interpretability | Low | High |
| Expressiveness | Very High | Medium |

---

## 14. Common Misconceptions

- ❌ Neural networks always outperform classical models  
- ❌ More layers always mean better performance  
- ❌ Neural networks don’t overfit  
- ❌ They don’t need preprocessing  

Neural networks amplify **both power and mistakes**.

---

## 15. Why Neural Networks Matter

Neural networks explain:
- Why deep learning works
- Why feature learning beats manual features
- Why optimization matters as much as architecture
- Why modern ML scales with data

They are the **foundation of modern AI systems**.

---

## Usage Rules

- This MOC is a conceptual hub
- Each architecture has its own note
- Avoid implementation details here
- Algorithms and techniques should backlink to this MOC
