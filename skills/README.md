# Skills

This directory contains the modular AI capabilities of Yasfiq AI OS.

## Naming Rules

Use lowercase kebab-case directory names. Each production Skill lives in its own directory and uses `SKILL.md` as the canonical definition.

## Skill Types

- `university/` — subject-specific and academic Skills
- `cross-domain/` — reusable learning/research/communication capabilities
- `builder/` — software, engineering, product, and portfolio capabilities
- `business/` — freelancing and monetization capabilities
- `content/` — content and personal-brand capabilities
- `life-os/` — personal productivity and orchestration capabilities

## Active / Scaffolded Skills

### University

- `university/introduction-electrical-engineering/` — Semester 1 IEE production pilot.
- `university/computational-thinking-programming/` — scaffold; course context pending.
- `university/renewable-energy-solar-panel-foundation/` — scaffold; course context pending.
- `university/career-design-professional-development-1/` — scaffold; course context pending.

### Cross-Domain

- `cross-domain/learning-coach/` — reusable learning and retention support.
- `cross-domain/research-mentor/` — research workflow and evidence synthesis.
- `cross-domain/information-literacy/` — source evaluation and verification.
- `cross-domain/english-for-engineer/` — engineering English across reading, writing, listening, and speaking.

### Builder

- `builder/coding-mentor/` — software implementation, debugging, review, testing, and AI-assisted coding.
- `builder/product-builder/` — problem framing, product definition, MVP scope, prototyping, validation, and iteration.

## Architecture Rule

Subject Skills own course-specific behavior and context. Cross-Domain Skills own reusable capabilities and should not duplicate course-specific knowledge. Builder Skills own reusable building capabilities and coordinate with Subject, Cross-Domain, Business, and Content Skills rather than absorbing their responsibilities.

Subject Skills can be scaffolded before course materials exist. Lecturer materials are added later to `CONTEXT.md` and `COURSE-MATERIALS.md` without requiring a new Skill.

## Lifecycle

Idea → Draft → Test → Active → Improve → Deprecated → Archived.

Skills are evaluated through real use and regression cases where appropriate.
