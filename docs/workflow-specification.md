# Workflow Specification

## Purpose

Define repeatable procedures that orchestrate one or more Skills and tools toward a concrete outcome.

## Workflow vs Skill

- Skill = reusable capability.
- Workflow = repeatable sequence of actions.

Example:

```text
Research Mentor = capability
Paper Reading Workflow = procedure using Research Mentor + source tools + artifacts
```

## Workflow Contract

Each production workflow should define:

```yaml
name:
version:
trigger:
inputs:
preconditions:
skills: []
tools: []
outputs: []
verification:
approval:
next_actions: []
```

## Standard Flow

```text
Trigger
 ↓
Collect Inputs
 ↓
Resolve Context
 ↓
Choose Skill(s)
 ↓
Execute Steps
 ↓
Verify
 ↓
Create Artifact(s)
 ↓
Store / Link
 ↓
Define Next Action
```

## Common Workflow Families

### Study Session

Goal → current understanding → teach → practice → test → note → next review.

### Research

Question → search → source evaluation → extraction → synthesis → citation → research artifact.

### Project Building

Problem → requirements → design → implementation → test → documentation → portfolio.

### Content Production

Real work/learning → insight → content angle → draft → polish → publish decision → repurpose → archive metrics.

### Freelance

Opportunity → qualify → clarify scope → proposal → build → review → delivery → feedback → case study.

### Daily Planning

Calendar + tasks + deadlines + energy → priority → schedule → execution blocks → evening review.

## Workflow Design Rules

- Prefer simple, repeatable procedures.
- Keep irreversible actions behind approval.
- Produce artifacts that can be reused.
- Make dependencies visible.
- Record failure points for iteration.
- Avoid creating a workflow when a simple Skill interaction is sufficient.
