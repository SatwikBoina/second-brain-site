---
type: concept
domain: machine-learning
category: hyperparameter-tuning
status: evergreen
---

# Bayesian Optimization

> Bayesian Optimization is a hyperparameter optimization technique that builds a **probabilistic model** of the objective function and uses it to choose the most promising hyperparameters to evaluate next.

---

## 1. Core Idea

Bayesian Optimization treats hyperparameter tuning as a **sequential decision problem**.

Instead of blindly searching:
- It learns from past evaluations
- Models uncertainty
- Actively balances exploration vs exploitation

It asks:
> *Where should I try next to most improve performance?*

---

## 2. Why Bayesian Optimization Is Needed

Hyperparameter tuning is often:
- Expensive
- Noisy
- Black-box (no gradients)

Bayesian Optimization is designed specifically for **expensive black-box functions**.

---

## 3. How Bayesian Optimization Works (High-Level)

Bayesian Optimization follows a loop:

1. Fit a **surrogate model** to past results  
2. Use an **acquisition function** to select next point  
3. Evaluate the true objective (train + validate model)  
4. Update the surrogate model  
5. Repeat until budget exhausted  

---

## 4. Surrogate Model

The surrogate approximates the true objective function.

Common choices:
- Gaussian Process (GP)
- Tree-structured Parzen Estimator (TPE)
- Random Forest (SMAC)

Purpose:
- Predict performance
- Quantify uncertainty

🔗 Related:
- [[Gaussian Process]]
- [[Probabilistic Models]]

---

## 5. Acquisition Function

The acquisition function decides **where to sample next**.

Common acquisition functions:
- Expected Improvement (EI)
- Probability of Improvement (PI)
- Upper Confidence Bound (UCB)

It encodes the **exploration–exploitation tradeoff**.

🔗 Related:
- [[Exploration vs Exploitation]]

---

## 6. Bayesian Optimization vs Random Search

| Aspect | Bayesian Optimization | Random Search |
|-----|----------------------|---------------|
| Uses past results | Yes | No |
| Sample efficiency | Very High | Medium |
| Computational overhead | Higher | Low |
| Parallelization | Limited | Easy |
| Noise handling | Strong | Weak |

🔗 Related:
- [[Random Search]]

---

## 7. Bayesian Optimization vs Grid Search

| Aspect | Bayesian Optimization | Grid Search |
|-----|----------------------|-------------|
| Efficiency | Very High | Low |
| Scalability | Good | Poor |
| Black-box aware | Yes | No |
| Guarantees | Probabilistic | Deterministic |

🔗 Related:
- [[Grid Search]]

---

## 8. Bias–Variance Perspective

Bayesian Optimization helps:
- Tune regularization precisely
- Control model complexity
- Reduce variance from poor hyperparameters

But it **does not replace validation**.

🔗 Related:
- [[Bias–Variance Tradeoff]]
- [[Model Complexity]]

---

## 9. When Bayesian Optimization Works Best

- Expensive models
- Small to medium tuning budgets
- Continuous hyperparameters
- Boosting models
- Neural networks

---

## 10. When Bayesian Optimization Works Poorly

- Very cheap models
- Huge parallel budgets
- Extremely noisy objectives
- Very high-dimensional spaces

---

## 11. Bayesian Optimization and Cross Validation

Usually combined with:
- k-fold CV
- Stratified k-fold (classification)

But CV increases cost → fewer BO iterations.

🔗 Related:
- [[Cross Validation]]

---

## 12. Bayesian Optimization and Data Leakage ⚠️

❌ Wrong:
- Using test set inside optimization

✅ Correct:
1. Optimize using CV or validation set
2. Lock hyperparameters
3. Evaluate once on test set

🔗 Related:
- [[Data Leakage]]
- [[Train–Test Split]]

---

## 13. Practical Implementations

Popular tools:
- Optuna
- Hyperopt
- scikit-optimize
- SMAC

These abstract surrogate + acquisition logic.

---

## 14. Common Mistakes

- ❌ Too small initial random phase  
- ❌ Poorly defined search bounds  
- ❌ Optimizing noisy metrics directly  
- ❌ Expecting global optimum guarantee  

Bayesian Optimization is **smart**, not magic.

---

## 15. Why Bayesian Optimization Matters

Bayesian Optimization explains:
- Why fewer trials can outperform random search
- Why tuning efficiency matters more than brute force
- How uncertainty guides decision-making

It is the **state-of-the-art classical tuning method**.

---

## Usage Notes

- Prefer Bayesian Optimization when:
  - Training is expensive
  - Budget is limited
- Link this note from:
  - Hyperparameter Tuning — MOC
  - Model Selection
