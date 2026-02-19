# LCAC - Least-Context Access Control

**Extending Zero Trust into the Cognitive Layer**

*Author: Quinton Stackfield · Atom Labs · DOI: [10.5281/zenodo.17458835](https://doi.org/10.5281/zenodo.17458835)*

---

## The Core Insight

Zero Trust redefined network security by removing implicit trust from every connection, user, and device. It asks: *who is acting, and are they authorized?*

LCAC applies the same principle one layer deeper.

As AI systems move from reactive models to autonomous reasoning agents, the relevant question is no longer only *who is acting* — it is *what does the agent know, what is it reasoning about, and is that reasoning authorized?*

LCAC answers that question by treating every inference event as a bounded transaction requiring explicit authorization.

> *Zero Trust governs identity and action. LCAC governs cognition and inference.*

---

## The Problem LCAC Solves

Modern AI systems operating autonomously introduce a threat surface that existing security frameworks were not designed to address: **contextual contamination**.

Contextual contamination occurs when an agent carries or infers knowledge across domains in ways it was never authorized to. Examples:

- A customer service agent that accumulates context across sessions and uses prior conversation data to influence unrelated interactions
- A financial AI that reasons across portfolio boundaries, creating unintended coordination between isolated decision systems
- A healthcare AI whose diagnostic reasoning for one patient influences inference pathways for another
- A defense system that carries cognitive state across mission classification tiers

None of these failures look like a traditional security breach. No credentials were stolen. No network was compromised. The system is functioning exactly as designed — except the reasoning is contaminated.

LCAC addresses this by enforcing **reasoning isolation** at the cognitive level.

---

## Architecture

LCAC introduces a **Cognitive Control Plane** positioned above the traditional Model and Data Control Planes.

```
┌─────────────────────────────────────────┐
│         Cognitive Plane (LCAC)          │
│  Governs reasoning, recall, knowledge   │
│  flow between agents and sessions       │
├─────────────────────────────────────────┤
│           Model Plane                   │
│  Manages inference, policy, execution   │
├─────────────────────────────────────────┤
│            Data Plane                   │
│  Manages storage, retrieval, access     │
└─────────────────────────────────────────┘
```

Each reasoning event passes through LCAC's Cognitive Boundary Module, which validates:

- Context authenticity
- Reasoning scope and duration
- Cognitive trust thresholds

### Enforcement Flow

```
Request
  ↓
Authorization Stage
  (LCAC validates contextual access,
   creates ephemeral reasoning container)
  ↓
Inference Stage
  (reasoning proceeds with enforced isolation,
   dynamic monitoring active)
  ↓
Verification Stage
  (LCAC audits output for drift or violation)
  ↓
Termination Stage
  (reasoning state cleared,
   only approved insights persist)
```

---

## Core Principles

### 1. Cognitive Least Privilege
Traditional systems limit who can act. LCAC limits what can be known.

An AI agent's memory, context window, and external recall functions are governed by contextual authorization. Knowledge access is not cumulative across reasoning events. This prevents **cognitive privilege escalation** — the gradual accumulation of context an agent was never authorized to hold.

### 2. Reasoning Isolation
LCAC enforces contextual boundaries between reasoning sessions. Each inference chain operates in a defined trust zone with its own reasoning memory.

This prevents contamination between unrelated tasks and ensures alignment integrity in multi-agent and federated reasoning systems.

### 3. Cognitive Integrity
Every inference must be verifiable and reconstructable. LCAC establishes inference traceability through signed reasoning checkpoints and memory provenance tracking, ensuring no unauthorized data blending occurs during reasoning flow.

### 4. Runtime Governance
Governance exists as a runtime enforcement function, not an external audit. Ethical alignment, compliance, and transparency are embedded directly in system logic — enabling continuous verification of reasoning behavior and decisions.

### 5. Contextual Trust Anchors
LCAC replaces static trust permissions with adaptive, evidence-based reasoning limits. Each agent's reasoning scope evolves dynamically based on context confidence, provenance quality, and historical integrity — forming the basis of Cognitive Trust Scoring.

---

## Metrics

LCAC defines six quantitative measures for runtime evaluation:

| Metric | Description | Target |
|--------|-------------|--------|
| **CTS** — Cognitive Trust Score | Overall trustworthiness of a reasoning session | ≥ 0.85 |
| **RDI** — Reasoning Drift Index | Cross-context contamination rate | ≤ 0.25 |
| **IIR** — Inference Integrity Ratio | Proportion of verified, traceable inferences | ≥ 0.90 |
| **CBC** — Context Boundary Compliance | All sessions remain within authorized context IDs | 100% |
| **EAS** — Ethical Alignment Score | Reasoning alignment with governance constraints | ≥ 0.80 |
| **LCI** — LCAC Compliance Index | Aggregated compliance: (CTS + IIR + EAS) / (1 + RDI) | ≥ 2.5 |

### Enforcement Responses

- **RDI ≥ 0.75:** Automatic LCAC termination trigger
- **IIR < 0.50:** Trust violation — invoke audit hooks
- **LCI < 1.5:** Non-compliant — initiate governance response

---

## Applied Domains

**Healthcare:** Enforces cognitive isolation between patient contexts. Each diagnostic reasoning event occurs within a bounded session. Inference logs remain context-locked. Prevents cross-patient reasoning contamination.

**Financial Services:** Reasoning segmentation by entity, portfolio, and strategy domain. Cross-domain reasoning requires explicit authorization and traceable escalation. Enables explainable AI for regulators.

**Defense and Intelligence:** Mission-level reasoning isolation across tactical, strategic, and cyber layers. No AI agent carries cognitive state across classification tiers.

**Smart Infrastructure / IoT:** Contextual Trust Anchors restrict inference blending across domains. Prevents cascading reasoning loops across distributed agent networks.

**Education:** Per-learner reasoning isolation. Generalized knowledge can propagate; individual reasoning logic cannot.

---

## Relationship to Existing Frameworks

LCAC **complements** but does not replace Zero Trust, NIST SP 800-53, ISO 27001, or NIST AI RMF. Those frameworks govern security, privacy, identity, and general AI risk. LCAC introduces a dedicated cognitive security layer that existing frameworks leave ungoverned.

```
NIST AI RMF    →  AI risk management
EU AI Act      →  Regulatory compliance
Zero Trust     →  Identity and access
LCAC           →  Cognition and inference  ← new layer
```

---

## Production Implementation

LCAC is operationalized within the **ATOM platform** and deployed in production within the **Vanta Capital Intelligence OS**, governing autonomous trading, risk, and decision-making agents.

The reference implementation provides:
- Cognitive boundary enforcement at inference time
- Real-time trust scoring and drift monitoring
- Immutable governance ledger with cryptographic verification
- Multi-tenant policy isolation

→ See [ATOM.md](./ATOM.md) for full platform details  
→ See [RIS.md](./RIS.md) for the reasoning measurement standard built on top of LCAC

---

*Atom Labs · [ris.atomlabs.app](https://ris.atomlabs.app) · DOI: 10.5281/zenodo.17458835*
