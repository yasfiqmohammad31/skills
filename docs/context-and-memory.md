# Context and Memory Model

## Purpose

Define how Yasfiq AI OS decides what information is active, persistent, temporary, or forbidden.

## Context Layers

```text
GLOBAL
├── identity
├── stable_goals
├── preferences
└── principles

DOMAIN
├── university
├── business
├── content
├── private_life
└── company_work (isolated)

TASK
├── course
├── assignment
├── project
├── research
└── content_task

SESSION
└── current interaction
```

## Loading Rule

Use least-necessary-context. A Skill receives the minimum context required to execute the request well.

## Boundaries

- University context may inform academic Skills, but does not automatically expose business or company information.
- Business/freelance context may inform product and monetization Skills, but does not automatically expose company information.
- Content context may reuse public-safe lessons, project outcomes, and portfolio evidence only when intended.
- Company context is isolated and must not be imported into personal Skills by default.
- Private-life context is used only where necessary for personal planning and should not leak into unrelated outputs.

## Memory Classes

### Stable
Long-lived identity, preferences, durable goals, and enduring constraints.

### Domain
Conventions and stable information belonging to one domain.

### Project
Current project decisions, architecture, milestones, and status.

### Session
Temporary working state for the active interaction.

### Ephemeral
Facts needed only for the immediate step.

## Memory Rules

1. Do not store every conversation.
2. Store summaries, decisions, preferences, and durable facts rather than raw transcripts.
3. Never store credentials, secrets, private keys, passwords, or authentication tokens.
4. Mark stale information for review or retirement.
5. Do not promote temporary task context to long-term memory without justification.
6. Company information stays isolated.

## Context Escalation

When a task needs information outside the currently active context:

```text
Need detected
→ Check whether safe and necessary
→ Ask explicit user intent if cross-context
→ Load only the required slice
→ Execute
→ Do not persist unless intentionally requested
```

## Context Injection Format

A future adapter should be able to represent context using a compact structure:

```yaml
context:
  domain:
  subject:
  task_type:
  active_project:
  constraints: []
  relevant_artifacts: []
  user_preferences: []
  risk_level:
```

## Key Principle

Context should make the AI more relevant without making it omniscient. More context is not automatically better context.
