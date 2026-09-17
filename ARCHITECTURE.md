# AI OS Architecture v1.0

## 1. Purpose and North Star

Yasfiq AI OS is a portable personal AI operating system for an Electrical Engineering student, IT Solution professional, software builder, aspiring global engineer, side-income builder, and technical content creator.

The system exists to turn AI from a collection of isolated tools into a set of modular capabilities that improve learning, engineering, product building, career development, content creation, and life management.

North-star direction:

> AI-Powered Global Engineer — combining software, AI, Electrical Engineering, IoT/robotics, English, and entrepreneurship.

The OS optimizes for capability growth and durable outputs rather than raw AI usage or tool count.

## 2. Strategic Domains

```text
YOU
│
├── LIFE OS
│   ├── Daily Planning
│   ├── Weekly Review
│   ├── Productivity
│   ├── Knowledge / File Management
│   ├── Priority Engine
│   ├── Energy-Aware Scheduling
│   └── AI Router / AI Radar
│
├── UNIVERSITY
│   ├── Academic Router
│   ├── Subject Skills (one per course/subject)
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

Company Work is an isolated context boundary, not a general-purpose personal Skill domain.

## 3. System Layers

The OS is composed of the following conceptual layers:

1. **Entrypoint** — a single human-facing starting point.
2. **Context Engine** — determines which contexts are active and prevents accidental mixing.
3. **Memory Layer** — stores only information that is intentionally persistent.
4. **Intent Router** — converts a natural-language request into an action intent.
5. **Priority & Energy Engine** — selects what should happen now based on value, urgency, available time, and energy.
6. **Skill Layer** — provides reusable capabilities.
7. **Workflow Layer** — provides procedures that combine Skills and tools.
8. **Tool Registry / Adapter Layer** — maps workflows to appropriate products and platforms.
9. **Verification & Approval Layer** — checks correctness and determines when human confirmation is required.
10. **Artifact Layer** — produces durable outputs and tracks their lifecycle.
11. **Observability Layer** — measures whether the OS is producing meaningful improvements.

## 4. Canonical Execution Flow

```text
User
 ↓
AI OS Entrypoint
 ↓
Intent + Context Detection
 ↓
Context Resolution
 ↓
Priority / Energy Check (when scheduling is involved)
 ↓
Skill Selection
 ↓
Workflow Selection
 ↓
Tool / Platform Adapter
 ↓
Execution
 ↓
Verification
 ↓
Human Approval? ── Yes ──→ User Review
       │
       No
       ↓
Artifact / Action
 ↓
Artifact Lifecycle
 ↓
Metrics / Learning Feedback
```

## 5. Entrypoint Principle

Users should not need to memorize Skill names.

Natural-language requests should be the default interface. The system may infer the relevant domain, subject, intent, mode, and workflow.

Resolution priority:

```text
Explicit user instruction > safe inference > guided clarification
```

When ambiguity materially affects the result, the OS asks a concise clarification instead of guessing.

## 6. Context Architecture

Contexts are intentionally layered:

```text
GLOBAL CONTEXT
├── Identity
├── Stable Goals
├── Preferences
└── Principles

DOMAIN CONTEXT
├── University
├── Personal Business / Freelance
├── Content / Personal Brand
├── Private Life
└── Company Work (isolated)

TASK CONTEXT
├── Course
├── Assignment
├── Project
├── Research task
└── Content task

SESSION CONTEXT
└── Current conversation / immediate state
```

Context loading follows least-necessary-context: a Skill should receive only the context required for the task.

Cross-context use requires explicit user intent. Company data, source code, credentials, internal documents, or confidential information must never be imported into personal Skills by default.

## 7. Memory Model

Memory is not a transcript dump.

```text
Stable Memory
→ long-lived identity, preferences, durable goals

Domain Memory
→ university, business, content, private-life conventions

Project Memory
→ active project state and decisions

Session Memory
→ temporary working state

Ephemeral Context
→ facts needed only for the current step
```

Rules:

- Store intentionally, not automatically.
- Prefer summaries and durable decisions over raw conversation history.
- Never store secrets or credentials.
- Retire stale information.
- Keep company/work memory isolated from personal memory.

## 8. Skill Taxonomy

### Subject Skill
Exactly one Skill per course or formally defined learning subject. It owns course-specific context and does not silently blend unrelated course material.

### Cross-Subject Skill
Reusable capabilities spanning subjects, such as learning, research, English, and information literacy.

### Builder Skill
Capabilities for code, technical systems, products, projects, and portfolio evidence.

### Business Skill
Capabilities for validation, monetization, freelancing, client communication, and revenue experiments.

### Content Skill
Capabilities for transforming real work and learning into public-facing content and personal-brand assets.

### Life OS Skill
Capabilities for planning, prioritization, scheduling, organization, and AI coordination.

## 9. Subject Skill Rule

One academic course = one isolated Subject Skill.

A Subject Skill should define:

- purpose
- scope and exclusions
- course context
- known learning outcomes
- current progress
- prerequisite map
- interaction modes
- teaching behavior
- output contract
- verification rules
- evaluation cases

Default modes:

Explain, Learn, Practice, Solve, Quiz, Review, Assignment Support, Exam Prep, and Explore Beyond Curriculum.

The Explore Beyond Curriculum mode may connect to other domains, but the Skill must clearly label when material leaves the course scope.

## 10. Skill Invocation and Modes

Modes may be selected through:

1. Explicit user request.
2. Safe inference from the request.
3. Guided clarification when intent is ambiguous.

The Skill must preserve the user's requested mode when explicitly stated.

## 11. Shared Skill Contract

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

The body defines behavior, workflow, guardrails, context requirements, verification, and evaluation criteria.

## 12. Workflow Model

Skills are capabilities; workflows are repeatable procedures that combine Skills and tools.

A workflow should document:

- trigger
- prerequisites
- steps
- inputs
- tools
- decision points
- verification
- outputs
- next actions

## 13. Priority Engine

When multiple tasks compete, the OS considers:

- urgency
- deadline proximity
- importance
- impact
- long-term value
- dependencies
- effort
- available time
- current energy

Priority is a planning aid, not an autonomous life decision. The user remains the final decision-maker.

## 14. Energy-Aware Scheduling

The OS classifies work by cognitive demand:

### Deep Work
Coding, engineering problems, research synthesis, complex assignments, product architecture.

### Light Work
Reading, documentation, review, English writing, planning, content refinement.

### Mobile Work
Listening, speaking, flashcards, idea capture, voice brainstorming, review, lightweight research.

The schedule should fit task type to the user's available device, time, and energy.

## 15. Tool Registry and Selection

Tool choice follows the workflow, not popularity.

The Tool Registry should eventually describe:

```yaml
name:
category:
best_for:
not_for:
cost:
platform:
inputs:
outputs:
privacy:
latency:
skill_compatibility:
status:
```

New tools enter the system only after relevance is assessed and a small practical test is performed.

AI Radar exists to reduce FOMO, not to maximize awareness of every AI release.

## 16. Platform Independence

Core Skills are platform-agnostic. Platform-specific instructions live under `adapters/`.

A platform adapter may translate the same Skill into the native conventions of ChatGPT, Gemini, Claude, Jules, or another supported environment without changing the core Skill contract.

## 17. Verification and Trust

Verification intensity should match task risk and uncertainty.

```text
Low risk
→ lightweight sanity check

Medium risk
→ source / calculation / test verification

High risk
→ explicit evidence, stronger verification, and human review
```

AI must clearly distinguish known facts, user-provided information, assumptions, calculations, and uncertainty.

## 18. Human-in-the-Loop

AI may proceed autonomously for low-risk reversible drafting and organization tasks.

Human approval is required before consequential or externally visible actions such as publishing, sending important communications, merging important code, spending money, or changing sensitive information.

The more irreversible or consequential an action is, the stronger the approval requirement.

## 19. Artifact Lifecycle

Important work should produce durable artifacts whenever practical.

```text
Create
 ↓
Store
 ↓
Classify / Tag
 ↓
Link
 ↓
Reuse
 ↓
Review
 ↓
Archive / Retire
```

Examples:

- learning → notes, solved examples, quizzes
- research → evidence brief, synthesis, references
- project → code, docs, demo, portfolio case study
- English → writing samples, speaking logs, corrections
- content → post, script, media plan
- planning → tasks, calendar entries, next actions

The same artifact may be reused across contexts only when its content and privacy boundary permit it.

## 20. Output Multiplication

When practical, one meaningful activity should generate multiple downstream assets.

Example:

```text
Build project feature
 ↓
Code + commit
 ↓
Documentation
 ↓
Learning note
 ↓
Portfolio evidence
 ↓
Content idea / post
 ↓
Potential business proof
```

This is a core strategy for combining university, portfolio, content, and side-income development without requiring separate time blocks for every output.

## 21. Skill Lifecycle

Production Skills follow:

```text
Idea → Draft → Test → Active → Improving → Deprecated → Archived
```

Every meaningful Skill update should include versioning and, where applicable, regression evaluation.

## 22. Evaluation

A Skill is production-ready only when representative behavior can be tested.

Evaluation should include:

- normal cases
- edge cases
- failure cases
- safety / boundary cases
- regression cases

Evaluation measures behavior, not prose quality.

## 23. Observability and Metrics

The OS should measure outcomes rather than activity volume.

Primary dimensions:

- Learning: comprehension, retention, successful independent performance
- Productivity: time saved and reduced task friction
- Building: completed features/projects and engineering depth
- Portfolio: durable evidence produced
- Content: consistent output and learning from audience response
- Business: validated opportunities, clients, and revenue experiments
- AI usage: usefulness, quality, verification rate, and signs of unhealthy dependence

Metrics are feedback signals, not absolute definitions of success.

## 24. Core Context Boundaries

The following remain explicitly separated:

- UNIVERSITY
- COMPANY WORK
- PERSONAL BUSINESS / FREELANCE
- CONTENT / PERSONAL BRAND
- PRIVATE LIFE

Cross-context use requires explicit user intent. Company context has the strongest isolation requirement.

## 25. Initial Product/Tool Philosophy

Gemini Notebook, Google Workspace, Jules, Google Cloud, Gemini Spark, Flow, MCP, and advanced agent automation are capabilities to be evaluated against workflows. They are not architectural foundations by themselves.

Initial architecture remains usable without any single vendor tool.

## 26. Deferred Capabilities

These are future implementation layers, not initial dependencies:

- AI agent orchestration
- MCP
- advanced automation
- Gemini Spark workflows
- Google Cloud workflows
- broad platform-specific automation

AI Context Orchestrator integration as a Skill Factory is explicitly deferred to a later phase and is not part of the current architecture.

## 27. Architecture Freeze Rule

This specification is considered the conceptual baseline for AI OS v1.0. Future changes should be driven by observed failure, new requirements, or validated workflow improvements—not by speculative complexity.

The next phase is implementation: build and evaluate the first production Skill against this architecture.
