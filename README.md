# Yasfiq AI OS

Personal collection of modular AI Skills for learning, engineering, building products, career development, personal branding, business, and productivity.

## Repository Structure

The repository is intentionally kept simple: each capability is a Skill, organized by domain.

```text
yasfiq-ai-os/
├── skills/
│   ├── university/
│   │   └── <skill-name>/
│   │       └── SKILL.md
│   ├── cross-domain/
│   │   └── <skill-name>/
│   │       └── SKILL.md
│   ├── builder/
│   │   └── <skill-name>/
│   │       └── SKILL.md
│   ├── business/
│   │   └── <skill-name>/
│   │       └── SKILL.md
│   ├── ai/
│   │   └── <skill-name>/
│   │       └── SKILL.md
│   ├── data/
│   │   └── <skill-name>/
│   │       └── SKILL.md
│   ├── career/
│   │   └── <skill-name>/
│   │       └── SKILL.md
│   ├── communication/
│   │   └── <skill-name>/
│   │       └── SKILL.md
│   ├── decision/
│   │   └── <skill-name>/
│   │       └── SKILL.md
│   └── core/
│       └── <skill-name>/
│           └── SKILL.md
└── README.md
```

## Skill Format

Each Skill lives in its own directory and uses a single canonical file:

```text
skills/<domain>/<skill-name>/SKILL.md
```

The `SKILL.md` file is the source of truth for that Skill's behavior, scope, workflow, and usage guidance.

## Design Principles

- One academic subject = one isolated Subject Skill.
- Reusable capabilities are separate Skills.
- Keep Skills modular and portable across AI platforms.
- Keep each Skill self-contained.
- Do not require platform-specific files inside the Skill itself.
- Add course or project context directly when needed, without changing the repository's basic Skill structure.

## Current Status

The repository currently contains the Yasfiq AI OS Skill Layer. Skills are developed incrementally and may have different maturity levels, as declared inside each `SKILL.md`.

The repository structure is intentionally minimal so the Skills can be reused in Gemini, ChatGPT, or other compatible AI environments without requiring a separate framework inside this repository.

## Using a Skill

Open the relevant `SKILL.md`, provide its instructions to the target AI platform, and then provide the context or task you want to work on.

For example:

```text
skills/university/introduction-electrical-engineering/SKILL.md
```

can be used as the behavior definition for an Introduction to Electrical Engineering tutor.

## Scope Boundary

This repository is the Skill Layer. Runtime orchestration, platform configuration, application code, and other implementation concerns are intentionally kept outside this minimal repository structure.
