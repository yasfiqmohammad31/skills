# Memory Management Mentor

- **Skill ID:** `memory-management-mentor`
- **Type:** Core / Memory / Context Governance
- **Status:** Draft
- **Version:** 1.0.0

## Mission

Manage what information an AI system should remember, retrieve, update, ignore, retire, or forget so that memory remains useful, current, appropriately scoped, privacy-aware, and separated from temporary context.

Memory exists to improve continuity and reduce repeated work; it must not become an uncontrolled copy of everything the user has ever shared.

## Core Principle

> **Identify Candidate → Classify → Check Authorization → Store Intentionally → Scope → Retrieve → Validate Freshness → Use → Update/Retire**

## Memory Model

Yasfiq AI OS distinguishes at least these layers:

1. **Stable Memory** — durable preferences, recurring constraints, long-lived goals, and other information that remains useful across many sessions.
2. **Domain Memory** — information associated with a domain such as university, career, engineering, or business.
3. **Project Memory** — state and decisions belonging to a specific project.
4. **Session Memory** — information useful during the current conversation/session.
5. **Ephemeral Context** — temporary information needed for one operation and not intended for durable storage.

Memory and context are related but not identical:

> **Memory = information retained across time.**
>
> **Context = information supplied to perform the current task.**

A memory item may become context only when it is relevant and authorized for the current task.

## Scope

- Memory classification
- Durable vs temporary information
- Memory eligibility
- Retrieval
- Freshness and staleness
- Memory conflicts
- Updates and corrections
- Retirement and archival
- User-requested forgetting
- Privacy and data minimization
- Context isolation
- Project state
- Preference management
- Memory provenance
- Memory confidence
- Memory evaluation

## Non-Goals

- Storing every conversation detail
- Inferring sensitive personal information for storage
- Treating memory as a complete transcript archive
- Using stale memory as current fact
- Sharing memory across isolated domains without authorization
- Storing credentials, passwords, API keys, private tokens, or secrets as ordinary memory
- Making consequential decisions solely from remembered information
- Pretending that a memory is verified merely because it was previously stored

## Memory Eligibility

Before durable storage, evaluate:

- **Utility:** Will this likely help future work?
- **Durability:** Is it likely to remain true long enough to justify retention?
- **Scope:** Which domain/project does it belong to?
- **Authorization:** Is retaining it appropriate?
- **Sensitivity:** Does it contain personal, confidential, or security-sensitive information?
- **Provenance:** Where did it come from?
- **Confidence:** How certain is it?
- **Staleness risk:** How quickly could it become outdated?

Prefer storing concise, structured facts over unnecessary narrative.

## Memory Categories

### Good Candidates

- Long-term goals
- Stable working preferences
- Recurring workflow preferences
- Persistent project decisions
- Course/project progress when useful for continuity
- Reusable constraints
- Explicitly established terminology or conventions

### Usually Session/Ephemeral

- One-off instructions
- Temporary calculations
- Temporary brainstorming
- Current debugging output
- A single day's transient schedule
- Intermediate tool results
- Draft content that has no continuing relevance

### Do Not Store as Ordinary Memory

- Passwords
- API keys
- Access tokens
- Private credentials
- Secrets
- Sensitive third-party data
- Confidential employer/client information without appropriate authorization
- Information that is unnecessary for future assistance

## Context Isolation

Memory must retain its domain boundary.

Example:

```text
University Memory
       ≠
Employer Memory
       ≠
Freelance Client Memory
       ≠
Personal Memory
       ≠
Business Memory
       ≠
Public Portfolio Memory
       ≠
Open Source Memory
```

A fact being known does not make it globally applicable.

Before retrieval, ask:

1. Is this memory relevant to the task?
2. Is it authorized in this context?
3. Does the current task belong to the same domain?
4. Could using it expose confidential or inappropriate information?

If boundaries are uncertain, do not silently cross them.

## Retrieval Rules

Retrieve the minimum memory necessary.

Prioritize:

1. Directly relevant project/task memory
2. Relevant domain memory
3. Stable preferences/constraints
4. Broader memory only when necessary

Do not inject unrelated personal history into a task simply because it exists.

## Freshness

Memory must have a freshness state where useful:

- **Current** — recently confirmed or inherently stable
- **Likely current** — probably still valid but not recently confirmed
- **Stale** — likely outdated
- **Unknown** — freshness cannot be established
- **Superseded** — replaced by newer information
- **Retired** — intentionally no longer used

Time-sensitive memory should be revalidated before it affects important work.

## Conflicts

When memory conflicts with current user instructions:

> **Current explicit instruction wins.**

When two memory items conflict:

1. Prefer newer reliable information.
2. Check provenance.
3. Check whether the items belong to different scopes.
4. Ask the user when the conflict materially affects the task.
5. Mark the superseded item rather than silently rewriting history when provenance matters.

Never fabricate a reconciliation.

## Provenance

Where practical, memory should carry:

- Source
- Date/recency
- Scope
- Confidence
- Last confirmation
- Superseded-by relationship when applicable

A remembered statement is not automatically an independently verified fact.

## User Control

The user remains the authority over personal memory decisions.

When a user says:

- **Remember this** → identify whether it is appropriate durable memory and preserve its scope.
- **Don't use this for this task** → exclude it from the current context.
- **Forget/delete this** → do not rely on it going forward; explain any product-level deletion steps that are required when applicable.
- **This is outdated** → update the current representation and mark the prior state as superseded where useful.
- **Use what you know about my preferences** → retrieve only relevant, authorized preferences.

Do not claim that information has been permanently deleted unless the underlying storage system actually confirms deletion.

## Memory Write Policy

A memory write should be intentional rather than automatic whenever the information could materially affect privacy, context boundaries, or future behavior.

Suggested decision:

```text
Candidate Information
       ↓
Useful later?
   ├─ No → Ephemeral / discard
   └─ Yes
       ↓
Durable enough?
   ├─ No → Session / project context
   └─ Yes
       ↓
Authorized + appropriate?
   ├─ No → Do not store
   └─ Yes
       ↓
Classify scope
       ↓
Store concise representation
       ↓
Record provenance/freshness
```

## Memory Update Policy

When new information arrives:

- Confirm whether it is a correction, addition, temporary exception, or new durable state.
- Avoid turning a temporary exception into a permanent preference.
- Preserve important historical distinctions when they matter.
- Replace obsolete operational state with current state.
- Avoid duplicate memory entries when one canonical representation is sufficient.

## Verification

Memory should use verification proportional to risk.

For low-risk preferences, user statements may be sufficient.

For important factual claims, verify against appropriate current sources before treating memory as authoritative.

Coordinate with `verification-trust-manager` for trust classification.

## Human-in-the-Loop

Human confirmation should be favored when:

- A memory could materially change future decisions
- Sensitive information is involved
- A domain boundary is unclear
- Two important memories conflict
- A proposed update could affect consequential workflows
- The user requests deletion or correction with unclear scope

## Memory Failure Modes

Watch for:

- Memory pollution
- Over-retention
- Stale memory
- Cross-domain leakage
- Preference overgeneralization
- Duplicate memory
- Contradictory memory
- False memory
- Unverified memory treated as fact
- Temporary state becoming durable
- Missing provenance
- Excessive retrieval

## Artifacts

When useful, produce:

- Memory schema
- Memory classification record
- Memory manifest
- Context manifest
- Memory update record
- Supersession record
- Memory retention policy
- Memory audit
- Memory evaluation cases

## Quality Gate

Before using durable memory:

- [ ] Is it relevant?
- [ ] Is it authorized?
- [ ] Is the scope correct?
- [ ] Is the information sufficiently current?
- [ ] Is its provenance understood?
- [ ] Is confidence appropriate?
- [ ] Is sensitive information handled appropriately?
- [ ] Could current user instructions override it?
- [ ] Could using it leak information across domains?
- [ ] Is only the minimum necessary memory being retrieved?

## Metrics

Measure:

- Retrieval relevance
- Memory precision
- Memory recall for necessary facts
- Stale-memory rate
- Conflict rate
- Incorrect-memory rate
- Cross-context leakage rate
- Unnecessary-memory retrieval rate
- User correction rate
- Memory update accuracy
- Retention efficiency
- User-perceived continuity

Do not optimize for maximum memory volume.

## Coordination

Works closely with:

- Context Engineering Mentor
- Intent & Task Routing Mentor
- Verification & Trust Manager
- AI Architecture Mentor
- AI Tools & Workflow Mentor
- Learning Coach
- Subject Skills
- Project Skills
- Privacy/security controls
- Artifact Lifecycle

## Evolution

Lifecycle:

> **Idea → Draft → Test → Active → Improve → Deprecated → Archived**

Memory policies should evolve from observed retrieval errors, stale information, privacy incidents, context leakage, and user corrections—not from a goal to remember everything.
