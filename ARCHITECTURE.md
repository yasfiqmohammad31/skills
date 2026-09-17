# AI OS Architecture v1.0

## 1. System Goal

Yasfiq AI OS is designed to turn AI from a collection of tools into a modular personal capability system supporting four strategic areas:

1. University and deep learning
2. Professional and engineering development
3. Product building and side income
4. Content creation and personal branding

A fifth layer, Life OS, coordinates time, tasks, files, routines, and AI usage across the four areas without mixing their private contexts.

## 2. Core Architecture

```text
YOU
│
├── LIFE OS
│   ├── Daily Planner
│   ├── Weekly Review
│   ├── Productivity
│   ├── Knowledge Management
│   └── AI Tool Router / AI Radar
│
├── UNIVERSITY
│   ├── Academic Router
│   ├── Subject Skills
│   │   ├── Career Design & Professional Development 1
│   │   ├── Computational Thinking & Programming
│   │   ├── Introduction to Electrical Engineering
│   │   └── Renewable Energy & Solar Panel Foundation
│   └── Cross-Subject Skills
│       ├── Learning Coach
│       ├── Research Mentor
│       ├── English for Engineer
│       └── Information Literacy
│
├── BUILDER / CAREER
│   ├── Coding Mentor
│   ├── Product Builder
│   ├── Engineering Project Mentor
│   ├── AI Architecture Mentor
│   ├── Portfolio Mentor
│   ├── Jules Mentor
│   ├── IoT / Robotics Mentor
│   └── Cloud / Deployment Mentor
│
├── BUSINESS
│   ├── Product Validation
│   ├── Freelance Mentor
│   ├── Monetization Mentor
│   └── Client Communication
│
└── CONTENT / BRAND
    ├── Content Strategist
    ├── Technical Content Creator
    ├── Content Repurposing
    └── Personal Branding Mentor
```

## 3. Skill Taxonomy

### Subject Skill
Exactly one Skill per course or formally defined learning subject. Subject Skills own their course-specific context and must not silently blend unrelated course material.

### Cross-Subject Skill
Reusable capability that operates across multiple subjects, such as research, learning science, English, or information literacy.

### Builder Skill
Capability for creating technical systems, products, codebases, or portfolio evidence.

### Business Skill
Capability for validation, monetization, freelancing, client communication, and revenue experiments.

### Content Skill
Capability for turning real work and learning into public-facing content and personal-brand assets.

### Life OS Skill
Capability for coordinating time, tasks, files, routines, and AI usage.

## 4. Context Boundaries

The following contexts must remain explicitly separated:

- UNIVERSITY
- COMPANY WORK
- PERSONAL BUSINESS / FREELANCE
- CONTENT / PERSONAL BRAND
- PRIVATE LIFE

Cross-context use requires explicit user intent. Company information must never be imported into personal Skills by default.

## 5. Subject Skill Rule

Each Subject Skill must contain:

- purpose
- scope
- course context
- known learning outcomes
- current progress
- prerequisite map
- interaction modes
- teaching behavior
- output contract
- verification rules
- evaluation cases

Default interaction modes are Explain, Learn, Practice, Solve, Quiz, Review, Assignment Support, Exam Prep, and Explore Beyond Curriculum.

## 6. Shared Skill Contract

Every production Skill should define:

```yaml
name:
version:
type:
domain:
status:
inputs:
outputs:
dependencies:
compatible_platforms:
```

The body should define behavior, workflow, guardrails, context requirements, and evaluation criteria.

## 7. Workflow Model

Skills are capabilities. Workflows are reusable procedures that combine them.

```text
User Goal
  ↓
Intent / Context Detection
  ↓
Router
  ↓
Skill Selection
  ↓
Workflow
  ↓
Tool / Platform Adapter
  ↓
Verification
  ↓
Artifact / Next Action
```

## 8. Output Philosophy

Important activities should create durable artifacts whenever reasonable:

- learning → notes / solved examples / quizzes
- research → evidence brief / synthesis / references
- project → code / documentation / demo / portfolio
- English → writing / speaking log / corrections
- content → post / script / media plan
- planning → tasks / calendar / next actions

The goal is output multiplication: one meaningful activity should produce multiple useful downstream assets when practical.

## 9. Platform Independence

Core Skills are platform-agnostic. Platform-specific instructions belong under `adapters/`.

Examples:

- ChatGPT adapter
- Gemini adapter
- Claude adapter
- Jules adapter

A platform can change without forcing the core Skill definition to change.

## 10. Tool Selection Principle

A tool is adopted because it improves a defined workflow, not because it is popular or newly released.

AI Radar exists to reduce FOMO by filtering new tools through relevance, testing, usefulness, and integration cost.

## 11. Evaluation

A Skill is considered production-ready only when representative scenarios are defined and the expected behavior is testable. Evaluation should cover normal cases, edge cases, failure cases, and regression behavior.

## 12. Deferred Capabilities

The following are intentionally future layers, not initial dependencies:

- AI agent orchestration
- MCP
- advanced automation
- Gemini Spark workflows
- Google Cloud workflows
- broader platform adapters

AI Context Orchestrator integration as a Skill Factory is explicitly deferred to a later phase.
