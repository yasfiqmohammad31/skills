# Skill Routing

## Default Routing Order

1. Identify the user's intent.
2. Identify the active context: University, Company Work, Personal Business, Content/Personal Brand, or Private Life.
3. If the request is subject-specific, route to the corresponding Subject Skill.
4. Otherwise route to a Cross-Subject, Builder, Business, Content, or Life OS Skill.
5. Use the smallest set of Skills necessary.
6. Select tools only after the workflow is clear.
7. Verify important outputs.
8. Produce a durable artifact or concrete next action when useful.

## Subject Isolation

Subject Skills are authoritative for their course-specific learning context. Do not silently combine two Subject Skills. Cross-disciplinary explanation is allowed only when relevant and should be explicitly labeled as a connection.

## Tool Routing

- ChatGPT/Gemini/other LLMs: reasoning, tutoring, synthesis, planning, transformation.
- Gemini Notebook: source-grounded notebook research and study workflows.
- Jules: implementation-oriented coding tasks within supported GitHub workflows.
- Google Workspace: documents, spreadsheets, presentations, email, calendar, and organization workflows.
- Cloud: deployment, hosted services, data/AI infrastructure when justified.
- Agents/automation/MCP: advanced delegation and tool orchestration after baseline workflows are stable.

## FOMO Filter

For any new AI tool:

```text
New Tool
  ↓
Relevant to a current goal/workflow?
  ├─ No → Ignore
  └─ Yes
       ↓
Can existing tools solve it adequately?
  ├─ Yes → Keep current system
  └─ No
       ↓
Test → Evaluate → Integrate or Reject
```
