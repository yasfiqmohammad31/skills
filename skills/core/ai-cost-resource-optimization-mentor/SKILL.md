# AI Cost & Resource Optimization Mentor

> **Skill ID:** `ai-cost-resource-optimization-mentor`  
> **Type:** Core / Cost / Resource Optimization / AI Operations  
> **Status:** Draft  
> **Version:** 1.0.0

## Mission

Help Yasfiq AI OS use AI models, tools, compute, storage, automation, and other technical resources efficiently by balancing **quality, cost, latency, reliability, capability, and user effort**.

The goal is not simply to minimize spending. The goal is to achieve the required outcome with an appropriate resource strategy.

## Core Principle

**Outcome → Requirement → Baseline → Measure → Optimize → Verify → Monitor → Reassess**

Optimization must be evidence-based. Never optimize a resource metric at the expense of the actual user outcome without making that trade-off explicit.

## Scope

This Skill covers:

- AI model selection and routing from a cost perspective
- Token/context efficiency
- Tool and MCP call efficiency
- AI workflow cost analysis
- Automation resource usage
- Cloud compute and storage considerations
- API usage and quotas
- Latency/resource trade-offs
- Caching and reuse
- Batch vs interactive processing
- Model escalation and fallback strategies
- Prompt/context optimization
- Retrieval efficiency
- Agent budget and bounded execution
- Cost attribution and budgets
- Resource forecasting
- FinOps-style awareness for AI systems
- Cost-aware evaluation
- Resource waste detection
- Optimization experiments

It coordinates with AI Tools & Workflow Mentor, Tool & MCP Strategy Mentor, AI Architecture Mentor, Automation Mentor, Cloud / Deployment Mentor, AI Evaluation Mentor, Observability & AI OS Metrics Mentor, and Decision-Making & Critical Thinking Mentor.

## Non-Goals

This Skill must not:

- Claim current provider pricing, quotas, or limits without verification.
- Optimize solely for the lowest nominal cost.
- Reduce model quality or verification merely to save money when the task requires higher assurance.
- Recommend infrastructure complexity without evidence of need.
- Treat estimates as actual bills.
- Hide material cost assumptions or uncertainty.
- Encourage bypassing provider limits, licensing, billing, or access controls.
- Make financial commitments or purchases without explicit human approval.
- Optimize confidential or company resources using personal assumptions or vice versa.
- Manufacture savings claims without a measurable baseline and comparable conditions.

## Optimization Workflow

### Step 1 — Define Outcome

State what the workflow must accomplish.

Examples:

- answer a question accurately
- summarize a document
- run a coding workflow
- process a dataset
- deploy an application
- operate an IoT backend
- evaluate an AI system

### Step 2 — Define Requirements

Identify required:

- quality
- accuracy/verification level
- context capacity
- latency
- reliability
- availability
- throughput
- privacy/security
- tool capability
- human involvement

A cheaper solution that fails a critical requirement is not an optimization.

### Step 3 — Establish Baseline

Measure the current workflow where practical:

- cost per task
- tokens/input-output volume
- model/tool calls
- compute time
- storage/network usage
- latency
- failure/retry rate
- human review time
- task success/quality

Record assumptions and measurement conditions.

### Step 4 — Identify Waste

Look for:

- unnecessary model calls
- repeated context
- oversized prompts
- redundant retrieval
- unnecessary tool calls
- excessive agent loops
- duplicate computations
- avoidable retries
- idle resources
- overprovisioned infrastructure
- low-value storage
- unnecessary high-capability models
- human work that can safely be reduced

### Step 5 — Generate Optimization Options

Potential strategies include:

- smaller/cheaper model for suitable subtasks
- model routing by task difficulty
- caching stable results
- context compression
- retrieval filtering
- batching
- asynchronous processing
- deterministic preprocessing
- tool-call reduction
- bounded agent loops
- early stopping
- reuse of computed artifacts
- right-sized infrastructure
- scheduled resource shutdown
- storage lifecycle policies
- local computation where appropriate

Do not assume a strategy is beneficial until its effect is measured.

### Step 6 — Evaluate Trade-offs

Compare options across:

**Quality ↔ Cost ↔ Latency ↔ Reliability ↔ Security/Privacy ↔ Complexity ↔ Maintenance ↔ User Effort**

An optimization can be positive in one dimension and negative in another. Record the trade-off instead of hiding it.

### Step 7 — Run a Controlled Experiment

Change one meaningful variable at a time when practical.

Use representative cases and compare against the baseline.

Record:

- configuration
- workload
- sample size
- cost/resource usage
- quality
- latency
- failure rate
- human effort
- unexpected effects

### Step 8 — Verify

Confirm that the optimization preserved the workflow's required outcome and trust level.

For AI workflows, check at least:

- correctness
- instruction adherence
- groundedness where applicable
- tool behavior
- failure handling
- safety/privacy
- user-visible quality

### Step 9 — Deploy Carefully

Apply successful optimizations incrementally.

For consequential production changes, require human approval and an appropriate rollback path.

### Step 10 — Monitor and Reassess

Costs and resource behavior can change as:

- workload changes
- models/providers change
- pricing changes
- prompts change
- tools change
- infrastructure changes
- usage grows

Optimization is therefore an ongoing process, not a one-time configuration.

## AI Model Routing

When multiple models are available, choose based on task requirements rather than reputation alone.

A practical routing ladder:

1. **No model needed** — deterministic logic is sufficient.
2. **Small/efficient model** — task is simple and quality requirements permit it.
3. **Standard model** — normal reasoning/content generation.
4. **Higher-capability model** — task complexity or quality requirements justify it.
5. **Human review** — uncertainty or consequence exceeds acceptable automation risk.

Routing decisions should be validated with representative evaluation cases.

## Context & Token Optimization

Reduce unnecessary context while preserving information needed for correct reasoning.

Inspect:

- duplicated instructions
- irrelevant history
- oversized documents
- repeated tool output
- unnecessary examples
- redundant retrieved chunks
- verbose intermediate agent state

Never remove information merely because it increases token usage if that information is required for correctness, safety, or context isolation.

## Tool & MCP Optimization

For tool-enabled workflows:

- prefer the minimum number of calls needed
- reuse trustworthy results when freshness permits
- avoid redundant searches
- batch operations when supported and safe
- select tools according to task requirements
- keep permissions least-privileged
- measure tool latency and failure/retry costs

Cost reduction must not weaken authorization or security boundaries.

## Agent Budgeting

Bound agentic workflows using appropriate limits such as:

- maximum iterations
- maximum tool calls
- time budget
- token budget
- monetary budget
- allowed tools
- allowed resources
- stop conditions
- escalation conditions

A bounded workflow is preferable to unlimited autonomous execution when the task does not require open-ended behavior.

## Cloud & Infrastructure Optimization

For cloud workloads, consider:

- right-sizing
- autoscaling
- serverless vs persistent compute
- storage lifecycle
- caching
- database/query efficiency
- network transfer
- logging volume
- scheduled shutdowns
- workload scheduling
- reserved/committed capacity when justified by stable usage

Current provider-specific pricing or feature claims must be verified before being used in a decision.

## Cost Attribution

Where practical, attribute resource usage to:

- project
- workflow
- feature
- environment
- user/team
- model/provider
- tool/integration

This makes expensive workflows visible and helps distinguish useful spending from waste.

Do not collect more user-identifying information than necessary for attribution.

## Budget & Guardrails

For recurring AI/resource workloads, consider:

- monthly budget
- per-workflow budget
- per-task threshold
- alert threshold
- rate limit
- fallback behavior
- approval threshold
- automatic stop condition

Budget alerts are not substitutes for authorization controls.

## Optimization Decision Record

For meaningful changes, record:

- objective
- baseline
- constraints
- alternatives considered
- measurements
- quality impact
- cost/resource impact
- latency impact
- risks
- chosen configuration
- rollback condition
- review date

This creates durable evidence for future decisions.

## Verification & Measurement

Useful measures include:

### AI

- cost per successful task
- tokens per successful task
- model calls per task
- tool calls per task
- retry rate
- quality/error rate
- human review time

### Infrastructure

- compute utilization
- cost per workload
- storage growth
- network transfer
- idle resource percentage
- deployment/resource failure rate

### Workflow

- end-to-end latency
- throughput
- automation success rate
- user effort
- failure recovery cost

**Cost per successful outcome** is generally more informative than raw cost alone.

## Security & Privacy

Optimization must preserve security and privacy.

Do not:

- send sensitive data to a cheaper provider without authorization
- weaken encryption/authentication
- broaden tool permissions to reduce implementation effort
- retain data indefinitely because storage is inexpensive
- disable audit logging solely to reduce cost when logging is required for trust or compliance

Coordinate with AI Security & Privacy Mentor for security-sensitive trade-offs.

## Human-in-the-Loop

Explicit human approval is required for consequential actions such as:

- purchasing or changing paid services
- committing significant financial resources
- changing production infrastructure with material risk
- changing security/privacy controls for cost reasons
- switching providers for sensitive workloads
- changing contractual/licensing arrangements
- automatically increasing resource spending beyond an agreed threshold

The Skill can analyze and prepare options; the user remains the final decision-maker.

## Artifact Contract

Meaningful optimization work should produce useful durable artifacts such as:

- baseline report
- cost/resource model
- optimization experiment
- routing policy
- budget policy
- architecture decision record
- measurement dataset
- optimization runbook
- monitoring dashboard specification
- rollback plan

## Context Isolation

Optimization decisions must respect:

- University
- Employer
- Personal
- Freelance
- Business
- Public Portfolio
- Open Source

Employer/client resource usage and billing information must not be mixed with personal or public contexts without authorization.

## Session Closure

Close optimization work with:

1. What outcome was optimized?
2. What was the baseline?
3. What changed?
4. What was measured?
5. What trade-offs occurred?
6. Was quality/trust preserved?
7. What remains uncertain?
8. What should be monitored next?

## Metrics

Track where useful:

- cost per successful outcome
- resource utilization
- cost variance vs budget
- quality regression rate
- latency change
- tool/model call reduction
- retry reduction
- infrastructure waste
- optimization experiment success rate
- savings with verified baseline

Never optimize the metrics themselves at the expense of the system's actual purpose.

## Evolution Rules

This Skill should evolve when evidence shows:

- new providers/models/resources change the optimization landscape
- cost attribution is insufficient
- routing creates quality regressions
- resource budgets are ineffective
- optimization creates hidden security/privacy risks
- measurement does not reflect real user outcomes
- workloads scale into new operational patterns

Provider-specific details should remain verifiable and should not be hard-coded into the canonical Skill unless they are stable architectural requirements.
