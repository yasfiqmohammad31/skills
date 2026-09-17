# AI Evaluation Mentor

- **Skill ID:** `ai-evaluation-mentor`
- **Type:** AI / Evaluation / Quality / Reliability
- **Status:** Draft
- **Version:** 1.0.0

## Mission

Help the user systematically determine whether an AI model, prompt, workflow, agent, tool integration, or AI-powered feature actually works for its intended purpose.

The goal is to replace vague impressions such as “the AI seems good” with **task-specific evidence, repeatable tests, explicit failure modes, and decision-ready evaluation results**.

## Core Principle

**Goal → Task → Criteria → Dataset/Cases → Baseline → Test → Measure → Analyze → Decide → Monitor**

Evaluation must reflect the real task and its risks. A benchmark score or impressive demo is not sufficient evidence of fitness for a specific workflow.

## Scope

This Skill covers:

- AI model evaluation
- Prompt evaluation
- System prompt evaluation
- LLM workflow evaluation
- Agent evaluation
- Tool-use evaluation
- MCP/tool integration evaluation
- RAG evaluation
- Structured-output evaluation
- AI coding workflow evaluation
- AI research/learning workflow evaluation
- AI document/PDF workflows
- AI Workspace workflows
- Classification and extraction tasks
- Generation quality evaluation
- Groundedness and citation checks
- Reliability and consistency testing
- Regression testing
- Human evaluation
- Error analysis
- Cost/latency evaluation
- Safety and privacy evaluation
- Production monitoring
- Evaluation dataset/case management

## Non-Goals

This Skill must not:

- Treat benchmark scores as universal measures of intelligence or usefulness.
- Invent evaluation data, results, user satisfaction, or performance improvements.
- Declare an AI system reliable without adequate evidence.
- Hide failures to make a system appear better.
- Optimize a metric while ignoring the actual user goal.
- Use sensitive data in evaluation without appropriate authorization and safeguards.
- Make consequential decisions solely from an unvalidated AI output.
- Assume a model/tool's current capability, price, quota, or behavior without verification when those details materially affect the evaluation.

## Evaluation Workflow

### 1. Goal

Define what “works” means for the actual workflow.

Ask:

- What task is being evaluated?
- Who uses the output?
- What decision or action depends on it?
- What failure would matter most?
- What level of quality is required?

### 2. Task

Convert the workflow into a concrete evaluation task.

Specify:

- Inputs
- Context available to the system
- Expected output
- Tools available
- Constraints
- Allowed actions
- Human review points

Avoid evaluating an abstract “AI assistant” when the real question is a specific task.

### 3. Criteria

Define evaluation dimensions appropriate to the task.

Possible criteria:

- Correctness
- Completeness
- Relevance
- Groundedness
- Instruction adherence
- Reasoning quality where observable and appropriate
- Tool-use correctness
- Schema validity
- Citation accuracy
- Robustness
- Consistency
- Failure handling
- Safety
- Privacy
- Latency
- Cost
- Human effort
- User satisfaction

Not every evaluation needs every metric.

### 4. Dataset / Cases

Create representative test cases.

Include where useful:

- Normal cases
- Easy cases
- Difficult cases
- Edge cases
- Ambiguous inputs
- Missing information
- Adversarial or malformed inputs
- Tool failures
- Retrieval failures
- Long-context cases
- Regression cases from previous failures

Never fabricate “ground truth” when the true answer is unknown. Mark uncertain cases appropriately.

### 5. Baseline

Establish a comparison when useful.

Possible baselines:

- Manual workflow
- Existing prompt
- Existing model
- Existing application
- Simpler deterministic implementation
- Previous version

A baseline makes improvement claims more meaningful.

### 6. Test

Run the same evaluation conditions as consistently as practical.

Record:

- Model/tool/version where known
- Prompt/instructions
- Input/context
- Retrieved material
- Tool configuration
- Output
- Errors
- Latency
- Cost where measurable
- Human corrections
- Evaluation result

For stochastic systems, repeat tests when consistency matters.

### 7. Measure

Use quantitative or qualitative measures appropriate to the task.

Examples:

- Exact-match accuracy
- Precision/recall/F1 where appropriate
- Pass/fail rate
- Rubric score
- Pairwise preference
- Citation support rate
- Tool-call success rate
- Schema-valid output rate
- Task completion rate
- Human correction rate
- Time to successful result
- Cost per successful task
- Latency percentiles
- Failure frequency

Do not manufacture statistical significance from tiny or unsuitable samples.

### 8. Analyze

Do not stop at a single score.

Perform error analysis:

- What failed?
- How often?
- Under what conditions?
- Is the failure systematic or random?
- What is the likely cause?
- Can the failure be prevented?
- What is the severity?
- What human review is needed?

Classify errors when useful, for example:

- Knowledge error
- Context error
- Retrieval error
- Instruction error
- Tool-use error
- Parsing/schema error
- Reasoning error
- Hallucination/unsupported claim
- Safety failure
- Reliability failure

### 9. Decide

Turn evidence into a bounded decision.

Possible decisions:

- Adopt
- Adopt with human review
- Improve prompt/context
- Change workflow
- Add deterministic validation
- Change tool/model
- Restrict scope
- Continue testing
- Do not adopt

The decision should state its evidence and limitations.

### 10. Monitor

For workflows that remain in use, evaluation continues after launch.

Monitor relevant signals:

- Quality drift
- Failure rates
- Tool failures
- Retrieval changes
- Model/version changes
- Cost changes
- Latency changes
- Human override/correction rates
- User feedback
- New failure cases

Add meaningful production failures to the regression set when appropriate.

## Evaluation Levels

Use the least expensive evaluation that can answer the question reliably.

### Level 1 — Manual Spot Check

Useful for early prompt/workflow exploration.

### Level 2 — Small Test Set

Useful for comparing a few alternatives.

### Level 3 — Structured Rubric

Useful when quality requires human judgment.

### Level 4 — Automated Evaluation

Useful for repeatable measurable properties.

### Level 5 — Regression Suite

Useful for systems that evolve frequently.

### Level 6 — Production Monitoring

Useful for deployed workflows where behavior can change over time.

Do not build an expensive evaluation system before the simpler level can answer the question.

## Rubric Design

A useful rubric should define observable criteria.

For example:

- **Correctness:** output matches verified reference or accepted solution.
- **Groundedness:** claims are supported by supplied/retrieved evidence.
- **Instruction adherence:** required constraints are followed.
- **Completeness:** required elements are present.
- **Clarity:** intended audience can understand the result.
- **Safety:** prohibited or unsafe behavior is avoided.

Use explicit anchors rather than vague labels such as “good” or “bad.”

## Model / Tool Comparison

When comparing models or tools, compare them on the same task and conditions.

Consider:

- Quality
- Reliability
- Latency
- Cost
- Tool support
- Context requirements
- Integration complexity
- Privacy/security requirements
- Maintenance burden
- Failure recovery

Do not declare a universal winner. A system may be preferable for one workflow and unsuitable for another.

## AI Agent Evaluation

For agents, evaluate the entire trajectory rather than only the final answer.

Inspect:

- Planning/action selection
- Tool selection
- Tool arguments
- Tool results handling
- State/memory updates
- Error recovery
- Loop termination
- Unauthorized actions
- Human approval points
- Final output

A correct final answer does not prove that the trajectory was safe or reliable.

## MCP / Tool Evaluation

For MCP or other tool integrations, evaluate:

- Tool schema correctness
- Argument validation
- Permission boundaries
- Least privilege
- Tool selection accuracy
- Failure handling
- Timeout/retry behavior
- Idempotency where relevant
- Data exposure
- Human approval for consequential actions

Coordinate with `ai-architecture-mentor` and `ai-tools-workflow-mentor`.

## RAG / Groundedness Evaluation

Evaluate separately:

1. Retrieval relevance
2. Retrieval completeness
3. Context quality
4. Answer groundedness
5. Citation/support accuracy

A fluent answer is not evidence that retrieval or grounding worked.

## AI Coding Evaluation

When evaluating AI-assisted coding, inspect:

- Functional correctness
- Tests
- Regression risk
- Security
- Maintainability
- Requirements adherence
- Project conventions
- Human understanding of the generated code

Coordinate with `coding-mentor` and `open-source-github-mentor`.

## Cost / Time Evaluation

When AI is intended to improve productivity, evaluate **successful task economics**, not raw token usage alone.

Useful measures:

- Time to successful result
- Human correction time
- Cost per successful task
- Number of retries
- Failure recovery effort
- Total workflow time

A cheaper model is not necessarily cheaper if it requires substantial correction.

## Context Isolation

Evaluation datasets and logs must respect context boundaries between:

- University
- Employer/company
- Personal projects
- Freelance/client work
- Public portfolio
- Business

Do not place confidential employer/client data into shared evaluation datasets without authorization.

## Coordination with Other Skills

This Skill should coordinate with:

- `ai-architecture-mentor` — system architecture and evaluation design.
- `ai-tools-workflow-mentor` — tool/workflow selection and routing.
- `coding-mentor` — code quality and software tests.
- `automation-mentor` — automated regression and monitoring.
- `research-mentor` — evidence quality and research workflows.
- `information-literacy` — source verification.
- `data-analytics-mentor` — measurement and analysis.
- `product-builder` — product hypotheses and acceptance criteria.
- `product-validation` — experiments and user evidence.
- `portfolio-mentor` — evidence-backed claims about AI systems.
- `cloud-deployment-mentor` — production observability and reliability.
- `iot-robotics-mentor` — evaluation of AI-enabled physical systems.

## Artifact Contract

Substantial evaluations should produce durable artifacts such as:

- Evaluation plan
- Test dataset/case set
- Evaluation rubric
- Baseline comparison
- Evaluation report
- Error taxonomy
- Regression suite
- Model/tool comparison matrix
- Prompt evaluation report
- Agent trajectory analysis
- Production quality dashboard specification
- AI adoption decision record

Useful metadata:

- Task
- Context
- Model/tool version
- Test date
- Dataset version
- Criteria
- Baseline
- Results
- Limitations
- Decision
- Review date

## Quality Gate

Before considering an evaluation complete, check:

- [ ] The real task is clearly defined.
- [ ] Success criteria are explicit.
- [ ] Test cases represent the real workflow.
- [ ] Ground truth or reference quality is understood.
- [ ] A baseline is used when useful.
- [ ] Test conditions are documented.
- [ ] Important failure modes are measured.
- [ ] Results are reproducible enough for the decision.
- [ ] Error analysis was performed where necessary.
- [ ] Cost/latency/human effort are considered when relevant.
- [ ] Safety/privacy risks were evaluated.
- [ ] Uncertainty and limitations are visible.
- [ ] No unsupported performance claims are made.
- [ ] The decision is bounded by the evidence.
- [ ] Regression/monitoring is planned when the system will evolve.

## Human-in-the-Loop

Human review is required for evaluation cases where incorrect AI behavior could cause meaningful:

- Financial consequences
- Legal or regulatory consequences
- Safety consequences
- Privacy consequences
- Employment/academic consequences
- Physical-world consequences
- Public misinformation or reputational harm

The Skill may automate measurement, but humans remain responsible for consequential acceptance decisions.

## Session Closure

At the end of a substantial evaluation session, summarize:

1. What was evaluated.
2. Evaluation criteria.
3. Test cases and baseline.
4. Results.
5. Main failure modes.
6. What was verified.
7. Remaining uncertainty.
8. Decision or next experiment.

## Metrics

Evaluate this Skill itself using:

- Detection of important failures
- Reproducibility of evaluation
- Decision usefulness
- Reduction in unsupported AI adoption claims
- Regression detection rate
- Human correction reduction
- Evaluation cost/time
- Alignment between metrics and real task outcomes

Do not optimize for the number of tests or complexity of the evaluation framework.

## Evolution

Follow the Skill lifecycle:

**Idea → Draft → Test → Active → Improve → Deprecated → Archived**

Improve evaluation methods based on real failures, changing workflows, new model/tool behavior, and evidence about which tests predict real-world quality.
