---
type: concept
domain: machine-learning
category: production
status: evergreen
---

# Deployment Basics (Machine Learning)

> Deployment is the process of **making a trained machine learning model available for real-world use**, where it must be reliable, scalable, observable, and aligned with business constraints.

---

## 1. Core Idea

Training a model answers:
> *Can we learn?*

Deployment answers:
> *Can this model safely and reliably make decisions in the real world?*

Most ML effort fails **after** training, not before.

---

## 2. What Deployment Really Means

Deployment is NOT:
- Uploading a pickle file
- Writing a Flask API
- Getting a prediction once

Deployment IS:
- Serving predictions repeatedly
- Under changing data
- Under latency constraints
- With monitoring and rollback

---

## 3. Offline Model vs Deployed Model

| Aspect | Offline Model | Deployed Model |
|---|---|---|
| Data | Static | Streaming / live |
| Environment | Notebook | Production system |
| Errors | Acceptable | Costly |
| Metrics | Offline | Online |
| Lifetime | One-time | Continuous |

A deployed model is a **living system**.

---

## 4. Basic Deployment Architecture

At a high level:

Input Data  
↓  
Preprocessing  
↓  
Model  
↓  
Post-processing  
↓  
Prediction / Decision


This entire flow must be:
- Versioned
- Testable
- Reproducible

🔗 Related:
- [[Model Pipelines]]

---

## 5. Batch vs Online Deployment

---

### 5.1 Batch Deployment

- Predictions generated periodically
- Used for:
  - Reports
  - Forecasts
  - Recommendations

Pros:
- Simple
- Stable

Cons:
- Not real-time

---

### 5.2 Online (Real-Time) Deployment

- Predictions served on request
- Used for:
  - Fraud detection
  - Recommendations
  - Personalization

Pros:
- Immediate decisions

Cons:
- Latency-sensitive
- More failure modes

---

## 6. Inputs and Outputs (Contracts)

Deployed models require **strict contracts**:

- Input schema
- Feature definitions
- Output format
- Value ranges

Breaking contracts breaks systems.

🔗 Related:
- [[Feature Engineering]]
- [[Model Pipelines]]

---

## 7. Model Artifacts

A deployable model includes:

- Trained model
- Preprocessing logic
- Metadata
- Version information

Never deploy a model without its preprocessing.

---

## 8. Versioning (Non-Negotiable)

You must version:
- Model
- Data
- Features
- Code

So you can:
- Roll back
- Debug
- Compare
- Audit

🔗 Related:
- [[Experiment Tracking]]

---

## 9. Evaluation in Production

Offline metrics ≠ Online performance.

In production, monitor:
- Prediction distribution
- Business KPIs
- Error rates
- Latency

🔗 Related:
- [[Evaluation Metrics — MOC]]

---

## 10. Monitoring Basics

At minimum, monitor:

- Input data drift
- Output drift
- Prediction volume
- Failures / timeouts

Silence is not success.

---

## 11. Data Drift and Concept Drift

Production data changes.

Causes:
- User behavior changes
- Seasonality
- Market shifts

Unmonitored drift = silent model death.

🔗 Related:
- [[Concept Drift]]
- [[Time Series MOC]]

---

## 12. Retraining Strategy

Key questions:
- When to retrain?
- With what data?
- With which validation?

Retraining is a **policy**, not an afterthought.

---

## 13. Failure Modes in Deployment

Common failures:
- ❌ Training–serving skew  
- ❌ Data leakage assumptions breaking  
- ❌ Unhandled edge cases  
- ❌ Latency spikes  
- ❌ Silent degradation  

Production ML fails *quietly*.

---

## 14. Interpretability and Debugging

In production you must be able to:
- Explain predictions
- Debug wrong outputs
- Justify decisions

Black boxes without observability are dangerous.

🔗 Related:
- [[Model Interpretability]]
- [[Error Analysis]]

---

## 15. Deployment and Fairness

Bias can emerge after deployment due to:
- Feedback loops
- Uneven exposure
- Distribution shifts

Fairness must be monitored continuously.

🔗 Related:
- [[Fairness in Machine Learning]]

---

## 16. Deployment Is a System Problem

Deployment involves:
- ML
- Software engineering
- Infrastructure
- Monitoring
- Product decisions

A good model can fail in a bad system.

---

## 17. How Deployment Fits in ML Lifecycle

Data  
↓  
Training  
↓  
Evaluation  
↓  
Deployment ← this  
↓  
Monitoring  
↓  
Retraining

Deployment closes the loop.

---

## 18. Common Misconceptions

- ❌ “Model accuracy is enough”  
- ❌ “Once deployed, we’re done”  
- ❌ “Monitoring is optional”  
- ❌ “ML deployment = API”  

Deployment is **continuous responsibility**.

---

## 19. Why Deployment Basics Matter

Deployment basics explain:

- Why many ML projects fail
- Why production metrics differ from offline ones
- Why reproducibility matters
- Why ML is not just modeling

They turn ML into **real-world impact**.

---

## Usage Notes

- Link this note from:
  - Model Pipelines
  - Experiment Tracking
  - Evaluation Metrics — MOC
  - Error Analysis
- Treat deployment as part of model design, not the last step
