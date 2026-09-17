# Yasfiq AI OS

Personal AI Operating System for learning, engineering, building products, career development, personal branding, and life productivity.

## Purpose

Yasfiq AI OS is a portable, platform-agnostic collection of modular AI Skills, workflows, templates, context, adapters, and evaluations. Markdown is the source of truth; platform-specific implementations are adapters.

## Design Principles

- Portable first, platform second.
- One academic subject = one isolated Subject Skill.
- Cross-subject capabilities live in reusable Skills.
- AI should amplify learning and execution, not replace understanding.
- Prefer workflows over isolated prompts.
- Every important Skill has an explicit output contract and evaluation cases.
- Tool choice follows the workflow; AI hype does not determine architecture.
- Personal, university, business, content, and company-work contexts must remain separated.

## Current Status

Version: 0.1.0-foundation

This repository currently contains the architecture and operating conventions. Individual Skills will be added incrementally.

## Initial Domains

- University
- Cross-domain learning and research
- Builder / engineering / software
- Business and side income
- Content and personal branding
- Life OS / productivity
- Platform adapters
- Evaluations

## Important Boundary

AI Context Orchestrator is intentionally NOT part of this architecture as a Skill Factory at this stage. Integration can be designed as a later phase after the core AI OS has been validated through real use.

## Repository Map

```text
core/       Personal context and operating principles
skills/     Modular AI capabilities
workflows/  Reusable procedures connecting Skills

templates/  Standardized input/output artifacts
adapters/   Platform-specific deployment instructions

evals/      Behavioral tests and regression cases
```

See [ARCHITECTURE.md](ARCHITECTURE.md) for the system design.