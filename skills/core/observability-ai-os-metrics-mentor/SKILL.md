# Observability & AI OS Metrics Mentor

- **Skill ID:** `observability-ai-os-metrics-mentor`
- **Type:** Core / Observability / Metrics / AI OS Operations
- **Status:** Draft
- **Version:** 1.0.0

## Mission

Help Yasfiq AI OS understand what is happening inside its workflows, Skills, tools, automations, and AI-assisted processes so problems can be detected, explained, measured, and improved without turning the system into a metric-collection exercise.

## Core Principle

**Goal → Instrument → Observe → Measure → Diagnose → Verify → Improve → Review**

Observability exists to support reliable outcomes, not to maximize dashboards, logs, or telemetry volume.

## Scope

This Skill covers:

- AI OS observability design
- workflow and Skill execution traces
- task outcome metrics
- tool/MCP usage metrics
- latency and cost measurement
- error and failure classification
- verification and trust events
- human approval/override events
- automation reliability
- learning/productivity/building metrics
- regression detection
- dashboards and reports
- event schemas and telemetry boundaries
- privacy-aware logging
- incident diagnosis and retrospectives
- metric lifecycle and governance

## Non-Goals

This Skill must not:

- optimize for vanity metrics such as number of AI chats or tool calls
- collect sensitive data without a legitimate purpose
- log secrets, credentials, private tokens, or unnecessary personal data
- treat a metric as proof of causality without appropriate evidence
- create instrumentation whose maintenance cost exceeds its value without justification
- hide failures by manipulating definitions
- optimize a local metric while harming the overall user outcome
- make consequential decisions solely from incomplete telemetry

## Observability Model

Use three complementary layers:

### 1. Events

What happened?

Examples:

- task started
- Skill selected
- workflow step completed
- tool called
- tool failed
- verification performed
- approval requested
- approval granted/rejected
- artifact created
- task completed

### 2. Metrics

How often, how long, how much, or how reliably?

Examples:

- task success rate
- workflow completion rate
- tool error rate
- verification failure rate
- latency
- cost
- retry rate
- approval rate
- rework rate

### 3. Traces / Context

Why did the workflow behave this way?

Capture enough structured context to reconstruct important execution paths while respecting privacy and context isolation.

## AI OS Outcome Hierarchy

Prefer metrics in this order:

1. **Outcome** — did the user's intended result happen?
2. **Quality** — was the result correct, useful, grounded, and appropriate?
3. **Reliability** — did the workflow behave consistently?
4. **Efficiency** — how much time, cost, latency, and effort were required?
5. **Activity** — how much AI/tool/system activity occurred?

Activity is useful for diagnosis but should rarely be the primary success metric.

## Core Metrics

### Task

- task success rate
- task completion rate
- task abandonment rate
- rework rate
- time to completion
- user correction rate

### AI Output

- correctness
- groundedness
- instruction adherence
- hallucination/error rate where measurable
- user acceptance/edit rate
- regression rate

### Workflow

- workflow success rate
- step failure rate
- retry rate
- blocked-step rate
- handoff failure rate
- recovery success rate

### Tool / MCP

- tool-call success rate
- tool latency
- tool timeout rate
- unnecessary tool-call rate
- tool-selection error rate
- permission/authorization failures
- tool output verification failures

### Automation

- run success rate
- trigger reliability
- duplicate execution rate
- idempotency failures
- retry exhaustion
- mean time to recovery

### Human-in-the-Loop

- approval rate
- rejection rate
- override rate
- correction-after-approval rate
- approval latency
- escalation rate

### AI OS Personal Outcomes

Measure outcomes across relevant domains such as:

- learning progress
- demonstrated mastery
- engineering projects completed
- portfolio evidence created
- useful content produced
- validated income opportunities
- time saved on repetitive work
- quality of work delivered

Do not equate more activity with more progress.

## Event Schema

Important events should be structured consistently. A minimal event may contain:

- timestamp
- session/workflow identifier
- task type
- context identifier
- Skill identifier
- workflow step
- event type
- outcome/status
- verification state
- tool identifier when applicable
- latency/duration when applicable
- cost when measurable
- error class when applicable

Do not include secrets or unnecessary sensitive payloads.

## Context Isolation

Telemetry must preserve boundaries between:

- University
- Employer / Company
- Freelance / Client
- Personal
- Business
- Public Portfolio
- Open Source

Do not aggregate confidential employer/client data into personal analytics merely because the data passed through an AI workflow.

## Privacy-Aware Logging

Before logging data, ask:

1. Why is this data needed?
2. Can a less sensitive representation answer the same question?
3. How long should it be retained?
4. Who should access it?
5. Is it safe to include in a trace?
6. Could it expose secrets, private content, or third-party information?

Prefer metadata and classifications over raw sensitive content.

## Failure Taxonomy

Classify failures so they can be acted upon:

- intent misunderstanding
- context missing
- stale/conflicting context
- wrong Skill
- wrong mode
- workflow design error
- tool selection error
- tool/API failure
- permission failure
- model/output error
- verification failure
- human approval rejection
- external-system failure
- timeout
- data-quality issue
- configuration error
- unknown

Do not collapse all failures into a generic "AI error."

## Diagnosis Workflow

When a workflow underperforms:

1. define the expected outcome
2. identify the observed failure
3. inspect the execution path
4. classify the failure
5. locate the earliest meaningful deviation
6. determine whether the issue is context, Skill, workflow, tool, model, data, or human decision
7. verify the diagnosis
8. apply the smallest useful change
9. rerun representative cases
10. monitor for regression

## Metric Design Rules

Every important metric should have:

- name
- definition
- numerator/denominator when relevant
- unit
- source
- collection method
- context/scope
- expected interpretation
- known limitations
- owner/use
- review cadence

Avoid ambiguous metrics such as "AI quality" without a defined measurement method.

## Baselines and Comparisons

A metric becomes useful when compared against a meaningful baseline:

- before vs after
- current vs historical
- workflow A vs workflow B
- manual vs assisted
- model/tool version changes
- expected vs actual

Keep populations and time windows consistent when comparing results.

## Causality Discipline

A metric changing after a system change does not automatically prove that the change caused it.

When causal claims matter, use stronger evidence such as controlled comparisons, repeated tests, or appropriate experiments through `ai-evaluation-mentor` and `data-analytics-mentor`.

## Dashboards

A dashboard should answer concrete operational questions, such as:

- Is the system working?
- Where is it failing?
- What changed?
- What is expensive or slow?
- Which workflows need attention?
- Are users correcting the system frequently?
- Are verification or approval gates working?

Avoid dashboards that merely display every available metric.

## Regression Monitoring

After changing a Skill, workflow, model, tool, MCP server, or prompt:

1. identify affected behaviors
2. select representative test cases
3. compare against the baseline
4. inspect quality and reliability changes
5. check cost/latency impact
6. check security/privacy impact
7. approve the change only when evidence is sufficient

Coordinate with `ai-evaluation-mentor` for formal regression evaluation.

## Incident Handling

For meaningful failures:

**Detect → Contain → Diagnose → Verify → Recover → Document → Prevent recurrence**

Do not silently modify logs or erase evidence needed to understand an incident.

For production or consequential systems, human ownership remains explicit.

## Coordination With Other Skills

- `ai-os-orchestrator` — provides execution structure to observe.
- `workflow-orchestration-mentor` — defines workflow steps and checkpoints.
- `tool-mcp-strategy-mentor` — provides tool-selection and tool-risk context.
- `verification-trust-manager` — provides verification/trust states.
- `ai-evaluation-mentor` — provides systematic evaluation and regression methods.
- `automation-mentor` — provides automation execution and reliability context.
- `ai-architecture-mentor` — designs system-level observability boundaries.
- `data-analytics-mentor` — analyzes collected metrics and trends.
- `context-engineering-mentor` — governs what context enters telemetry.
- `memory-management-mentor` — governs durable information and retention considerations.
- `decision-making-critical-thinking-mentor` — prevents metric-driven reasoning errors.

## Artifact Contract

Useful outputs include:

- observability specification
- event schema
- metric dictionary
- workflow trace format
- dashboard specification
- failure taxonomy
- incident report
- regression report
- weekly/monthly AI OS health report
- metric review decision record

## Human-in-the-Loop

Require human review for consequential interpretation or action, including:

- production remediation
- deletion or retention changes involving important data
- changes to privacy boundaries
- security-sensitive telemetry changes
- major architecture changes
- decisions that materially affect university, employment, finances, clients, or public reputation

AI may detect and explain signals, but the user retains final authority for consequential decisions.

## Session Closure

End an observability task with:

- intended outcome
- observed state
- important metrics
- failures/anomalies
- diagnosis
- verification status
- changes made
- unresolved uncertainty
- artifact created/updated
- next monitoring action

## Metrics for This Skill

Measure whether observability itself is useful:

- time to detect failures
- time to diagnose failures
- percentage of actionable alerts
- false-alert rate
- telemetry cost
- instrumentation maintenance burden
- percentage of important workflows with meaningful visibility
- regression detection effectiveness

Do not optimize for telemetry volume.

## Evolution

Lifecycle:

**Idea → Draft → Test → Active → Improve → Deprecated → Archived**

Evolve the Skill when real operational evidence shows that a metric, event, dashboard, or diagnostic method improves reliability or decision quality.