# Skill Specification

## Purpose

Standardize how production Skills are designed so they remain portable, testable, maintainable, and consistent.

## Required Metadata

```yaml
name:
version:
type:
domain:
status:
inputs:
outputs:
dependencies:
compatible_platforms:
```

## Required Sections

1. Purpose
2. Scope
3. Context requirements
4. User profile assumptions
5. Behavior / principles
6. Modes
7. Workflow logic
8. Output contract
9. Verification rules
10. Boundary / safety rules
11. Evaluation cases
12. Version history

## Subject Skills

One course = one Subject Skill.

A Subject Skill owns:

- course-specific terminology
- curriculum context
- known learning outcomes
- current progress
- prerequisite map
- assessment modes
- course-relevant artifacts

It must not silently mix unrelated course contexts.

## Cross-Subject Skills

Cross-subject capabilities should avoid embedding assumptions about one course. They accept subject context as an input.

Examples: Learning Coach, Research Mentor, English for Engineer, Information Literacy.

## Mode Design

Common modes:

- Explain
- Learn
- Practice
- Solve
- Quiz
- Review
- Assignment Support
- Exam Prep
- Explore Beyond Curriculum

Modes should change behavior, not merely change a heading.

## Output Contract

A Skill must define what a successful response or artifact looks like. Prefer structured outputs where they improve reuse.

Examples:

```text
Explain → explanation + example + understanding check
Practice → exercise + hints policy + answer check
Research → evidence brief + citations + uncertainty
Project → plan + implementation artifact + verification
```

## Teaching Rule

For learning Skills, optimize for independent capability. Do not remove productive struggle merely to maximize speed.

## Skill Lifecycle

```text
Idea
→ Draft
→ Test
→ Active
→ Improving
→ Deprecated
→ Archived
```

Each version should have a reason for change and relevant regression cases.

## Portability Rule

Core Skill logic must not depend on a vendor-specific feature when the underlying behavior can be described generically. Platform-specific mechanics belong in adapters.

## Dependency Rule

Dependencies should be explicit. A Skill should not silently require another Skill to work.
