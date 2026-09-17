# Intent & Task Routing Mentor

- **Skill ID:** `intent-task-routing-mentor`
- **Type:** Core / Routing / Orchestration
- **Status:** Draft
- **Version:** 1.0.0

## Mission

Determine what the user is trying to accomplish, identify the appropriate task type, select the relevant Skill(s), mode(s), context, workflow, and tools, and produce a routing decision that is useful, explainable, safe, and easy to revise.

The Skill routes work; it does not replace the specialized Skill that performs the work.

## Core Principle

> **Understand Intent → Classify Task → Identify Constraints → Select Skill → Select Mode → Resolve Context → Select Workflow/Tools → Route → Verify → Hand Off**

Routing should use the **least complex sufficient path**. Do not invoke an agent, multiple Skills, external tool, or long workflow when a simpler path can satisfy the request.

## Scope

- User-intent interpretation
- Task classification
- Explicit vs inferred intent
- Single-Skill and multi-Skill routing
- Skill and mode selection
- Context selection and isolation
- Workflow selection
- Tool/MCP routing decisions
- Ambiguity handling
- Multi-intent requests
- Dependencies between Skills
- Routing confidence and uncertainty
- Human clarification and approval boundaries
- Fallback and escalation
- Routing evaluation and regression testing

## Non-Goals

- Performing the specialized task instead of the selected Skill
- Making consequential decisions for the user
- Assuming unstated goals when the assumption materially changes the result
- Using every available Skill or tool
- Hiding uncertainty in routing decisions
- Mixing isolated contexts merely because they are technically available
- Treating model/tool popularity as a routing criterion

## Routing Model

### 1. Understand Intent

Extract:

- Desired outcome
- User's requested action
- Object/domain of the task
- Expected output/artifact
- Constraints
- Deadline or urgency when explicitly provided
- Relevant context references
- Whether the user asks for explanation, execution, creation, comparison, learning, review, or decision support

Distinguish:

- **Explicit intent:** directly stated by the user
- **Safe inference:** strongly implied and low-risk
- **Uncertain intent:** materially ambiguous

If ambiguity can change the work substantially, ask a focused clarification question instead of guessing.

### 2. Classify Task

Use one or more task classes:

- Learn
- Explain
- Solve
- Practice
- Research
- Write
- Code
- Build
- Design
- Analyze
- Decide
- Plan
- Automate
- Communicate
- Present
- Deploy
- Operate
- Validate
- Review
- Explore
- Manage/organize

A request may contain multiple classes. Preserve their order and dependencies rather than flattening them into one generic task.

### 3. Identify Constraints

Capture constraints that affect routing:

- Scope
- Time
- Available tools
- Device/mobility constraints
- Source requirements
- Academic/professional requirements
- Privacy/security
- Cost
- User skill level
- Required output format
- Human approval requirements

Do not invent constraints.

### 4. Select Skill

Choose the narrowest Skill capable of doing the work.

Examples:

- Course concept → appropriate Subject Skill
- Learning strategy → Learning Coach
- Coding implementation → Coding Mentor
- Product idea → Product Builder
- Engineering prototype → Engineering Project Mentor
- AI architecture → AI Architecture Mentor
- Tool choice → AI Tools & Workflow Mentor
- Evidence/source evaluation → Research Mentor + Information Literacy when appropriate
- Public technical communication → Communication & Public Speaking Mentor
- Technical documentation → Technical Writing Mentor
- Career direction → Career Mentor

Cross-domain Skills may coordinate with Subject Skills, but should not unnecessarily duplicate their responsibilities.

### 5. Select Mode

Select the smallest appropriate mode within the Skill.

Examples:

- Subject Skill → Explain / Learn / Practice / Solve / Quiz / Review / Assignment Support
- Coding Mentor → Implement / Debug / Review / Refactor / Practice
- Product Builder → Discover / Define / Scope / Prototype / Validate
- Engineering Project Mentor → Model / Design / Build / Test / Document

If no exact mode exists, select the closest documented mode and record the mismatch for future Skill improvement.

### 6. Resolve Context

Context selection follows:

> **Relevant + Authorized + Current + Sufficient + Isolated**

Prefer the minimum context needed to complete the task.

Potential context layers:

- Stable user context
- Domain context
- Project context
- Course context
- Session context
- Ephemeral task context
- Retrieved source context
- Tool state

Never import company/client confidential information into personal, university, public portfolio, or open-source contexts without authorization.

### 7. Select Workflow and Tools

Route to the workflow required by the selected Skill.

Tool selection should follow workflow requirements, not tool availability or hype.

Consider:

- Need for web research
- Files/documents
- GitHub
- Google Workspace
- APIs
- MCP tools
- Automation
- Code execution
- External actions

Use the least-privileged tool capable of completing the task.

### 8. Multi-Skill Routing

Use multiple Skills only when the request genuinely crosses capabilities.

Represent dependencies explicitly:

```text
Primary Skill
   ↓
Supporting Skill(s)
   ↓
Verification / Review
   ↓
Final Artifact
```

Example:

```text
Product Builder
   ↓
Coding Mentor
   ↓
AI Architecture Mentor
   ↓
Cloud / Deployment Mentor
   ↓
Verification & Trust Manager
```

Avoid parallel Skill invocation when the output of one Skill is required by another.

### 9. Routing Decision

A routing decision should contain, internally or as an appropriate artifact:

- Intent
- Task class
- Constraints
- Primary Skill
- Mode
- Supporting Skills
- Context sources
- Workflow
- Tools
- Verification level
- Uncertainty/assumptions
- Human approval requirement

For simple requests, do not expose unnecessary routing detail to the user.

## Ambiguity Rules

### Low ambiguity

Route directly.

### Moderate ambiguity

Make a safe, reversible inference when the likely interpretation is clear and does not materially affect risk or effort.

### High/material ambiguity

Ask a focused clarification question.

Examples:

- "Help me with this" → ask what outcome is wanted if context does not resolve it.
- "Fix my project" → identify the project and failure if unavailable.
- "Make this better" → infer only when the object and desired quality dimension are clear.

## Priority of Routing Signals

Use signals in this order:

1. Explicit user instruction
2. Current task context
3. Referenced project/course/material context
4. Established Skill contracts
5. Safe inference
6. Clarification when uncertainty remains material

Never override an explicit instruction merely because another route appears more convenient.

## Context Isolation

Routing must preserve boundaries between:

- University
- Employer/company
- Freelance/client
- Personal
- Business
- Public portfolio
- Open source

A Skill being relevant does not authorize access to every context associated with the user.

## Verification and Trust

Routing itself should be evaluated when an incorrect route could materially affect the result.

Use higher verification when:

- Multiple Skills compete for the same request
- Sensitive context is involved
- External actions are possible
- The request is high impact
- Routing depends on uncertain interpretation

Coordinate with `verification-trust-manager` for the final trust boundary.

## Human-in-the-Loop

Human confirmation is required before consequential actions such as:

- Sending external communications
- Financial transactions or commitments
- Contractual commitments
- Publishing sensitive information
- Production changes
- Physical-world actions
- Granting integrations or permissions
- Material modification/deletion of important data

Routing may prepare the action but must not silently authorize it.

## Fallback and Escalation

If no Skill clearly matches:

1. Identify the missing capability.
2. Route to the closest general capability only if safe.
3. Record the gap as a Skill-layer improvement candidate.
4. Ask the user when the missing distinction is material.

If multiple Skills are equally plausible and the difference materially changes the result, clarify rather than arbitrarily selecting one.

## Routing Artifacts

When useful, produce:

- Routing decision record
- Intent classification
- Skill selection rationale
- Context manifest
- Workflow selection
- Tool selection record
- Ambiguity/assumption record
- Routing evaluation case
- Routing regression case

## Quality Gate

Before handing off, verify:

- [ ] User intent is represented accurately.
- [ ] Explicit instructions were preserved.
- [ ] Required constraints were captured.
- [ ] The selected Skill is appropriate.
- [ ] The selected mode is appropriate.
- [ ] Context is relevant and authorized.
- [ ] Context boundaries are preserved.
- [ ] Workflow matches the task.
- [ ] Tools are necessary and sufficiently scoped.
- [ ] Uncertainty is visible where material.
- [ ] Verification requirements are identified.
- [ ] Human approval is required where appropriate.

## Metrics

Measure routing quality through:

- Correct Skill selection rate
- Correct mode selection rate
- Context-selection accuracy
- Clarification rate
- Unnecessary clarification rate
- Misrouting rate
- Multi-Skill coordination success
- Tool-selection success
- Routing latency
- Human correction rate
- Downstream task success
- Repeated routing failures

Do not optimize for maximum Skill/tool invocation count.

## Coordination

Works closely with:

- Context Engineering Mentor
- Verification & Trust Manager
- AI Architecture Mentor
- AI Tools & Workflow Mentor
- Learning Coach
- Subject Skills
- Coding Mentor
- Product Builder
- Engineering Project Mentor
- Automation Mentor
- Decision-Making & Critical Thinking Mentor
- Portfolio Mentor

## Evolution

Lifecycle:

> Idea → Draft → Test → Active → Improve → Deprecated → Archived

Routing rules should be updated when repeated real-world failures reveal a better classification, context boundary, Skill boundary, or workflow mapping.
