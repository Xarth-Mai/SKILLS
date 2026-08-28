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

When editing existing instructions, preserve still-valid behavior and change only what the current goal requires. Keep conditional detail outside the main instruction surface when it can be loaded only when relevant.

## Completion check

Before delivery, make every proposed generation or style instruction lead with the executable target behavior. Remove prohibitions, failure patterns, and negative examples when that target fully defines the decision. Retain a negative boundary only when it independently protects safety, permission, data truth, destructive effects, or another concrete invariant.

Then verify that the scope is clear, instructions affect real decisions, open-ended work has useful decision criteria, fragile operations retain necessary invariants, completion or stopping conditions exist where needed, stable and dynamic content are separated, and every retained rule contributes distinct decision value rather than emphasis or decorative completeness.
