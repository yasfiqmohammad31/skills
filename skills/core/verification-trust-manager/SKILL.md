# Verification & Trust Manager

- **Skill ID:** `verification-trust-manager`
- **Type:** Core / Verification / Trust / Safety
- **Status:** Draft
- **Version:** 1.0.0

## Mission

Help Yasfiq AI OS determine **how much verification is appropriate before an AI output, tool result, decision, or action is trusted or used**.

The Skill protects the user from treating fluent AI output as automatically correct while avoiding unnecessary verification overhead for low-risk tasks.

## Core Principle

**Claim/Action → Risk → Evidence → Verification → Confidence → Human Review → Use → Monitor**

Trust is contextual. An output is not simply “trusted” or “untrusted”; its acceptable level of verification depends on the task, evidence, uncertainty, and consequences of failure.

## Scope

This Skill covers:

- AI answer verification
- Fact checking
- Source verification
- Technical calculation checking
- Code verification
- Citation checking
- Document/PDF grounding checks
- Tool-result verification
- MCP/tool safety checks
- Agent action verification
- Data provenance
- Output confidence and uncertainty
- Human review thresholds
- High-risk workflow safeguards
- Verification checklists
- Regression and trust monitoring

## Non-Goals

This Skill must not:

- Claim certainty where evidence is insufficient.
- Treat model confidence or fluent wording as proof.
- Invent sources, citations, calculations, tests, or verification results.
- Apply the same verification level to every task.
- Encourage users to skip professional expertise in high-stakes domains.
- Silently approve consequential external actions.
- Turn an unverified AI output into a verified fact merely by repeating it.

## Verification Levels

Select the lightest level that is appropriate for the risk.

### Level 0 — No Formal Verification

Suitable for low-risk brainstorming, creative exploration, or non-factual drafting where correctness is not consequential.

### Level 1 — Plausibility Check

Check internal consistency, obvious contradictions, units, formatting, and whether the response actually addresses the request.

### Level 2 — Source Check

Verify important factual claims against appropriate sources.

### Level 3 — Independent Verification

Recalculate, reproduce, cross-check with another method, or compare against an independent reliable source.

### Level 4 — Test / Expert Review

Use reproducible testing, domain expertise, or controlled validation when failure has meaningful consequences.

### Level 5 — Human Authorization

Required before consequential actions even when supporting analysis has been verified.

Verification level is selected from risk, not from the apparent intelligence of the AI.

## Risk Assessment

Before deciding how much verification is needed, inspect:

- Consequence of error
- Likelihood of error
- Uncertainty
- Reversibility
- Data sensitivity
- External impact
- Regulatory/academic/professional requirements
- Whether an independent check is practical

Higher consequence or lower reversibility generally requires stronger verification.

## Claim Verification

For factual claims, distinguish:

- User-provided fact
- Verified fact
- Source-reported claim
- AI-generated inference
- Assumption
- Hypothesis
- Unknown

When evidence is available, identify the source and its relevance.

Do not collapse “a source says X” into “X is definitely true” when the source itself is uncertain, promotional, contested, or based on limited evidence.

Coordinate with `research-mentor` and `information-literacy`.

## Source Verification

Evaluate sources using relevant factors:

- Authority
- Primary vs secondary status
- Evidence quality
- Methodology
- Recency
- Relevance
- Independence
- Potential incentives/conflicts
- Agreement with independent sources

For technical components, engineering parameters, software APIs, and safety-sensitive specifications, prefer authoritative primary documentation where appropriate.

## Calculation Verification

For mathematics and engineering calculations:

1. Restate the known values.
2. Identify the governing equation/model.
3. Check units and dimensions.
4. Substitute values independently.
5. Check arithmetic.
6. Test order of magnitude.
7. Consider boundary conditions and assumptions.
8. Compare with an independent method when practical.

A plausible-looking numerical answer is not sufficient evidence.

Coordinate with relevant Subject Skills and `engineering-project-mentor`.

## Code Verification

For AI-generated or AI-assisted code, verify:

- Requirements
- Syntax/build
- Tests
- Edge cases
- Error handling
- Security
- Dependencies
- Data handling
- Integration behavior
- Project conventions
- Regression risk

The user should understand important generated code before relying on it.

Coordinate with `coding-mentor` and `open-source-github-mentor`.

## AI Output Verification

For generated answers, ask:

- What claims require verification?
- What evidence supports them?
- Could the model have misunderstood the context?
- Could information be outdated?
- Are there unsupported assumptions?
- Is the requested output complete?
- What would falsify the answer?

For important outputs, prefer evidence that is independent of the model's own generation.

## Document / RAG Verification

When an AI answer is based on supplied or retrieved documents, verify:

1. The cited passage exists.
2. The passage actually supports the claim.
3. Context has not been distorted.
4. Important qualifiers are preserved.
5. The answer does not introduce unsupported information.
6. The source version/date is appropriate when relevant.

Coordinate with `research-mentor`, `information-literacy`, and `ai-evaluation-mentor`.

## Tool / MCP Verification

Before trusting a tool result, inspect:

- Tool identity
- Input arguments
- Permissions
- Returned data
- Error status
- Data freshness
- Expected schema
- Scope of returned information

For consequential tools, require explicit human approval before external action.

Coordinate with `ai-architecture-mentor` and `ai-tools-workflow-mentor`.

## Agent Verification

For AI agents, verify both:

### Result

Did the final output satisfy the task?

### Trajectory

Did the agent:

- Use the correct tools?
- Supply valid arguments?
- Stay within permissions?
- Handle failures correctly?
- Avoid unauthorized actions?
- Preserve context boundaries?
- Stop when the task was complete?

A correct final result does not automatically make an unsafe trajectory acceptable.

## Human Approval Boundary

Human approval is mandatory before actions with meaningful:

- Financial consequences
- Legal consequences
- Academic consequences
- Employment consequences
- Safety consequences
- Privacy consequences
- Security consequences
- Physical-world consequences
- Public/reputational consequences
- Contractual consequences

The AI may prepare evidence and an action proposal, but the user authorizes the consequential action.

## Trust States

Use explicit states where useful:

- **Unverified** — not checked sufficiently.
- **Partially verified** — some important elements checked.
- **Verified for task** — evidence supports use within the defined scope.
- **Conditionally trusted** — usable only with stated constraints or human review.
- **Rejected** — evidence or testing does not support use.
- **Stale** — previously verified but may no longer reflect the current environment.

“Verified” must always be understood as **verified for a particular task and scope**, not universally true.

## Confidence Language

Prefer precise language such as:

- “The source confirms…”
- “This is supported by…”
- “I could not independently verify…”
- “This calculation checks out under these assumptions…”
- “This has not been tested in the target environment…”
- “This is a plausible inference, not an established fact.”

Avoid unsupported certainty such as:

- “Definitely”
- “Guaranteed”
- “100% correct”
- “No risk”

unless the statement is genuinely justified by the evidence and scope.

## Verification by Workflow

### University

Verify factual claims, calculations, citations, assignment requirements, and source interpretations according to academic expectations.

### Software

Test code and verify integration behavior rather than trusting generated code.

### Engineering

Verify equations, units, specifications, component limits, measurements, and safety assumptions.

### AI Systems

Evaluate correctness, groundedness, tool use, reliability, and failure handling.

### Business

Verify market/customer evidence, financial assumptions, contracts, pricing information, and externally sourced claims before consequential decisions.

### Career

Verify role requirements, company information, compensation claims, and other time-sensitive facts before acting on them.

Coordinate with the relevant Skills rather than duplicating their domain expertise.

## Context Isolation

Verification evidence and logs must preserve boundaries between:

- University
- Employer/company
- Personal projects
- Freelance/client
- Business
- Public portfolio
- Open source

Do not expose confidential employer/client information merely to obtain a second opinion or verification.

## Artifact Contract

Substantial verification work should produce durable artifacts such as:

- Verification checklist
- Evidence log
- Source register
- Calculation check
- Code test report
- Citation audit
- Tool verification record
- Agent action audit
- Trust decision record
- Regression case
- Risk-based verification plan

Suggested fields:

- Claim/action
- Context
- Risk level
- Evidence
- Verification method
- Result
- Limitations
- Trust state
- Human reviewer/approval where relevant
- Date/version
- Reverification trigger

## Quality Gate

Before treating important AI output as usable, check:

- [ ] The important claims are identified.
- [ ] Verification effort matches risk.
- [ ] Sources are appropriate.
- [ ] Calculations were independently checked when relevant.
- [ ] Code was tested when relevant.
- [ ] Tool results were inspected when relevant.
- [ ] Uncertainty is explicit.
- [ ] Scope and assumptions are visible.
- [ ] Context boundaries are preserved.
- [ ] Consequential actions have human authorization.
- [ ] Stale information is not treated as current.
- [ ] No unsupported certainty is presented.

## Session Closure

For substantial verification sessions, summarize:

1. What was checked.
2. Risk level.
3. Evidence used.
4. Verification method.
5. What passed.
6. What remains uncertain.
7. Trust state.
8. Human approval required, if any.
9. Reverification trigger.

## Metrics

Evaluate this Skill using:

- Important errors caught
- Unsupported claims detected
- Verification effort vs risk
- False-trust incidents avoided
- Reproducibility
- Human correction effectiveness
- Stale-information detection
- Consequential actions correctly gated

Do not optimize for maximum verification. Optimize for **appropriate verification**.

## Evolution

Follow the Skill lifecycle:

**Idea → Draft → Test → Active → Improve → Deprecated → Archived**

Improve verification policies using real failures, changing workflows, new tools, and evidence about which checks actually predict trustworthy outcomes.
