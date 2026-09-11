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
- Check for historical negations that name retired steps, agents, tools, or artifacts. Confirm retirement against current callers and contracts, then delete the obsolete enumeration and retain the current positive action; preserve negative boundaries that still prevent concrete routing, safety, permission, data-truth, or artifact-integrity errors
- Prefer the smallest change that explains and fixes an observed problem.
- For Codex skills, preserve progressive disclosure and defer canonical skill mechanics to the installed `$skill-creator` when it is relevant and available.

## Workflow

1. Recover the intended outcome, scope, target model or environment, and real boundaries from the request and available context. State material assumptions; ask only when unresolved information changes the scope or a consequential decision. Inspect the relevant instruction files, tool descriptions, request assembly, and their callers
2. Inspect routing separately from behavior, then check decision value, specificity, conflicts, examples, completion conditions, progressive disclosure, and dependency assumptions. Compare tool descriptions with actual behavior. Preserve user preferences, operational constraints, useful context, and demonstrated safeguards; length, negation, repetition, or an antipattern match alone is not evidence of harm. Trace suspected obsolete rules to available history and current model documentation or observed failures
3. Read [references/antipatterns.md](references/antipatterns.md) when a detailed diagnostic pass is useful.
4. Report only findings with meaningful behavioral or maintenance impact.
5. For each finding, give its location, the relevant text or code, behavioral impact, evidence and confidence, and smallest useful correction. Distinguish observed conflicts or contract mismatches from model-dependent hypotheses. Include a concrete patch for supported findings within the requested scope; keep uncertain hypotheses as flagged items rather than applying speculative changes
6. Provide a complete rewrite only when the user asks for one or when a local patch cannot resolve the structural problem.
7. Re-check the fix against the original goal and all affected callers, contracts, and tests. Preserve scope and permissions; apply changes only when the user's request authorizes editing
8. For consequential behavioral changes, compare original and candidate actions or artifacts with an existing eval or a representative bounded probe when execution is authorized. Report what actually ran and what remains unverified. Restore a concise guard if removal regresses behavior; a clean review requires no manufactured diff

## Output

Lead with the overall verdict. Group findings by impact, not by how many categories can be named. Distinguish required fixes, useful improvements, and parts that should remain unchanged. Prefer concise patches over wholesale rewrites when the existing design is fundamentally sound.
