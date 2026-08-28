---
name: prompt-skill-review
description: Audit existing LLM prompts, agent instructions, or Codex skill instructions for high-impact instruction-design problems and propose minimal fixes. Use when the user explicitly asks to review, audit, diagnose, simplify, or harden existing instructions rather than create them from scratch.
---

# Prompt & Skill Review

Evaluate whether existing instructions express the intended behavior with the minimum necessary control. Preserve valid intent, scope, product choices, permissions, and working behavior. Prioritize issues that can materially change model decisions over stylistic cleanup.

## Review principles

- Recover the intended task and operating context before judging the wording.
- Rank findings by behavioral impact: misrouting, scope expansion, permission mistakes, conflicting decisions, context contamination, fragile operations, and maintainability matter more than cosmetic phrasing.
- Give open-ended tasks enough decision criteria and autonomy; give genuinely fragile or high-risk operations the invariants, authorization points, and stopping conditions they require.
- Keep diagnosis separate from generation instructions. A review may name failure patterns without copying a catalog of those patterns into the rewritten prompt.
- Prefer the smallest change that explains and fixes an observed problem.
- For Codex skills, preserve progressive disclosure and defer canonical skill mechanics to the installed `$skill-creator` when it is relevant and available.

## Workflow

1. Identify the intended outcome, instruction layer, target model or environment, and real boundaries.
2. Inspect trigger/scope, decision value, target-state specification, specificity, workflow freedom, conflicts, repetition, examples, completion conditions, progressive disclosure, and dependency assumptions. For every generation or style rule, verify that it leads with an executable target state and can guide the intended decision on its own. Retain an accompanying prohibition only when it independently protects a concrete boundary.
3. Read [references/antipatterns.md](references/antipatterns.md) when a detailed diagnostic pass is useful.
4. Report only findings with meaningful behavioral or maintenance impact.
5. For each finding, state the location, behavioral impact, and smallest useful correction.
6. Provide a complete rewrite only when the user asks for one or when a local patch cannot resolve the structural problem.
7. Re-check the proposed fix against the original goal so the review itself does not add new scope, permissions, or unnecessary rules.

## Output

Lead with the overall verdict. Group findings by impact, not by how many categories can be named. Distinguish required fixes, useful improvements, and parts that should remain unchanged. Prefer concise patches over wholesale rewrites when the existing design is fundamentally sound.
