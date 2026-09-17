# IEE Skill Evaluation Suite v1.1

These cases validate the behavioral contract of `skills/university/introduction-electrical-engineering/SKILL.md` against both generic learning behavior and the user's current lecturer-provided material.

## Evaluation Principles

A passing Skill should:

- preserve course-context isolation
- teach rather than merely answer
- adapt to beginner-level gaps
- use simple-first, technical-second explanations
- encourage active reasoning
- avoid premature full solutions when learning is the goal
- distinguish official course facts from enrichment
- treat lecturer-provided material as authoritative for course context
- avoid inventing weekly placement, exam scope, or syllabus items
- check units, assumptions, signs, and physical plausibility when quantitative work is actually involved
- identify the user's underlying error when correcting mistakes
- produce useful next actions or durable artifacts when appropriate

## Cases

### E01 — Beginner concept explanation

**Prompt:**

> Aku masih nggak ngerti apa itu Electrical Engineering. Jelasin pakai bahasa bayi.

**Expected behavior:**

- Start with a simple intuition.
- Explicitly explain that the analogy is only an intuition aid.
- Introduce the technical definition of Electrical Engineering.
- Stay within the current introductory course context.
- End with a short understanding check.

**Failure signals:**

- starts with dense specialist theory
- uses a misleading analogy as literal truth
- jumps immediately into advanced subfields

### E02 — Source-grounded course explanation

**Prompt:**

> Berdasarkan materi dosen saya, apa saja bidang utama Electrical Engineering?

**Expected behavior:**

- Use the lecturer-provided material as the primary source.
- Identify Power and Energy Systems, Signal/Communications/Electronics, and Control System/Computing as the main groupings shown in Session 1.
- Avoid silently replacing the lecturer's organization with a generic taxonomy.

**Failure signals:**

- invents another official taxonomy without labeling it as enrichment
- claims the list is complete for all universities

### E03 — Lecturer-material grounding

**Prompt:**

> Dari Sesi 2, tokoh siapa saja yang dibahas dalam sejarah Electrical Engineering?

**Expected behavior:**

- Extract names and milestones from Session 2.
- Preserve the deck's historical organization.
- Avoid inventing additional figures as if they were covered in the session.

### E04 — Guided problem solving

**Prompt:**

> Sebuah resistor 10 ohm diberi tegangan 20 V. Berapa arusnya? Aku ingin belajar, jangan kasih jawaban langsung.

**Expected behavior:**

- Respect the explicit learning preference.
- Ask or prompt the user to identify the relevant law.
- Give graduated hints before the final answer.
- Clearly treat this as foundational enrichment unless later course material confirms it is course core.

**Failure signals:**

- immediately gives only `I = 2 A`
- claims Ohm's law was already taught in the supplied Session 1/2 materials

### E05 — Explicit solve mode

**Prompt:**

> Mode Solve. Kerjakan soal ini langkah demi langkah: ...

**Expected behavior:**

- Provide a complete derivation appropriate to the problem.
- State knowns, unknowns, governing law, assumptions, calculation, units, result, and sanity check.

### E06 — Wrong solution diagnosis

**Prompt:**

> Aku dapat 20 A dari soal 10 ohm dan 20 V. Salahnya di mana?

**Expected behavior:**

- Identify likely formula/substitution error.
- Explain the correct relationship.
- Distinguish conceptual vs arithmetic error.
- Provide a small transfer check.

### E07 — Missing diagram information

**Prompt:**

> Rangkaian ini punya dua resistor paralel. Hitung arus totalnya.

**Expected behavior:**

- Do not invent resistor values or source voltage.
- State what information is missing.
- Explain what can be determined symbolically.

### E08 — Course scope boundary

**Prompt:**

> Dosenku baru ngajarin pengantar dan sejarah listrik. Jelasin transistor sampai desain amplifier tiga tahap yang detail.

**Expected behavior:**

- Explain that this goes beyond the currently supplied course material.
- Offer a prerequisite-friendly overview or clearly label advanced enrichment.
- Do not pretend it is part of the official syllabus.

### E09 — Weekly-scope uncertainty

**Prompt:**

> Minggu ke-4 dosenku pasti ngajarin Kirchhoff kan?

**Expected behavior:**

- Do not invent the weekly syllabus.
- State that calendar-week placement is currently unknown.
- Ask for the RPS or later lecturer material if the exact week matters.

### E10 — Current-material distinction

**Prompt:**

> Apakah dari dua materi awal ini sudah bisa disimpulkan bahwa saya sudah belajar circuit analysis?

**Expected behavior:**

- Answer based on the supplied materials only.
- Explain that the two decks establish introductory/history/field/application/career content but do not establish that quantitative circuit analysis has been taught.
- Avoid treating the user's self-rating of 0/10 as proof of what the lecturer has or has not taught.

### E11 — Future-topic extraction

**Prompt:**

> Teknologi masa depan apa saja yang muncul di materi Sesi 2?

**Expected behavior:**

- Extract Renewable Energy, Smart Grid, Electric Vehicles, Artificial Intelligence, Industry 4.0, and Quantum Computing.
- Present them as topics explicitly shown in the supplied material.

### E12 — Assessment structure extraction

**Prompt:**

> Bagaimana bobot penilaian IEE dari materi Sesi 1?

**Expected behavior:**

- State UAS 25%, UTS 25%, Individual Assignment 20%, Group Assignment 20%, Attendance 10%.
- Do not add other components.
- Attribute this as the structure shown in the supplied Session 1 deck.

### E13 — Active recall

**Prompt:**

> Aku sudah baca tentang definisi Electrical Engineering dan bidang utamanya. Tes aku.

**Expected behavior:**

- Start a quiz or retrieval interaction.
- Prefer one question at a time unless a batch is requested.
- Adapt difficulty based on answers.
- Prefer source-grounded questions before adding enrichment.

### E14 — Beyond curriculum connection

**Prompt:**

> Apa hubungan bidang Control System and Computing dengan minat saya di robotika?

**Expected behavior:**

- Start from the course material's description of Control System and Computing.
- Clearly label the robotics connection as a practical extension/enrichment when the deck does not explicitly teach the detailed robotics mechanisms.
- Avoid claiming that a specific robotics curriculum was covered.

### E15 — User has strong programming background

**Prompt:**

> Jelasin konsep Electrical Engineering dengan analogi programming.

**Expected behavior:**

- Use programming as an analogy bridge because it matches the known user context.
- Clearly mark the analogy and its limitations.
- Return to the actual electrical/engineering model.

## Regression Expectations

Any future Skill revision should continue to pass these cases unless the relevant behavior is intentionally changed and the evaluation suite is updated with a documented reason.
