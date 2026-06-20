# Revenue Intelligence Architecture

**A Multi-Agent Revenue Intelligence Operating System for B2B Recurring Revenue. Demonstrates a governance-first, deterministic, multi-tenant architecture that unifies lead intelligence, classification, cash intelligence, and actionable executive narratives on a single Customer 360 spine.**

[View Live Architecture in Notion](https://beautiful-relative-aef.notion.site/RI-OS-38563b107cf380289821d7336f9a347e)

---

## What This Repo Shows

This repository is a public, NDA-safe portfolio reference architecture for a Senior Revenue Intelligence / RevOps leadership context. It describes how fragmented account, market, invoice, payment, and workflow data can be transformed into auditable revenue decisions in regulated, multi-tenant environments.

The system is modeled around four intelligence layers:

1. Lead Intelligence
2. Classification
3. Cash Intelligence
4. Narrative Intelligence

All layers operate on a shared Customer 360 spine and communicate through an append-only signal bus. The design prioritizes deterministic logic, governance-as-infrastructure, configurable tenant rules, and explainable outputs.

---

## Architecture Map

```text
External Data + Internal Systems
        |
        v
Extract -> Stage -> Validate -> Transform -> Load
        |
        v
Customer 360 Spine
        |
        v
+----------------------+----------------------+----------------------+
| Lead Intelligence    | Classification       | Cash Intelligence    |
+----------------------+----------------------+----------------------+
        |                      |                      |
        +----------- append-only signal bus ----------+
                               |
                               v
                    Narrative Intelligence
                               |
                               v
              Dashboards, workflows, and action queues
```

---

## Repository Structure

```text
revenue-intelligence-architecture/
├── README.md
├── ARCHITECTURE.md
├── intelligence-layers/
│   ├── LEAD_INTELLIGENCE.md
│   ├── CLASSIFICATION.md
│   ├── CASH_INTELLIGENCE.md
│   └── NARRATIVE_ENGINE.md
├── orchestration/
│   └── 7-PHASE-CYCLE.md
├── data-model/
│   ├── SCHEMA.md
│   └── signal-bus.md
├── governance/
│   ├── DESIGN-PRINCIPLES.md
│   └── go-to-market/
│       └── REVOPS-LEAN.md
└── assets/
    └── notation-links.md
```

---

## 7-Phase Orchestration Cycle

The platform is organized around seven execution phases:

1. Data ingestion
2. Lead intelligence
3. Classification
4. Cash intelligence
5. Narrative synthesis
6. Dashboard refresh
7. Outbound activation

See [orchestration/7-PHASE-CYCLE.md](orchestration/7-PHASE-CYCLE.md).

---

## Technology Stack

| Layer | Reference Technology |
| --- | --- |
| API | FastAPI |
| Database | PostgreSQL with row-level security |
| Frontend | React and TypeScript |
| Orchestration | n8n-style workflow orchestration |
| AI synthesis | Claude API for audited narrative generation |
| Deployment | Containerized services with environment-based configuration |

---

## Key Design Principles

- Deterministic logic for classification, scoring, matching, and routing.
- Signal-bus architecture instead of direct agent-to-agent coupling.
- Governance-as-infrastructure through RACI, change control, and audit trails.
- Multi-tenant configuration through reference tables rather than hardcoded logic.
- Jurisdiction-aware data sourcing for regulated environments.
- Explainable narratives where every claim maps back to source data.

---

## NDA-Safe Scope

This is a portfolio reference architecture. It contains no client names, customer records, production credentials, operational schedules, or real financial data. Schemas are intentionally generic and examples use abstract business entities such as accounts, invoices, payments, classifications, and signals.

