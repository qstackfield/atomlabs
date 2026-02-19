# RIS - Reasoning Integrity Standard

**The Global Reasoning Integrity Standard for the Autonomous Age**

*Developed and maintained by Atom Labs - Standards Division*  
*Live portal: [ris.atomlabs.app](https://ris.atomlabs.app)*  
*Repository: [github.com/qstackfield/ris-standard](https://github.com/qstackfield/ris-standard)*

---

## What RIS Is

The Reasoning Integrity Standard (RIS) is the first formal framework dedicated to measuring the integrity of AI reasoning itself.

Where existing frameworks govern security, privacy, compliance, and safety, RIS governs **how a system reasons** — whether its internal reasoning process is stable, coherent, bounded, and auditable under real-world conditions.

**The objective:** Make AI reasoning integrity a measurable, reportable, and certifiable property.

RIS v1.0 defines:
- A multi-level reasoning integrity model (RIS-0 through RIS-4)
- A measurement framework and scoring methodology
- Mandatory controls and governance requirements
- Evaluation and audit procedures
- A reference implementation (LCAC) and operational pipeline

---

## Why RIS Exists

Modern AI systems exhibit powerful but structurally fragile reasoning behavior:

- Reasoning chains drift over time and across contexts
- Identical prompts produce materially different reasoning paths
- Multi-agent systems amplify variance and drift
- Tool calls, memory, and upstream systems influence reasoning in opaque ways
- Organizations have no standard way to assess reasoning stability

This creates structural gaps in safety-critical deployments, enterprise risk and governance, procurement and vendor due diligence, model change management, and regulatory compliance.

**RIS closes this gap.** It provides a concrete, testable standard for reasoning stability and governance.

---

## RIS Levels

| Level | Name | Summary |
|-------|------|---------|
| **RIS-0** | Uncontrolled Reasoning | No stability guarantees; unsuitable for critical use |
| **RIS-1** | Drift-Sensitive Reasoning | Highly sensitive to context and perturbation |
| **RIS-2** | Semi-Stable Reasoning | Partially consistent; acceptable for low-risk flows |
| **RIS-3** | Controlled, Production-Grade Reasoning | Stable within defined envelopes; enterprise-ready |
| **RIS-4** | High-Integrity, Safety-Critical Reasoning | Strictly controlled; auditable for regulated use |

Each level carries eligibility criteria, required controls, evidence expectations, variance and drift parameters, and governance implications.

**Level selection is a risk decision, not just a technical metric.**

---

## Five Measurement Pillars

### 1. Chain Stability
Reliability of multi-step reasoning across sessions, users, and contexts. Measures whether the system produces consistent reasoning chains when given semantically equivalent inputs under varying conditions.

### 2. Semantic Coherence
Internal logical consistency and structural quality of reasoning outputs. Evaluates whether the reasoning structure is internally sound, not just whether the final answer is correct.

### 3. Drift Sensitivity
How easily reasoning degrades due to time, prompt changes, data shifts, tool calls, or configuration changes. A low drift sensitivity score indicates resilient reasoning under perturbation.

### 4. Variance Envelope Compliance
Predictability of reasoning within an acceptable variance band under repeated evaluation. Defines the operational boundary within which a system's reasoning is considered stable.

### 5. Boundary Governance
Adherence to defined operational, ethical, and safety boundaries. Measures whether the system respects the reasoning constraints it has been given.

---

## The RIS Evaluation Pipeline

```
1. Scenario and sample design
2. Baseline runs for chain stability
3. Perturbation runs for drift and variance
4. Semantic coherence scoring
5. Boundary and control checks
6. Aggregation into RIS metrics
7. RIS Level assignment (0–4)
8. Scorecard and report generation
9. CII (Cognitive Integrity Index) computation
10. Publication to RIS Portal or internal systems
```

---

## Cognitive Integrity Index (CII)

CII is the unified trust score produced by the full RIS evaluation pipeline. It aggregates RIS scores across the five pillars into a single operational indicator.

**Live CII dashboard:** [ris.atomlabs.app](https://ris.atomlabs.app) — showing real evaluation runs, scored models, leaderboard rankings, and trend data.

Current portal status:
- 11 evaluations completed
- 3 unique models scored
- RIS levels assigned across RIS-0 through RIS-2
- Sources: LCAC pipeline and portal submissions

---

## The Full Standard Structure

RIS v1.0 is structured as a formal specification:

```
0.  Foreword
1.  Scope
2.  Normative References
3.  Fundamental Concepts
4.  RIS Levels
5.  Measurement Framework
6.  Controls
7.  Scoring and Conformance
8.  Risk Models
9.  Evaluation Methodology
10. Audit Guidelines
11. Reference Implementation
12. Standard Mapping
13. Appendices
```

The complete standard is available at [ris.atomlabs.app](https://ris.atomlabs.app).

---

## Relationship to Existing Standards

RIS is explicitly designed to complement, not replace:

| Framework | Scope | RIS Adds |
|-----------|-------|----------|
| NIST SP 800-53 | Security control baselines | Reasoning integrity layer |
| ISO/IEC 27001 | Information security management | Cognitive security controls |
| SOC 2 | Service organization controls | Reasoning audit evidence |
| NIST AI RMF | AI risk management | Measurable reasoning stability |
| EU AI Act | Regulatory structure for AI | Certifiable reasoning conformance |
| OWASP ASVS | Application security verification | Cognitive boundary verification |

---

## Adoption Path

1. **Internal Analysis** - Review the standard, levels, and measurement framework
2. **Pilot Evaluation** - Run RIS evaluations against internal systems using the benchmark guide
3. **Establish Internal Targets** - Define required RIS levels per use case
4. **Integrate with Governance** - Link RIS results with model registries, incident management, and vendor review
5. **Continuous Evaluation** - Extend into CI/CD and runtime via LCAC and the Governor
6. **Certification (optional)** - Engage Atom Labs for RIS Certification and audit-grade scorecards

---

## Who RIS Is For

- Enterprise AI teams deploying LLMs and agentic systems
- Governance, risk, and compliance functions
- Safety and assurance organizations
- Engineering and MLOps teams building cognitive infrastructure
- Research labs studying reasoning drift and stability
- Vendors seeking demonstrable reasoning guarantees
- Regulators and auditors needing structured reasoning evidence

**If reasoning instability has a cost, RIS creates a way to measure and mitigate it.**

---

## Citation

```
Reasoning Integrity Standard (RIS) v1.0
Atom Labs, 2025
https://github.com/qstackfield/ris-standard
https://ris.atomlabs.app
```

---

## Contact

**Atom Labs - Standards Division**  
Email: RIS@atomlabs.app  
GitHub: [github.com/qstackfield](https://github.com/qstackfield)

→ See [LCAC.md](./LCAC.md) for the cognitive security framework RIS is built on  
→ See [ATOM.md](./ATOM.md) for the platform that operationalizes RIS at runtime
