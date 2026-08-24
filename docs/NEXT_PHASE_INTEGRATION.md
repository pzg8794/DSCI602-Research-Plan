# DSCI 602 — Proposed Next-Phase Integration

**Updated:** August 24, 2026
**Status:** Draft for adviser discussion; not approved
**Proposed scope:** Fairness-aware quantum-network routing and resource allocation
**Out of scope for this phase:** Clinical data, clinical deployment, and clinical validation

## Purpose

This document proposes a DSCI 602 research direction that integrates the existing threat-aware quantum-routing draft with the fairness-aware bandit framework developed in DSCI 601.

The existing draft studies how bandit policy, threat regime, allocator choice, and replay capacity affect routing efficiency and robustness. The proposed next phase would preserve that technical foundation while adding a distinct research dimension: fairness-aware mediation and service equity in quantum entanglement routing and qubit allocation.

The central question is whether fairness-aware decision-making only constrains a baseline quantum-routing system or whether some operating regimes can reduce service disparities while preserving or improving efficiency, stability, resource utilization, and robustness.

## 1. Existing GA Draft: Research Questions

### GA-RQ1 — Policy Performance

**How do classical and context-aware multi-armed bandit policies perform under stochastic quantum-network conditions?**

### GA-RQ2 — Threat Progression

**How does the performance of bandit-based routing strategies change as network disruptions evolve from stochastic noise to structured, adaptive adversarial interference?**

### GA-RQ3 — Policy–Allocator–Capacity Interaction

**How do choices in bandit policy, resource-allocation strategy, and replay-capacity semantics interact to affect routing efficiency and stability in quantum entanglement routing?**

These questions remain within the existing GA draft. Any future revision or submission status will be determined separately.

## 2. Proposed DSCI 602 Research Questions

The proposed questions mirror the existing draft so the work remains one coherent research program while introducing a distinct fairness contribution.

### RQ1 — Fairness-Aware Policy Performance

**How does adding fairness-aware mediation to classical and context-aware multi-armed bandit policies affect routing efficiency, stability, and service equity under stochastic quantum-network conditions?**

This question extends GA-RQ1 from policy performance alone to joint performance-and-equity evaluation. It tests whether fairness-aware action selection produces a measurable utility cost, no meaningful cost, or an improvement in long-run network behavior.

### RQ2 — Fairness Under Increasing Threats

**How do routing performance and service disparities change as quantum-network disruptions evolve from stochastic noise to structured and adaptive adversarial interference, particularly when context quality differs across flows or service classes?**

This question extends GA-RQ2 by asking whether aggregate robustness can conceal concentrated service degradation for particular flows or service classes.

### RQ3 — Fairness Within the Policy–Allocator–Capacity Interaction

**How do bandit policy, qubit-allocation strategy, replay-capacity semantics, and fairness mediation interact to affect routing efficiency, stability, and service equity in quantum entanglement routing?**

This question extends GA-RQ3 by introducing fairness mediation as a planned experimental factor and service equity as a planned outcome.

The proposed experimental extension is:

$$
\text{Policy}\times\text{Allocator}\times\text{Capacity}
$$

becoming

$$
\text{Policy}\times\text{Allocator}\times\text{Capacity}\times\text{Fairness Mediation},
$$

while the evaluation target expands from

$$
\text{Efficiency}+\text{Stability}
$$

to

$$
\text{Efficiency}+\text{Stability}+\text{Service Equity}.
$$

## 3. Central Hypothesis

The proposed study would test whether quantum-network operating regions exist in which fairness disparities can be reduced without sacrificing aggregate utility, and potentially while improving it:

$$
\exists\;\lambda,\gamma,\epsilon
\quad\text{such that}\quad
\Delta_{\text{fairness}}\downarrow
$$

while

$$
U_{\text{network}}\ge U_{\text{baseline}}.
$$

The study would treat fairness and utility as interacting empirical objectives rather than assume in advance that improving one must worsen the other.

## 4. Candidate Quantum Service-Equity Measures

For routing action $a_t$ and oracle action $a_t^*$, cumulative regret remains:

$$
R_T=\sum_{t=1}^{T}\left(r_t(a_t^*)-r_t(a_t)\right).
$$

Candidate service-equity measures include:

### Entanglement-Success Gap

$$
\Delta_{\text{success}}(t)=
\left|
P_t(\text{success}\mid G_0)-P_t(\text{success}\mid G_1)
\right|.
$$

### Latency Gap

$$
\Delta_{\text{latency}}(t)=
\left|
\bar L_t(G_0)-\bar L_t(G_1)
\right|.
$$

### Normalized Resource-Access Gap

$$
\Delta_{\text{allocation}}(t)=
\left|
\frac{Q_t(G_0)}{D_t(G_0)}-
\frac{Q_t(G_1)}{D_t(G_1)}
\right|,
$$

where $Q_t(G)$ represents resources allocated to service cohort $G$ and $D_t(G)$ represents its demand. In this proposed quantum-network study, $G_0$ and $G_1$ are provisional operational flow or service classes, not legally or ethically protected attributes. The grouping and metric definitions require adviser review.

Other candidate measures include fidelity disparity, retry burden, starvation frequency, path-access diversity, and fairness-conditioned oracle efficiency.

## 5. Proposed Fairness-Aware Routing Objective

A proposed fairness-mediation objective could adjust a bandit utility score using anticipated service disparity and context-quality penalties:

$$
S_t^{\text{fair}}(a)=
U_t(a)
-\lambda\max\left(0,\widehat{\Delta}_{t}(a)-\epsilon\right)
-\gamma C_t(a).
$$

Where:

- $U_t(a)$ is the underlying policy's routing utility score;
- $\widehat{\Delta}_{t}(a)$ is the estimated service disparity associated with action $a$;
- $\epsilon$ is an allowable disparity threshold;
- $C_t(a)$ represents missing, stale, noisy, or low-confidence network context;
- $\lambda$ controls the utility–fairness tradeoff; and
- $\gamma$ controls sensitivity to context quality.

The study would examine how the fairness–performance relationship changes across $\lambda$, $\gamma$, and $\epsilon$, and whether it depends on policy, allocator, capacity, topology, and threat regime.

## 6. Proposed Research Objectives

1. Define measurable service-equity outcomes for competing quantum-network flows or service classes.
2. Extend the existing threat-aware evaluation grid by adding fairness mediation as a controlled factor.
3. Measure when fairness-aware routing reduces disparities at a performance cost, without meaningful loss, or with an aggregate performance improvement.
4. Test performance and equity under nonstationary and adversarial conditions.
5. Diagnose mechanisms such as load distribution, route starvation, path diversity, context quality, allocator behavior, replay capacity, and fidelity.
6. Reuse existing infrastructure where reproducible while separating experiments, analyses, and claims belonging to the GA draft from the proposed DSCI 602 contribution.

## 7. Relationship to the Existing GA Draft

| Dimension | Existing GA draft | Proposed DSCI 602 phase |
|---|---|---|
| Primary question | Robust quantum routing under matched threats | Fair and robust quantum resource allocation |
| Policy family | Classical, contextual/neural, adversarial, predictive, and hybrid bandits | Same technical family plus fairness-mediated variants |
| Threats | Baseline, stochastic, structured, adaptive, and online-adaptive | Same progression, evaluated for unequal service outcomes |
| Allocator | Experimental factor | Preserved and tested jointly with fairness mediation |
| Replay capacity | Experimental factor | Preserved and tested for fairness–performance interaction |
| Core outcomes | Efficiency, regret, robustness, and stability | Existing outcomes plus service equity |
| Contribution boundary | Threat-aware matched evaluation | Quantum-specific fairness formulation and fairness–performance interaction |

Cross-domain transfer to clinical fairness is future work only; this proposed phase uses no clinical data and makes no clinical-deployment claim.

## 8. Decisions for Adviser Discussion

1. Review and provisionally refine the three proposed research questions.
2. Select an initial service-cohort definition and fairness metrics.
3. Convert each research question into a test matrix using the existing experiment framework.
4. Identify fairness-mediation intervention points in the policy and allocator pipeline.
5. Determine which questions existing experiment states can support and which require new executions.
6. Keep the GA-draft revision track and the proposed DSCI 602 contribution separate in claims, experiments, and credit.
