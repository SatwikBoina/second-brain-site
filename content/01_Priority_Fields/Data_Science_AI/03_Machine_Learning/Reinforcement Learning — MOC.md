# 📌 MOC — Reinforcement Learning

> Central hub for **Reinforcement Learning (RL)** in Machine Learning.
> Reinforcement learning focuses on learning **how to act** in an environment by interacting with it and optimizing **long-term rewards**.

---

## 1. Core Idea

In Reinforcement Learning, an **agent** interacts with an **environment**:

\[
\text{State} \xrightarrow{\text{Action}} \text{Reward + Next State}
\]

The objective is:
> Learn a policy that **maximizes cumulative reward over time**.

Unlike supervised learning:
- No labeled targets
- Feedback is delayed
- Actions influence future data

---

## 2. Why Reinforcement Learning Matters

Reinforcement learning is essential for:

- Sequential decision making
- Control problems
- Planning under uncertainty
- Learning from interaction instead of static data

RL powers:
- Robotics
- Games (Chess, Go)
- Recommendation systems
- Resource allocation
- Autonomous systems

---

## 3. Reinforcement Learning vs Other Paradigms

| Paradigm | Feedback | Data Source |
|-------|---------|------------|
| Supervised Learning | Explicit labels | Fixed dataset |
| Unsupervised Learning | No labels | Fixed dataset |
| Semi-Supervised Learning | Few labels | Fixed dataset |
| Reinforcement Learning | Reward signal | Agent interaction |

RL learns from **consequences**, not answers.

---

## 4. Core Components of Reinforcement Learning

---

### 4.1 Agent
- The learner / decision maker

---

### 4.2 Environment
- The world the agent interacts with

---

### 4.3 State (S)
- Representation of the current situation

---

### 4.4 Action (A)
- Choice made by the agent

---

### 4.5 Reward (R)
- Scalar feedback signal

---

### 4.6 Policy (π)
- Mapping from states to actions

\[
\pi(a \mid s)
\]

---

### 4.7 Value Function
- Expected future reward

🔗 Related:
- [[Value Function]]
- [[Q-Function]]

---

## 5. Reinforcement Learning Objective

The agent maximizes **expected return**:

\[
G_t = \sum_{k=0}^{\infty} \gamma^k R_{t+k}
\]

Where:
- \( \gamma \) = discount factor
- Controls short-term vs long-term reward

---

## 6. Exploration vs Exploitation

Key dilemma:
- **Exploration** → try new actions
- **Exploitation** → use known good actions

Balancing this trade-off is central to RL.

🔗 Related:
- [[Exploration vs Exploitation]]

---

## 7. Major Classes of Reinforcement Learning

---

### 7.1 Value-Based Methods

Learn value functions, derive policy indirectly.

Examples:
- [[Q-Learning]]
- [[SARSA]]
- Deep Q-Networks (DQN)

---

### 7.2 Policy-Based Methods

Learn policy directly.

Examples:
- Policy Gradient
- REINFORCE

---

### 7.3 Actor–Critic Methods

Combine value + policy learning.

Examples:
- A2C / A3C
- PPO
- DDPG

---

### 7.4 Model-Based Reinforcement Learning

Learn a model of the environment.

Examples:
- Planning + RL
- World models

---

## 8. Reinforcement Learning and Neural Networks

When state/action spaces are large:
- Neural networks approximate policies or value functions

This is **Deep Reinforcement Learning**.

🔗 Related:
- [[Neural Networks — MOC]]

---

## 9. Reward Design (Critical)

Rewards define **what the agent learns**.

Bad reward design causes:
- Reward hacking
- Unintended behavior
- Unstable learning

Reward ≠ objective (always).

---

## 10. Evaluation in Reinforcement Learning

Evaluation is difficult because:
- Data is non-IID
- Performance depends on policy behavior
- Exploration affects results

Common approaches:
- Average return
- Regret
- Success rate

---

## 11. Bias–Variance Perspective

RL challenges:
- High variance gradients
- Bias from bootstrapping
- Non-stationary data

Stability is a major concern.

---

## 12. Reinforcement Learning vs Planning

- Planning → environment model known
- RL → environment model unknown

Model-based RL bridges both worlds.

---

## 13. Common Failure Modes

- ❌ Sparse rewards
- ❌ Poor exploration
- ❌ Reward misalignment
- ❌ Overfitting to environment quirks

RL failures are often **design failures**, not algorithm failures.

---

## 14. When Reinforcement Learning Works Best

- Sequential decisions matter
- Actions affect future states
- Simulation environments exist
- Feedback is delayed

---

## 15. When Reinforcement Learning Is Overkill

- Static prediction problems
- Simple decision rules
- Small datasets without interaction
- High interpretability requirements

---

## 16. Relationship to Other ML Concepts

Reinforcement learning connects strongly to:

- [[Neural Networks — MOC]]
- [[Probabilistic Models — MOC]]
- [[Optimization]]
- [[Exploration vs Exploitation]]
- [[Sequential Decision Making]]

---

## 17. How Reinforcement Learning Fits in ML

