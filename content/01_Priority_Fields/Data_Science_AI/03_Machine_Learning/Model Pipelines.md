---
type: concept
domain: machine-learning
category: workflow
status: evergreen
---

# Model Pipelines

> A model pipeline is an **ordered, reproducible sequence of data transformations and modeling steps** that converts raw input data into predictions in a safe, consistent, and reusable way.

---

## 1. Core Idea

A pipeline enforces the rule:

> **The same transformations applied during training must be applied during inference — in the same order.**

Pipelines turn ML from:
- Ad-hoc scripts ❌  
into
- Deterministic systems ✅

---

## 2. Why Model Pipelines Matter

Without pipelines:
- Data leakage happens silently
- Experiments are irreproducible
- Deployment breaks
- Results cannot be trusted

With pipelines:
- Preprocessing is correct by construction
- Training and inference stay aligned
- Hyperparameter tuning becomes safe
- ML becomes engineering

---

## 3. What a Pipeline Contains

A typical pipeline includes:

1. Data preprocessing  
2. Feature engineering  
3. Dimensionality reduction (optional)  
4. Model  
5. Post-processing (optional)

All steps are **learned and applied together**.

---

## 4. Pipeline vs Ad-Hoc Workflow

| Aspect | Ad-Hoc ML | Pipeline-Based ML |
|---|---|---|
| Preprocessing | Manual | Encapsulated |
| Leakage risk | High | Low |
| Reproducibility | Poor | Strong |
| Tuning | Fragile | Safe |
| Deployment | Painful | Straightforward |

Pipelines are not optional for serious ML.

---

## 5. Pipelines in Scikit-Learn

Scikit-learn pipelines are:

- Estimators themselves
- Fully compatible with CV and tuning
- Serializable
- Composable

Every step must implement:
- `fit`
- `transform` (except final model)

🔗 Related:
- [[Scikit-Learn Concepts]]

---

## 6. Fit–Transform Discipline (Critical)

Pipeline behavior during training:

1. `fit` is called **only on training data**
2. Each transformer learns parameters
3. Transformations are frozen
4. Model is trained on transformed data

During inference:
- Only `transform` + `predict` are used

This enforces **temporal correctness**.

---

## 7. Pipelines and Data Leakage

Pipelines prevent common leakage sources:

- Scaling using full dataset ❌
- Encoding categories using test data ❌
- Imputation using global statistics ❌

Because:
> Transformers are fit **inside cross-validation folds**.

🔗 Related:
- [[Data Leakage]]
- [[Cross Validation]]

---

## 8. Pipelines and Hyperparameter Tuning

Pipelines allow tuning of:
- Model hyperparameters
- Preprocessing hyperparameters
- Feature engineering choices

All within **one validation loop**.

🔗 Related:
- [[Hyperparameter Tuning — MOC]]
- [[Model Selection]]

---

## 9. Pipelines and Feature Engineering

Feature engineering becomes:
- Explicit
- Modular
- Reusable
- Testable

Instead of notebooks full of hidden logic.

🔗 Related:
- [[Feature Engineering]]
- [[Feature Scaling]]
- [[Feature Encoding]]

---

## 10. Pipelines and Model Comparison

Using pipelines ensures:
- Fair comparison between models
- Identical preprocessing
- Comparable metrics

Without pipelines, comparisons are invalid.

---

## 11. Pipelines in Time Series (Special Case)

Time series pipelines must respect:
- Temporal order
- Rolling features
- Expanding windows

Pipelines still help, but **splitting strategy matters**.

🔗 Related:
- [[Time Series MOC]]

---

## 12. Pipelines and Production

A pipeline is a **deployable artifact**:

- One object
- One version
- One contract

Production systems prefer:
- One pipeline > many scripts

---

## 13. Common Pipeline Patterns

---

### 13.1 Simple Pipeline
- Scaling → Model

---

### 13.2 Feature Pipeline
- Imputation → Encoding → Scaling → Model

---

### 13.3 Hybrid Pipeline
- Numeric pipeline
- Categorical pipeline
- Combined → Model

---

## 14. Common Mistakes

- ❌ Fitting transformers outside pipeline  
- ❌ Manual preprocessing before CV  
- ❌ Mixing train and test logic  
- ❌ Using pipelines only at the end  
- ❌ Treating pipelines as “sklearn boilerplate”  

Pipelines are **core logic**, not syntax.

---

## 15. Pipelines and Bias–Variance

Pipelines affect:
- Variance (through leakage control)
- Bias (through preprocessing choices)

Preprocessing is part of the model.

🔗 Related:
- [[Bias–Variance Tradeoff]]

---

## 16. Pipelines and Interpretability

Interpretability must consider:
- Feature transformations
- Encodings
- Interactions

Pipelines make interpretation traceable.

🔗 Related:
- [[Model Interpretability]]

---

## 17. How Pipelines Fit in ML

Raw Data  
↓  
Pipeline (fit once)  
↓  
Transformed Data + Model  
↓  
Predictions


Pipelines define the **unit of ML work**.

---

## 18. Why Model Pipelines Matter

Model pipelines explain:

- Why ML results are trustworthy
- Why experiments are reproducible
- Why tuning works correctly
- Why deployment is possible

They are the **difference between ML code and ML systems**.

---

## Usage Notes

- Link this note from:
  - Scikit-Learn Concepts
  - Model Selection
  - Hyperparameter Tuning — MOC
  - Data Leakage
- Treat pipelines as mandatory infrastructure, not optional abstraction
