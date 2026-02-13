---
type: concept
domain: machine-learning
category: interpretability
status: evergreen
---

# Model Interpretability

> Model interpretability is the ability to **understand, explain, and trust** a model’s predictions by relating them to input features and decision logic.

---

## 1. Core Idea

A model is interpretable if humans can answer:

- Why did the model make this prediction?
- Which features mattered most?
- How would the prediction change if inputs changed?

Interpretability is about **understanding behavior**, not just accuracy.

---

## 2. Why Model Interpretability Matters

Interpretability is critical for:

- Trust and adoption
- Debugging models
- Regulatory compliance
- Fairness and bias detection
- Business decision-making

High accuracy without understanding is often **unusable**.

---

## 3. Interpretability vs Explainability

Important distinction:

- **Interpretability** → model is inherently understandable  
- **Explainability** → explanations are added post hoc  

A linear model is interpretable.  
SHAP explanations make a complex model explainable.

---

## 4. Types of Interpretability

---

### 4.1 Global Interpretability

Understanding **overall model behavior**.

Questions answered:
- Which features matter most?
- How does the model generally behave?

Examples:
- Feature importance
- Coefficient values
- Partial dependence plots

---

### 4.2 Local Interpretability

Understanding **individual predictions**.

Questions answered:
- Why this prediction for this instance?
- What features pushed it up or down?

Examples:
- SHAP values
- LIME explanations

---

## 5. Intrinsically Interpretable Models

Models that are understandable by design:

- Linear Regression
- Logistic Regression
- Decision Trees (shallow)
- Rule-based models

🔗 Related:
- [[Linear Models — MOC]]
- [[Decision Tree Classifier]]

---

## 6. Black-Box Models

Models that are hard to interpret directly:

- Random Forest
- Gradient Boosting
- XGBoost / LightGBM / CatBoost
- Neural Networks
- SVM with kernels

These require **post-hoc explanations**.

---

## 7. Post-hoc Interpretability Techniques

---

### 7.1 Feature Importance

- Global importance ranking
- Often model-specific

Limitations:
- Can be misleading with correlated features

---

### 7.2 SHAP (Shapley Values)

- Game-theoretic explanations
- Local + global interpretability
- Consistent and additive

🔗 Related:
- [[SHAP Values]]

---

### 7.3 LIME

- Local surrogate models
- Explains one prediction at a time

🔗 Related:
- [[LIME]]

---

### 7.4 Partial Dependence & ICE

- Shows effect of one feature on predictions
- Assumes feature independence

🔗 Related:
- [[Partial Dependence Plot]]

---

## 8. Interpretability and Feature Engineering

Interpretability improves when:
- Features are meaningful
- Encodings are understandable
- Interactions are intentional

Poor features → misleading explanations.

🔗 Related:
- [[Feature Engineering]]
- [[Interaction Terms]]

---

## 9. Interpretability vs Performance Trade-off

Often there is a trade-off:

| Model Type | Accuracy | Interpretability |
|----------|----------|------------------|
| Linear Model | Medium | High |
| Tree | Medium–High | Medium |
| Boosting | High | Low |
| Neural Network | Very High | Very Low |

The right balance depends on **use case**, not ego.

---

## 10. Interpretability and Bias / Fairness

Interpretability helps:
- Detect biased features
- Identify proxy variables
- Explain unfair outcomes

Opaque models hide bias; interpretable models expose it.

🔗 Related:
- [[Bias]]
- [[Fairness in ML]]

---

## 11. Interpretability and Regulation

In regulated domains (finance, healthcare):

- Explanations may be legally required
- Black-box models may be restricted

Interpretability becomes **non-negotiable**.

---

## 12. Common Misconceptions

- ❌ Interpretability means simpler models always win  
- ❌ Feature importance equals causality  
- ❌ SHAP explanations are always correct  
- ❌ One explanation fits all audiences  

Interpretability is **context-dependent**.

---

## 13. When to Prioritize Interpretability

- High-stakes decisions
- Human-in-the-loop systems
- Regulated environments
- Model debugging and monitoring

---

## 14. When Interpretability Matters Less

- Low-risk predictions
- Fully automated systems
- Pure ranking or recommendation tasks

Even then, *some* understanding is useful.

---

## 15. Why Model Interpretability Matters

Model interpretability explains:

- Why models succeed or fail
- Why stakeholders trust predictions
- Why fairness and compliance are possible
- Why ML systems can be responsibly deployed

It is the **bridge between models and humans**.

---

## Usage Notes

- Link this note from:
  - Model Selection
  - Feature Engineering
  - SHAP / LIME
  - Ethics & Fairness
- Do NOT confuse interpretability with causality
