# Yasfiq AI OS — Skill Registry

> **Purpose:** Single source of truth for the Skill Layer inventory. This file exists so Skill development can continue safely across conversation limits, sessions, and future refactors.

## Registry Rules

1. Every Skill gets one registry entry.
2. The repository is the source of truth; conversation counts are not authoritative.
3. Each entry should include category, path, status, version, and creation/last-known commit when available.
4. New Skills are added to this registry as part of the same development cycle.
5. Renamed, deprecated, or archived Skills should keep their history rather than disappearing silently.
6. A Skill's detailed behavior belongs in its `SKILL.md`; this file is an inventory and navigation layer.
7. `SKILL.md` and course context/material files are separate concerns. Course-specific material does not belong in this registry.

## Current Inventory

**Current registered total: 47 Skills**

### University — Subject Skills

| # | Skill | Path | Status | Version |
|---:|---|---|---|---|
| 1 | Introduction to Electrical Engineering | `skills/university/introduction-electrical-engineering/SKILL.md` | Active/Pilot | 1.1.0 |
| 2 | Computational Thinking & Programming | `skills/university/computational-thinking-programming/SKILL.md` | Draft | 1.0.0 |
| 3 | Renewable Energy & Solar Panel Foundation | `skills/university/renewable-energy-solar-panel-foundation/SKILL.md` | Draft | 1.0.0 |
| 4 | Career Design & Professional Development 1 | `skills/university/career-design-professional-development-1/SKILL.md` | Draft | 1.0.0 |

### Cross-Domain Skills

| # | Skill | Path | Status |
|---:|---|---|---|
| 5 | Learning Coach | `skills/cross-domain/learning-coach/SKILL.md` | Draft |
| 6 | Research Mentor | `skills/cross-domain/research-mentor/SKILL.md` | Draft |
| 7 | Information Literacy | `skills/cross-domain/information-literacy/SKILL.md` | Draft |
| 8 | English for Engineer | `skills/cross-domain/english-for-engineer/SKILL.md` | Draft |

### Builder Skills

| # | Skill | Path | Status | Version |
|---:|---|---|---|---|
| 9 | Coding Mentor | `skills/builder/coding-mentor/SKILL.md` | Draft | 1.0.0 |
| 10 | Product Builder | `skills/builder/product-builder/SKILL.md` | Draft | 1.0.0 |
| 11 | Engineering Project Mentor | `skills/builder/engineering-project-mentor/SKILL.md` | Draft | 1.0.0 |
| 12 | AI Architecture Mentor | `skills/builder/ai-architecture-mentor/SKILL.md` | Draft | 1.0.0 |
| 13 | Portfolio Mentor | `skills/builder/portfolio-mentor/SKILL.md` | Draft | 1.0.0 |
| 14 | IoT / Robotics Mentor | `skills/builder/iot-robotics-mentor/SKILL.md` | Draft | 1.0.0 |
| 15 | Cloud / Deployment Mentor | `skills/builder/cloud-deployment-mentor/SKILL.md` | Draft | 1.0.0 |
| 16 | Open Source & GitHub Mentor | `skills/builder/open-source-github-mentor/SKILL.md` | Draft | 1.0.0 |

### Business Skills

| # | Skill | Path | Status | Version |
|---:|---|---|---|---|
| 17 | Product Validation Mentor | `skills/business/product-validation/SKILL.md` | Draft | 1.0.0 |
| 18 | Freelance Mentor | `skills/business/freelance-mentor/SKILL.md` | Draft | 1.0.0 |
| 19 | Monetization Mentor | `skills/business/monetization-mentor/SKILL.md` | Draft | 1.0.0 |
| 20 | Entrepreneurship Mentor | `skills/business/entrepreneurship-mentor/SKILL.md` | Draft | 1.0.0 |
| 21 | Business Development Mentor | `skills/business/business-development-mentor/SKILL.md` | Draft | 1.0.0 |
| 22 | Personal Branding Mentor | `skills/business/personal-branding-mentor/SKILL.md` | Draft | 1.0.0 |
| 23 | Sales & Negotiation Mentor | `skills/business/sales-negotiation-mentor/SKILL.md` | Draft | 1.0.0 |
| 24 | Customer Success Mentor | `skills/business/customer-success-mentor/SKILL.md` | Draft | 1.0.0 |
| 25 | Operations & Delivery Mentor | `skills/business/operations-delivery-mentor/SKILL.md` | Draft | 1.0.0 |
| 26 | Strategic Planning Mentor | `skills/business/strategic-planning-mentor/SKILL.md` | Draft | 1.0.0 |

### AI / Data / Career / Communication Skills

| # | Skill | Path | Status | Version |
|---:|---|---|---|---|
| 27 | AI Tools & Workflow Mentor | `skills/ai/ai-tools-workflow-mentor/SKILL.md` | Draft | 1.0.0 |
| 28 | Automation Mentor | `skills/ai/automation-mentor/SKILL.md` | Draft | 1.0.0 |
| 29 | Data Analytics Mentor | `skills/data/data-analytics-mentor/SKILL.md` | Draft | 1.0.0 |
| 30 | Career Mentor | `skills/career/career-mentor/SKILL.md` | Draft | 1.0.0 |
| 31 | Communication & Public Speaking Mentor | `skills/communication/communication-public-speaking-mentor/SKILL.md` | Draft | 1.0.0 |
| 32 | Technical Writing Mentor | `skills/communication/technical-writing-mentor/SKILL.md` | Draft | 1.0.0 |

### Core / AI OS Skills

| # | Skill | Path | Status | Version |
|---:|---|---|---|---|
| 33 | AI Evaluation Mentor | `skills/ai/ai-evaluation-mentor/SKILL.md` | Draft | 1.0.0 |
| 34 | Decision-Making & Critical Thinking Mentor | `skills/decision/decision-making-critical-thinking-mentor/SKILL.md` | Draft | 1.0.0 |
| 35 | AI Radar & FOMO Filter | `skills/ai/ai-radar-fomo-filter/SKILL.md` | Draft | 1.0.0 |
| 36 | Verification & Trust Manager | `skills/core/verification-trust-manager/SKILL.md` | Draft | 1.0.0 |
| 37 | Context Engineering Mentor | `skills/core/context-engineering-mentor/SKILL.md` | Draft | 1.0.0 |
| 38 | Intent & Task Routing Mentor | `skills/core/intent-task-routing-mentor/SKILL.md` | Draft | 1.0.0 |
| 39 | Memory Management Mentor | `skills/core/memory-management-mentor/SKILL.md` | Draft | 1.0.0 |
| 40 | Priority Engine Mentor | `skills/core/priority-engine-mentor/SKILL.md` | Draft | 1.0.0 |
| 41 | AI OS Orchestrator | `skills/core/ai-os-orchestrator/SKILL.md` | Draft | 1.0.0 |
| 42 | Workflow Orchestration Mentor | `skills/core/workflow-orchestration-mentor/SKILL.md` | Draft | 1.0.0 |
| 43 | Tool & MCP Strategy Mentor | `skills/core/tool-mcp-strategy-mentor/SKILL.md` | Draft | 1.0.0 |
| 44 | Observability & AI OS Metrics Mentor | `skills/core/observability-ai-os-metrics-mentor/SKILL.md` | Draft | 1.0.0 |
| 45 | Skill Lifecycle & Governance Mentor | `skills/core/skill-lifecycle-governance-mentor/SKILL.md` | Draft | 1.0.0 |
| 46 | AI Security & Privacy Mentor | `skills/core/ai-security-privacy-mentor/SKILL.md` | Draft | 1.0.0 |
| 47 | AI Cost & Resource Optimization Mentor | `skills/core/ai-cost-resource-optimization-mentor/SKILL.md` | Draft | 1.0.0 |

## Registry Integrity Note

The repository history contains the authoritative commit history for each Skill. Some older Skill creation records may not have been captured with individual commit SHAs in this registry yet. That does not invalidate the Skill files; the registry can be enriched during a future maintenance pass.

## Continuing After a Conversation Limit

When starting a new conversation for this project:

1. Open `SKILL-REGISTRY.md`.
2. Read the current registered total.
3. Inspect the last completed Skill and its repository path.
4. Continue from the next planned Skill rather than recreating existing Skills.
5. Update this registry whenever a new Skill is created, renamed, deprecated, or archived.

## Planned Next Core Skills

The following are candidates for future Skill development, not yet registered as active Skills unless added above:

- additional core governance/operations capabilities identified during architecture development

These are intentionally listed as a roadmap rather than counted as existing Skills.

## Status Definitions

- **Draft:** Designed and committed, but not yet fully validated through sustained real-world use.
- **Active/Pilot:** In real use and being refined from actual usage evidence.
- **Deprecated:** Replaced or no longer recommended for new workflows.
- **Archived:** Retained for history but not used by the active system.

## Versioning

Use semantic-style versions for Skill behavior changes:

- **MAJOR:** incompatible behavior/contract change
- **MINOR:** backward-compatible capability addition
- **PATCH:** correction, clarification, or non-breaking refinement
