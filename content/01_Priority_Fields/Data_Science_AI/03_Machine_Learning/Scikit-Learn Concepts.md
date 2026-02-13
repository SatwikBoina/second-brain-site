# 📌 MOC — Scikit-Learn Concepts

> Central hub for **core concepts and design principles of Scikit-Learn**.
> Scikit-learn provides a **consistent, modular, and composable framework** for classical machine learning in Python.

---

## 1. Core Philosophy of Scikit-Learn

Scikit-learn is built on a few strong principles:

- Consistency of API
- Explicit over implicit
- Composition over inheritance
- Separation of concerns
- Fit once, reuse everywhere

Understanding sklearn is about understanding **patterns**, not memorizing classes.

---

## 2. The Estimator Abstraction (Most Important Concept)

Everything in sklearn is an **Estimator**.

An estimator is any object that:
- Learns from data using `.fit()`

Examples:
- Models
- Transformers
- Pipelines

This single abstraction enables the entire ecosystem.

---

## 3. Types of Estimators

---

### 3.1 Predictors (Models)

Purpose:
- Learn a mapping from X → y

Common methods:
- `.fit(X, y)`
- `.predict(X)`
- `.predict_proba(X)`
- `.decision_function(X)`

Used for:
- Regression
- Classification
- Clustering

---

### 3.2 Transformers

Purpose:
- Transform data
- Do NOT predict targets

Common methods:
- `.fit(X)`
- `.transform(X)`
- `.fit_transform(X)`

Examples:
- Scalers
- Encoders
- Imputers
- Dimensionality reduction

---

### 3.3 Meta-Estimators

Purpose:
- Wrap other estimators

Examples:
- Pipelines
- GridSearchCV
- RandomizedSearchCV
- Ensembles

Meta-estimators orchestrate learning.

---

## 4. Fit–Transform–Predict Lifecycle

Canonical sklearn flow:

1. `fit()` → learn parameters
2. `transform()` → apply transformation
3. `predict()` → make predictions

This enforces **train–test separation** by design.

---

## 5. Pipeline (Production-Critical Concept)

Pipelines chain estimators:

Raw Data  
↓  
Transformer  
↓  
Transformer  
↓  
Model


Benefits:
- Prevents data leakage
- Enables reproducibility
- Simplifies tuning
- Makes workflows portable

Pipelines are **mandatory for serious ML**.

---

## 6. Feature Engineering as First-Class Citizen

In sklearn:
- Feature engineering is explicit
- Transformations are objects
- Everything is composable

Common feature tools:
- Scaling
- Encoding
- Imputation
- Polynomial features

---

## 7. Train–Test Split and Validation

Scikit-learn enforces good evaluation habits:

- Explicit train–test split
- Cross-validation utilities
- Stratified splitting
- Time-aware splitting

Evaluation is **opt-in and explicit**, not hidden.

---

## 8. Cross-Validation as an API

Cross-validation is treated as:
- A reusable strategy
- A pluggable component

CV controls:
- How data is split
- How models are evaluated
- How tuning is done

---

## 9. Hyperparameter Tuning in Sklearn

Tuning is external to models.

Key ideas:
- Models stay simple
- Search strategies live outside
- Validation strategy is explicit

Search objects are estimators themselves.

---

## 10. Scoring vs Loss

Important distinction in sklearn:

- Loss → optimized internally (often hidden)
- Scoring → used for evaluation and selection

You can:
- Choose scoring metric
- Define custom scorers

---

## 11. Stateless vs Stateful Objects

After `.fit()`:
- Estimators become stateful
- Learned attributes end with `_`

Examples:
- `coef_`
- `feature_importances_`
- `mean_`

This naming convention is intentional.

---

## 12. Reproducibility and Random State

Many algorithms involve randomness.

Scikit-learn:
- Exposes `random_state`
- Makes randomness explicit
- Enables reproducibility

No hidden global randomness.

---

## 13. Model Inspection and Introspection

Sklearn allows:
- Coefficient inspection
- Feature importance access
- Decision function access

Encourages **understanding models**, not blind usage.

---

## 14. Scikit-Learn and Bias–Variance

Design encourages:
- Starting simple
- Adding complexity gradually
- Evaluating properly

Defaults favor **robustness over cleverness**.

---

## 15. What Scikit-Learn Is NOT

Scikit-learn is not:
- Deep learning framework
- AutoML system
- Online learning system
- Big data engine

It excels at:
- Classical ML
- Medium-scale data
- Research → production bridge

---

## 16. Common Beginner Mistakes

- ❌ Fitting transformers on full data  
- ❌ No pipelines  
- ❌ Tuning on test set  
- ❌ Ignoring cross-validation  
- ❌ Treating sklearn as a black box  

Sklearn rewards **discipline**.

---

## 17. How Scikit-Learn Fits in ML

Data  
↓  
Preprocessing (Transformers)  
↓  
Model (Estimator)  
↓  
Evaluation  
↓  
Selection / Deployment


Scikit-learn operationalizes **the ML lifecycle**.

---

## 18. Why Scikit-Learn Concepts Matter

Understanding sklearn concepts means:
- You understand classical ML workflows
- You avoid data leakage
- You write reproducible ML
- You can explain your work clearly
- You transition easily to production systems

Scikit-learn teaches **how ML should be done**.

---

## Usage Rules

- This MOC is conceptual, not an API list
- Algorithms live in separate notes
- Always prefer pipelines
- Treat validation as part of the model
