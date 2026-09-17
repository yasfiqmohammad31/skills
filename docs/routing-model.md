# Routing Model

## Purpose

Route natural-language requests to the right context, Skill, workflow, tool, and verification path without requiring the user to memorize the internal architecture.

## Canonical Route

```text
User Request
 ↓
Intent Detection
 ↓
Context Detection
 ↓
Boundary Check
 ↓
Priority / Energy Check (if scheduling or task selection)
 ↓
Skill Match
 ↓
Workflow Match
 ↓
Tool Selection
 ↓
Execution
 ↓
Verification
 ↓
Approval (when required)
 ↓
Artifact / Action
```

## Intent Categories

Initial intents include:

- learn
- explain
- practice
- solve
- quiz
- review
- assignment
- research
- build
- debug
- plan
- organize
- create_content
- publish
- monetize
- communicate
- reflect

The list may grow as real usage reveals new recurring intents.

## Context Resolution

The router should identify:

```text
domain
subject
project
privacy boundary
risk
available device
available time
energy
```

When a user explicitly names a Skill or subject, preserve that choice unless it conflicts with a safety or boundary rule.

## Skill Selection

Match by capability first, then narrow by domain/subject.

Example:

```text
"Explain Kirchhoff's laws for tomorrow's IEE exam"
→ domain: university
→ subject: introduction-electrical-engineering
→ intent: exam_prep / explain
→ skill: IEE Subject Skill
→ supporting skills: learning coach
```

## Ambiguity Handling

Ask a concise question when two or more routes would produce materially different outcomes.

Examples of safe inference:

- "Make me a quiz on this" when an active subject is known.
- "Plan my evening" when date, available time, and active commitments are known.

Examples requiring clarification:

- "Write a report" without knowing topic or audience.
- "Use my work data" without specifying the company context and authorization.

## Tool Selection

The router chooses a tool based on workflow requirements, input/output needs, privacy, cost, and current availability. New or popular tools do not automatically become preferred tools.

## FOMO Filter

For a new AI tool:

```text
Discovery
→ Relevance to current goals?
→ Better than current workflow?
→ Low enough integration cost?
→ Safe to use?
→ Small test
→ Adopt / Monitor / Ignore
```

## User Override

The user may request a specific tool or Skill. The router should honor the request when feasible and safe, while noting if another route is materially better.

## Output of Router

Internally, the router should be able to resolve to a compact object such as:

```yaml
route:
  domain:
  context:
  intent:
  mode:
  skill:
  workflow:
  tools: []
  risk:
  approval_required: false
```

The internal structure is implementation guidance; the user should normally experience a natural conversation rather than raw routing data.
