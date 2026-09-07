---
name: prompt-skill-authoring
description: Design or refactor LLM prompts, agent instructions, and the instruction layer of Codex skills. Use when the task is about how instructions should be written; when the deliverable is a Codex skill, use this alongside the installed skill-creator rather than replacing it.
---

# Prompt & Skill Instruction Authoring

Design instructions that are concise, decision-relevant, executable, and maintainable. Assume the model already has general language, reasoning, coding, and tool-use ability. Add information only when it changes an important decision, preserves a real constraint, or materially improves the result.

## Core principles

- Preserve the user's goal, scope, chosen product, and authorization boundaries.
- Describe the desired result and the criteria for choosing among reasonable approaches.
- Match specificity to risk. Give open-ended work room to adapt; preserve fixed steps or exact parameters only when deviation creates a concrete correctness, safety, permission, or reliability problem.
- Prefer intent-level reasoning guidance over prescribing a chain of thought. Tell the model what deserves careful reasoning and what constitutes a good decision, rather than dictating the reasoning steps it must follow.
- Prefer specifications of desired behavior. Keep unavoidable hard boundaries brief and operational, including the appropriate fallback or stopping behavior when useful.
- Separate stable instructions from per-request data and parameters.
- Treat every rule as a cost: keep it only if removing it could change a meaningful decision or observable result.
- Refine instructions from real failures with the smallest rule that explains the demonstrated cause; keep revisions proportional to evidence from actual use.

## Route by deliverable

For ordinary prompts, system/developer instructions, agent prompts, or reusable prompt templates, read [references/prompt-authoring.md](references/prompt-authoring.md).

For a Codex skill, use `$skill-creator` for the canonical skill format, discovery behavior, resource layout, UI metadata, initialization, validation, and packaging. Then read [references/skill-creator-companion.md](references/skill-creator-companion.md) for the division of responsibility between the two skills.

Keep `$skill-creator` guidance canonical and referenced rather than copied. If the two skills appear to disagree about Codex skill mechanics or policy, follow `$skill-creator` for those concerns.

## Working method

First recover the intended outcome, operating context, non-obvious constraints, and observable success criteria. Identify what the model cannot safely or reliably infer from the task itself. Add only those instructions, plus the decision criteria needed for ambiguous choices.

When editing existing instructions, trace the instruction owners, relevant tool contracts, and request assembly before choosing a change. State the target model or environment when it affects the advice; verify model-specific assumptions against current documentation or observed behavior. Preserve still-valid behavior and load conditional detail only where it changes the current decision

For tool descriptions, request assembly, or behavioral validation, read the corresponding sections of [references/prompt-authoring.md](references/prompt-authoring.md), including when the deliverable is a Skill

## Completion check

Before delivery, make generation and style guidance express an executable target behavior. Preserve explicit user preferences, product constraints, format-sensitive examples, and guards against demonstrated failures. Wording, length, or repetition alone does not establish a defect; remove or rewrite a boundary only when its valid purpose remains covered

Then verify that the scope is clear, instructions affect real decisions, open-ended work has useful decision criteria, fragile operations retain necessary invariants, completion or stopping conditions exist where needed, stable and dynamic content are separated, and every retained rule contributes distinct decision value rather than emphasis or decorative completeness.
