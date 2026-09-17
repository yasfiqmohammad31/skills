# Tool Registry and Trust Model

## Purpose

Keep tool selection explicit, comparable, and replaceable. The AI OS should not become dependent on one vendor simply because it is currently convenient.

## Tool Registry Entry

```yaml
name:
category:
status:
best_for: []
not_for: []
cost:
platform:
inputs: []
outputs: []
privacy:
latency:
skill_compatibility: []
notes:
```

## Tool Selection Criteria

Evaluate tools against:

1. Workflow fit
2. Output quality
3. Reliability
4. Privacy / data handling
5. Cost
6. Speed / latency
7. Integration effort
8. Portability / lock-in
9. User learning curve

No single criterion is automatically dominant; the workflow determines the trade-off.

## Trust / Verification Levels

### Level 0 — Draft
Low-risk generation where factual accuracy is not central.

### Level 1 — Sanity Check
Basic consistency, formatting, or arithmetic check.

### Level 2 — Evidence / Test
Requires source checking, calculation verification, code execution, or another concrete test.

### Level 3 — Strong Verification
Multiple evidence checks, explicit uncertainty, and human review for consequential decisions.

## Human Approval Policy

Approval is required for actions that are:

- externally visible
- financially consequential
- difficult to reverse
- privacy-sensitive
- capable of changing important systems

Examples: publishing content, sending important email, merging significant code, purchasing, changing access, or exposing private data.

## New Tool Intake

```text
Discover
→ Compare with existing workflow
→ Test on one representative task
→ Record result
→ Adopt / Monitor / Ignore
```

## Vendor Independence

A new tool can be introduced through `adapters/` without changing the core Skill specification whenever possible.

## Current Strategic Tools

The OS is designed to work with tools such as ChatGPT, Gemini, Gemini Notebook, Google Workspace, Jules, Google Cloud, Gemini Spark, and Google Flow when they are relevant. Their current product capabilities should be verified at implementation time because products evolve.

AI Context Orchestrator remains outside the current Skill Factory design and is explicitly deferred.
