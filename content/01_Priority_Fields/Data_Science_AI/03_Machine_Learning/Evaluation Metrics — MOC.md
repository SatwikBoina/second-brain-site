# 📌 MOC — Evaluation Metrics

> Central hub for **Evaluation Metrics in Machine Learning**.
> Evaluation metrics quantify **how well a model performs** on unseen data, from technical accuracy to real-world impact.

---

## 1. Core Idea

An evaluation metric answers:

> *How good is this model for our actual goal?*

Metrics:
- Do **not** train the model
- Do **not** guide gradients
- Do determine model selection, trust, and deployment

Optimizing the wrong metric means succeeding at the wrong problem.

---

## 2. Metrics vs Loss Functions

Critical distinction:

| Aspect | Loss Function | Evaluation Metric |
|---|---|---|
| Used during training | ✅ | ❌ |
| Differentiable | Usually | Rarely |
| Optimized directly | ✅ | ❌ |
| Human / business facing | ❌ | ✅ |

Loss shapes learning.  
Metrics judge outcomes.

🔗 Related:
- [[Loss Functions — MOC]]

---

## 3. Why Evaluation Metrics Matter

Evaluation metrics determine:
- Which model is chosen
- Whether a model is deployable
- Whether performance is acceptable
- Whether the model is fair and safe

In practice:
> Most ML failures come from **metric misuse**, not bad models.

---

## 4. Metric Choice Depends on Problem Type

---

## 4.1 Regression Metrics

Used when targets are **continuous**.

Common metrics:
- MAE
- MSE
- RMSE
- R²
- Adjusted R²
- MAPE / SMAPE

🔗 Hub:
- [[Regression Metrics — MOC]]

---

## 4.2 Classification Metrics

Used when targets are **categorical**.

Common metrics:
- Accuracy
- Precision / Recall
- F1-score
- ROC–AUC
- PR–AUC
- Confusion Matrix

🔗 Hub:
- [[Classification Metrics — MOC]]

---

## 4.3 Probabilistic Metrics

Evaluate **probability quality**, not just labels.

Examples:
- Log loss
- Brier score
- Calibration error

🔗 Related:
- [[Probability Calibration]]

---

## 4.4 Ranking Metrics

Used when **order matters more than labels**.

Examples:
- Precision@K
- Recall@K
- MAP
- NDCG

Common in:
- Search
- Recommendation systems

---

## 4.5 Ordinal Metrics

Used for **ordered categorical outputs**.

Examples:
- MAE on class indices
- Quadratic Weighted Kappa
- Spearman correlation

🔗 Related:
- [[Ordinal Regression]]

---

## 5. Metrics and Class Imbalance

Accuracy is often misleading.

Better alternatives:
- Precision / Recall
- F1-score
- PR–AUC
- Cost-weighted metrics

🔗 Related:
- [[Class Imbalance]]
- [[Cost-Sensitive Learning]]

---

## 6. Metrics and Thresholds

Many metrics depend on a **decision threshold**.

Key idea:
- Metrics change when threshold changes
- One model → many operating points

🔗 Related:
- [[Threshold Tuning]]

---

## 7. Metrics and Business Cost

Technical performance ≠ business value.

Sometimes the right metric is:
- Expected cost
- Risk-weighted error
- Custom KPI

🔗 Related:
- [[Cost-Sensitive Learning]]

---

## 8. Metrics and Bias–Variance

Metric behavior reflects:
- Overfitting
- Underfitting
- Model instability

Variance across folds matters as much as mean score.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Cross Validation]]

---

## 9. Metrics and Model Selection

Model selection is metric-driven.

But:
- One metric is rarely enough
- Trade-offs must be explicit

🔗 Related:
- [[Model Selection]]

---

## 10. Metrics and Fairness

Overall metrics can hide subgroup failures.

Fair evaluation requires:
- Group-wise metrics
- Error parity checks
- Calibration by group

🔗 Related:
- [[Fairness in Machine Learning]]

---

## 11. Metrics for Structured & Complex Outputs

Standard metrics fail when outputs are structured.

Alternatives:
- Sequence accuracy
- Edit distance
- Span-level F1
- Structure-aware metrics

🔗 Related:
- [[Structured Prediction]]

---

## 12. Validation Strategy and Metrics

Metrics are only meaningful when computed correctly.

Best practices:
- Use held-out data
- Cross-validate when data is limited
- Never tune on test metrics

🔗 Related:
- [[Data Leakage]]
- [[Train-Test Split]]
- [[Cross Validation]]

---

## 13. Common Metric Anti-Patterns

- ❌ Using accuracy for imbalanced data  
- ❌ Reporting a single metric only  
- ❌ Ignoring variance across runs  
- ❌ Optimizing metrics disconnected from business  
- ❌ Comparing models using different metrics  

Metrics are **decision tools**, not decorations.

---

## 14. How Evaluation Metrics Fit in ML

