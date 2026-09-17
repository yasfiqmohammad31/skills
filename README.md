# Yasfiq AI OS

Personal AI Operating System for learning, engineering, building products, career development, personal branding, and life productivity.

## Purpose

Yasfiq AI OS turns AI from a collection of tools into a modular personal capability system. Markdown is the source of truth; platform-specific implementations are adapters.

The current strategic direction is **AI-Powered Global Engineer**: combining software, AI, Electrical Engineering, IoT/robotics, English, and entrepreneurship.

## Architecture Status

**Architecture baseline: v1.0 — implementation in progress**

The conceptual architecture defines:

- AI OS entrypoint
- layered context and memory
- intent routing
- priority and energy-aware scheduling
- modular Skills
- reusable workflows
- tool registry and platform adapters
- verification and human approval
- artifact lifecycle
- evaluation and observability

See `ARCHITECTURE.md` for the system contract.

## Design Principles

- Portable first, platform second.
- One academic subject = one isolated Subject Skill.
- Subject Skill behavior is separated from mutable course context/materials.
- Cross-subject capabilities live in reusable Skills.
- AI amplifies learning and execution; it does not replace understanding.
- Prefer workflows over isolated prompts.
- Tool choice follows workflow, not hype.
- Important work should create durable, reusable artifacts.
- Personal, university, business, content, and company-work contexts stay separated.
- Production Skills are versioned and evaluated.

## Skill Layer Status

### University

- Introduction to Electrical Engineering — production pilot.
- Computational Thinking and Programming — scaffold.
- Renewable Energy and Solar Panel Foundation — scaffold.
- Career Design and Professional Development 1 — scaffold.

### Cross-Domain

- Learning Coach — scaffold.
- Research Mentor — scaffold.
- Information Literacy — scaffold.
- English for Engineer — scaffold.

More Builder, Business, Content, and Life OS Skills will be added incrementally.

## Repository Map

```text
core/       Personal context and operating principles
skills/     Modular AI capabilities
workflows/  Reusable procedures connecting Skills
templates/  Standardized input/output artifacts
adapters/   Platform-specific deployment instructions
evals/      Behavioral tests and regression cases
docs/       Architecture specifications and design contracts
```

## Important Boundary

AI Context Orchestrator is intentionally **not** part of the current Skill Factory architecture. Any integration will be considered later, after the core AI OS is validated through real use.

## Current Phase

Build the Skill Layer first. Subject Skills may be scaffolded without course materials; materials are added later to course context. The next implementation focus is expanding reusable Cross-Domain, Builder, Business, Content, and Life OS capabilities before deepening individual course contexts.
