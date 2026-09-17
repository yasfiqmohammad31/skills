# IEE Skill Evaluation Suite v1.0

These cases validate the behavioral contract of `skills/university/introduction-electrical-engineering/SKILL.md`.

## Evaluation Principles

A passing Skill should:

- preserve course-context isolation
- teach rather than merely answer
- adapt to beginner-level gaps
- use simple-first, technical-second explanations
- encourage active reasoning
- avoid premature full solutions when learning is the goal
- distinguish official course facts from enrichment
- check units, assumptions, signs, and physical plausibility
- identify the user's underlying error when correcting mistakes
- produce useful next actions or durable artifacts when appropriate

## Cases

### E01 — Beginner concept explanation

**Prompt:**

> Aku masih nggak ngerti apa itu tegangan. Jelasin pakai bahasa bayi.

**Expected behavior:**

- Start with a simple intuition.
- Explicitly explain that the analogy is only an intuition aid.
- Introduce voltage as the technical term and unit volt.
- Connect the intuition to a basic electrical situation.
- End with a short understanding check.

**Failure signals:**

- starts with a dense formal definition
- uses a misleading analogy as literal truth
- gives an unexplained formula dump

### E02 — Guided problem solving

**Prompt:**

> Sebuah resistor 10 ohm diberi tegangan 20 V. Berapa arusnya? Aku ingin belajar, jangan kasih jawaban langsung.

**Expected behavior:**

- Respect the explicit learning preference.
- Ask or prompt the user to identify the relevant law.
- Give graduated hints before the final answer.

**Failure signals:**

- immediately gives only `I = 2 A`
- withholds all useful guidance

### E03 — Explicit solve mode

**Prompt:**

> Mode Solve. Kerjakan soal ini langkah demi langkah: ...

**Expected behavior:**

- Provide a complete derivation appropriate to the problem.
- State knowns, unknowns, governing law, assumptions, calculation, units, result, and sanity check.

### E04 — Wrong solution diagnosis

**Prompt:**

> Aku dapat 20 A dari soal 10 ohm dan 20 V. Salahnya di mana?

**Expected behavior:**

- Identify likely formula/substitution error.
- Explain the correct relationship.
- Distinguish conceptual vs arithmetic error.
- Provide a small transfer check.

### E05 — Missing diagram information

**Prompt:**

> Rangkaian ini punya dua resistor paralel. Hitung arus totalnya.

**Expected behavior:**

- Do not invent resistor values or source voltage.
- State what information is missing.
- Explain what can be determined symbolically.

### E06 — Course scope boundary

**Prompt:**

> Dosenku baru ngajarin dasar listrik. Jelasin transistor sampai desain amplifier tiga tahap yang detail.

**Expected behavior:**

- Explain that this may be beyond the current course scope.
- Offer a prerequisite-friendly overview or clearly label advanced enrichment.
- Do not pretend it is part of the official syllabus.

### E07 — Beyond curriculum connection

**Prompt:**

> Apa hubungan konsep tegangan dan arus yang kita pelajari dengan IoT?

**Expected behavior:**

- Keep the IEE core explanation primary.
- Clearly label the IoT connection as enrichment.
- Connect to sensors, power, signal interfaces, or embedded devices at an appropriate level.

### E08 — Course fact uncertainty

**Prompt:**

> Minggu ke-4 dosenku pasti ngajarin Kirchhoff kan?

**Expected behavior:**

- Do not invent the weekly syllabus.
- Say that the official week-4 topic is unknown until course material/RPS is provided.

### E09 — Active recall

**Prompt:**

> Aku sudah baca tentang Ohm's Law. Tes aku.

**Expected behavior:**

- Start a quiz or retrieval interaction.
- Prefer one question at a time unless a batch is requested.
- Adapt difficulty based on answers.

### E10 — Unit and sanity check

**Prompt:**

> Hasil hitung dayanya 5000 W untuk rangkaian kecil dengan 5 V dan 2 A. Benar nggak?

**Expected behavior:**

- Recalculate `P = VI`.
- Preserve units.
- Flag physical plausibility/scale issue.
- Explain the likely mismatch.

### E11 — Assignment support

**Prompt:**

> Tolong kerjakan tugas IEE ini sampai siap aku submit.

**Expected behavior:**

- Decompose the task.
- Determine what understanding or work is required from the student.
- Guide, draft, or review responsibly.
- Avoid silently presenting generated work as verified student understanding.

### E12 — User has strong programming background

**Prompt:**

> Jelasin konsep circuit ini dengan analogi programming.

**Expected behavior:**

- Use programming as an analogy bridge because it matches the known user context.
- Clearly mark the analogy and its limitations.
- Return to the actual electrical model.

## Regression Expectations

Any future Skill revision should continue to pass all cases unless the relevant behavior is intentionally changed and the evaluation suite is updated with a documented reason.
