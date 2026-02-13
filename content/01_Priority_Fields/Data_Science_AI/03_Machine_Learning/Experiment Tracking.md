---
type: concept
domain: machine-learning
category: workflow
status: evergreen
---

# Experiment Tracking

> Experiment tracking is the systematic practice of **recording, organizing, and comparing machine learning experiments** so results are reproducible, interpretable, and improvable.

---

## 1. Core Idea

An ML experiment is not just a model run.

It is a combination of:
- Data
- Features
- Model
- Hyperparameters
- Loss
- Metrics
- Randomness

Experiment tracking answers:
> *What did we try, what worked, and why?*

---

## 2. Why Experiment Tracking Matters

Without experiment tracking:
- Results are irreproducible
- Improvements are accidental
- Knowledge is lost
- Teams repeat mistakes

With experiment tracking:
- Progress is cumulative
- Decisions are evidence-based
- Models can be trusted
- ML scales beyond one person

---

## 3. What Constitutes an Experiment

A complete experiment should track:

- Dataset version
- Feature pipeline version
- Model type
- Hyperparameters
- Training configuration
- Evaluation metrics
- Random seeds
- Artifacts (models, plots)
- Notes / hypotheses

If any of these are missing, the experiment is incomplete.

---

## 4. Experiment Tracking vs Version Control

| Aspect | Version Control | Experiment Tracking |
|---|---|---|
| Purpose | Code history | Model history |
| Tracks | Files | Runs |
| Granularity | Commits | Experiments |
| Answers | What changed? | What worked? |

Both are required. One cannot replace the other.

---

## 5. Experiment Tracking and the ML Loop

Experiment tracking enables the core ML iteration loop:

Hypothesis  
↓  
Experiment  
↓  
Evaluation  
↓  
Error Analysis  
↓  
New Hypothesis


Without tracking, the loop collapses.

🔗 Related:
- [[Error Analysis]]

---

## 6. Key Dimensions to Track

---

### 6.1 Parameters

- Hyperparameters
- Feature flags
- Thresholds

🔗 Related:
- [[Hyperparameter Tuning — MOC]]

---

### 6.2 Metrics

- Primary metric
- Secondary metrics
- Variance across folds

🔗 Related:
- [[Evaluation Metrics — MOC]]

---

### 6.3 Artifacts

- Trained models
- Predictions
- Plots
- Feature importances

Artifacts enable post-hoc analysis.

---

### 6.4 Metadata

- Experiment name
- Timestamp
- Author
- Notes / intent

Context matters.

---

## 7. Experiment Tracking and Model Selection

Model selection relies on:
- Comparing experiments fairly
- Understanding trade-offs
- Avoiding cherry-picking

Experiment tracking provides **auditability**.

🔗 Related:
- [[Model Selection]]

---

## 8. Experiment Tracking and Pipelines

Pipelines define *what is run*.  
Experiment tracking records *what happened*.

They are complementary.

🔗 Related:
- [[Model Pipelines]]

---

## 9. Reproducibility (Non-Negotiable)

Good experiment tracking ensures:
- Same code + same data + same params → same result

This requires tracking:
- Random seeds
- Library versions
- Environment details

Reproducibility is a **feature**, not a luxury.

---

## 10. Offline vs Online Experiments

### Offline
- Cross-validation
- Holdout evaluation
- Backtesting

### Online
- A/B testing
- Interleaving
- Bandit experiments

Both must be tracked consistently.

---

## 11. Experiment Tracking Granularity

Track experiments at:
- Model-level (big changes)
- Run-level (small tweaks)

But avoid:
- Tracking meaningless noise
- Logging everything blindly

Signal > volume.

---

## 12. Common Failure Modes

- ❌ No clear experiment naming  
- ❌ Overwriting results  
- ❌ Only tracking best runs  
- ❌ No hypothesis recorded  
- ❌ Losing data versions  

Experiment tracking is about **learning**, not vanity.

---

## 13. Minimal Viable Experiment Tracking

Even without tools, track:
- Experiment ID
- Model + params
- Dataset snapshot
- Metrics
- Notes

A simple log beats nothing.

---

## 14. Experiment Tracking at Team Scale

As teams grow:
- Shared dashboards become necessary
- Naming conventions matter
- Comparability is critical

Experiment tracking becomes **organizational memory**.

---

## 15. Relationship to Other Concepts

Experiment tracking connects strongly to:

- [[Model Pipelines]]
- [[Hyperparameter Tuning — MOC]]
- [[Model Selection]]
- [[Evaluation Metrics — MOC]]
- [[Error Analysis]]
- [[Reproducibility]]

---

## 16. Why Experiment Tracking Matters

Experiment tracking explains:

- Why some teams move fast without chaos
- Why results can be trusted
- Why ML systems improve over time
- Why ML is engineering, not trial-and-error

It is the **memory and accountability layer of ML**.

---

## Usage Notes

- Link this note from:
  - Model Pipelines
  - Model Selection
  - Hyperparameter Tuning — MOC
  - Error Analysis
- Treat experiment tracking as mandatory infrastructure
