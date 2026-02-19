# ATOM - The Cognitive Operating System

**Runtime Cognitive Governance for Autonomous AI**

*Developed by Atom Labs*  

---

## What ATOM Is

ATOM is the production platform that operationalizes the full Atom Labs cognitive security stack.

Where LCAC, RIS, and ABE are frameworks and standards, ATOM is the running system - the engine that enforces cognitive governance on every AI call, in real time, across any provider, in any environment.

Every AI call that passes through ATOM is:
- Authority-checked before execution (ABE)
- Scored against reasoning integrity pillars (RIS)
- Evaluated for cognitive boundary compliance (LCAC)
- Traced with an immutable, cryptographically-fingerprinted audit record

---

## Architecture

ATOM is built as a governance layer that wraps AI providers without replacing them. Any model call — cloud or local — passes through the governance pipeline before and after execution.

```
Tenant Request
      ↓
┌─────────────────────────────────────┐
│         Governance Gateway          │
│   Policy resolution · Auth check    │
│   Provider routing · ABE gate       │
└──────────────────┬──────────────────┘
                   ↓
┌─────────────────────────────────────┐
│         Reasoning Governor          │
│   RIS evaluation · Drift scoring    │
│   Semantic assertions · Severity    │
│   Enforcement state resolution      │
└──────────────────┬──────────────────┘
                   ↓
┌─────────────────────────────────────┐
│         Provider Router             │
│   Multi-provider · Fallback logic   │
│   Shadow execution · Cost tracking  │
└──────────────────┬──────────────────┘
                   ↓
        AI Provider (any)
                   ↓
┌─────────────────────────────────────┐
│         Governance Trace            │
│   SHA-256 policy fingerprint        │
│   Immutable audit record            │
│   CII scoring · Event stream        │
└─────────────────────────────────────┘
```

---

## Core Components

### Reasoning Governor
The central orchestrator. For every AI call, the Governor runs the full governance pipeline: RIS evaluation, drift detection, semantic assertion checking, severity computation, and enforcement state resolution. Results are persisted as governance events and surfaced to the enterprise console in real time.

### Sequential Executor
The execution spine. Manages multi-step agent workflows with deterministic policy application, pool-safe provider routing, memory management, and complete trace linkage. Every execution is fingerprinted with a SHA-256 policy hash — linking the governance decision to the exact policy state at execution time.

### LCAC Policy Engine
Evaluates every reasoning event against the active governance policy set. Policies are defined as code (JSON), versioned, and auditable. Policy violations are classified by severity and trigger configurable enforcement responses.

### Provider Router
Universal abstraction across every AI provider. ATOM supports all major cloud providers and local models through a single contract interface - enabling governance without vendor lock-in.

### Enforcement State Machine
Manages enforcement posture across four modes: Shadow (observe only), Warn (flag and continue), Block (prevent execution), and Emergency (full lockdown). Enforcement mode is tenant-configurable and Redis-backed for sub-millisecond state resolution.

### Governance Event Stream
Every governance decision is emitted as a structured event to the stream and persisted to the governance ledger. Events carry full forensic context: provider, model, tenant, agent, policy hash, severity, enforcement mode, simulated action, RIS scores, and drift data.

---

## Provider Support

ATOM's provider router supports every major AI provider and local execution environment:

**Cloud:** OpenAI · Anthropic · Google Gemini · Groq · AWS Bedrock · Azure OpenAI  
**Local:** llama.cpp / GGUF · Ollama · vLLM · ONNX  
**Dynamic:** Local model pool with LRU swap and file-based directory management

Shadow model execution runs a secondary provider in parallel to detect silent vendor model updates - a critical capability for organizations where model behavior changes are a compliance event.

---

## Governance Policies

ATOM policies are defined as versioned JSON files with explicit conditions and actions:

```json
{
  "id": "policy.coherence_guard",
  "name": "Coherence Guard",
  "version": "2025.11",
  "severity": "warning",
  "conditions": {
    "match": "any",
    "rules": [
      { "metric": "coherence.qci", "op": "<", "value": 0.70 }
    ]
  },
  "actions": [
    { "type": "emit_incident", "params": { "incident_type": "coherence_drop" }}
  ]
}
```

Production policy set includes: coherence guard · drift surge detector · integrity collapse lockdown · trust chronic low · variance anomaly · and six additional named policies.

Each policy generates a SHA-256 hash at evaluation time - providing an immutable link between every governance decision and the exact policy version that produced it.

---

## Enterprise Console

The ATOM enterprise console provides a real-time governance operations interface:

- **CII Dashboard** - Live Cognitive Integrity Index across all tenants and agents
- **Governance Timeline** - Full history of governance events with forensic drill-down
- **Enforcement Controls** - Real-time enforcement mode management per tenant
- **Provider Matrix** - Health, cost, drift, and performance across all provider
- **Trace Viewer** - Step-by-step execution traces with policy fingerprints
- **Risk Rollup** - Aggregated risk signals with configurable alerting

**Tech stack:** Next.js 15 · TypeScript · TailwindCSS · React Query

---

## Running Services

| Service | Description | Status |
|---------|-------------|--------|
| lcac-gateway-v2 | Governance gateway | Production |
| lcac-api | FastAPI backend | Production |
| atomlabs-console | Next.js enterprise UI | Production |
| postgresql | Governance ledger | Production |
| redis-server | Enforcement state / event stream | Production |
| cloudflared | Cloudflare tunnel | Production |

---

## Production Deployment

ATOM is deployed in production within the **Vanta Capital Intelligence OS** - governing autonomous trading, risk, and decision-making agents in a live financial environment.

This is the highest-stakes validation environment available: real capital, real decisions, real consequences.

---

## Multi-Tenant Architecture

ATOM is designed for enterprise multi-tenant deployment from the ground up:

- Row-level security in PostgreSQL isolates tenant data
- Per-tenant enforcement mode and policy configuration
- Per-tenant model preferences and provider routing
- Tenant-scoped governance event streams and audit exports
- API key management per tenant

---

→ See [LCAC.md](./LCAC.md) for the cognitive security framework  
→ See [RIS.md](./RIS.md) for the reasoning integrity standard  
→ See [ABE.md](./ABE.md) for execution enforcement  
→ See [CREDENTIALS.md](./CREDENTIALS.md) for research credentials and IP documentation
