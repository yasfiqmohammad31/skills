# Yasfiq AI OS

Personal AI Operating System for learning, engineering, building products, career development, personal branding, and life productivity.

## Purpose

Yasfiq AI OS turns AI from a collection of tools into a modular personal capability system. Markdown is the source of truth; platform-specific implementations are adapters.

The current strategic direction is **AI-Powered Global Engineer**: combining software, AI, Electrical Engineering, IoT/robotics, English, and entrepreneurship.

## Architecture Status

**Architecture baseline: v1.0 — frozen for initial implementation**

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

See [ARCHITECTURE.md](ARCHITECTURE.md) and the design documents under `docs/`.

## Design Principles

- Portable first, platform second.
- One academic subject = one isolated Subject Skill.
- Cross-subject capabilities live in reusable Skills.
- AI amplifies learning and execution; it does not replace understanding.
- Prefer workflows over isolated prompts.
- Tool choice follows workflow, not hype.
- Important work should create durable, reusable artifacts.
- Personal, university, business, content, and company-work contexts stay separated.
- Production Skills are versioned and evaluated.

## Initial Domains

- University
- Cross-domain learning and research
- Builder / engineering / software
- Business and side income
- Content and personal branding
- Life OS / productivity
- Platform adapters
- Evaluations

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

## Next Phase

Build the first production Skill — **Introduction to Electrical Engineering** — and use it as the first end-to-end validation of the architecture.
