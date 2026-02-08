# Dual-Path Lambda Learning  
### Functional Variational Convergence via KL Drift and Adaptive Gain Control

This repository implements a **functional dynamical learning system** that compares two optimization pathways:

1. **Pure drift minimization** via gradient descent  
2. **Adaptive gain-controlled learning** via annealed sensitivity dynamics  

The system is expressed using **immutable lambda-style state transitions** and evaluated through **information-theoretic convergence metrics** (KL divergence) alongside classical loss.

---

## 📌 Core Idea

Learning is modeled as a **discrete-time dynamical system**:

- State evolves through **pure functional transformations**
- No imperative mutation in learning logic
- Convergence measured against a known probabilistic ground truth

Two paths operate in parallel:

### Path A — Representation Purification (Drift Minimization)

\[
\theta_{t+1} = \theta_t - \eta \nabla F
\]

### Path B — Sensitivity Annealing (Adaptive Gain Control)

\[
\theta_{t+1} = \theta_t - \eta \alpha_t \nabla F
\]
\[
\alpha_{t+1} = \alpha_t \cdot \lambda
\]

where:

- \( \theta \) is the inferred mean  
- \( \alpha \) is a self-regulating sensitivity parameter  
- \( \lambda \) is a decay factor  


