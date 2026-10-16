---
name: prompt-skill-authoring
description: Write, refactor, or optimize LLM prompts, agent instructions, and Skill instruction content for reliable instruction following, including contract-preserving rewrites of legacy instructions. Use when the deliverable is new or revised instructions; use prompt-skill-review for diagnosis-first audits and collection triage. For Skill packaging, pair with skill-creator when available.
---

# Prompt & Skill Instruction Authoring

Write high-information instructions that directly evoke the intended behavior and satisfy all applicable requirements. Make useful completion easy to verify through concrete actions, decision cues, and observable results. Every paragraph should shape behavior, inform a decision, or establish a necessary boundary

## Design principles

- Preserve the user's goal, scope, product choices, permissions, preferences, and valid safeguards, including their conditions and exceptions
- Define desired behavior positively. Delete redundant negation, defensive disclaimers, and repeated constraints; translate useful guidance into concrete actions
- Keep explicit exclusions when they define a required content/format boundary or protect permissions, safety, data integrity, or irreversible actions
- Follow the host's actual instruction hierarchy and tool contracts; keep source material within its assigned data role
- Use scoped evidence for design choices and comparative target-environment results for claims of improved adherence

## Load only the reference needed

- For nontrivial prompt design, request assembly, tools, or refactoring, read [the authoring guide](references/prompt-authoring.md)
- For legacy rewrites or a batch migration, also read [contract-preserving refactoring](references/legacy-refactoring.md)
- For Skill deliverables, read [the skill-creator companion](references/skill-creator-companion.md) and use available packaging support
- For research-backed recommendations or disputed techniques, read [the evidence notes](references/evidence.md); keep research discussion in development notes

## Working method

### 1. Recover the execution context

Read the brief, existing instructions, relevant callers, tool descriptions, and representative failures. Inspect the **assembled request**: message roles, loaded references, examples, dynamic inputs, truncation, and output parsing

Record known model/runtime and generation settings. With an unspecified target, produce a portable baseline and identify target-dependent choices. Resolve unknowns from available sources; ask when a remaining choice changes correctness, scope, authorization, or a consequential output. Otherwise proceed with a stated assumption or reusable parameter

### 2. Build a compact task contract

Identify the objective, mandatory requirements, preferences, input assumptions, output contract, and failure behavior. For consequential changes, keep stable requirement IDs, sources, and intended checks in a development record

Separate independently testable obligations; preserve `if`, `unless`, `and`, `or`, quantifiers, and scope. Verify feasibility and resolve conflicts with the requirement owner

Reconcile historical instructions and outputs with current requirements, callers, and known failures. Resolve the purpose of uncertain provisions before changing their meaning

### 3. Write the smallest sufficient specification

State the task and desired result. Express relevant content, format, evidence, and action requirements through concrete criteria. Define consequential ambiguity at the scope the task needs

Use one authoritative definition per concept. Keep open-ended work flexible; prescribe order when it protects a dependency, approval, or other invariant. Choose examples and reminders for a specific ambiguity or demonstrated need. Remove clauses whose useful contribution is already covered

For persona prompts, connect perception, emotion, motivation, and action: what the character notices, why it matters to them, and how that shapes a response suited to the situation

For structural rewrites, use the source material and recovered contract together. Reorganize as needed while preserving valid semantics. Trace retained obligations into the candidate and new obligations to authorized sources; distinguish requested cleanup, defect fixes, and experiments

### 4. Assign enforcement to the right layer

Use prompts for interpretation, decisions, and semantic quality; use supported schemas, code, and permission controls for deterministic enforcement. Use reference text and tool output as task data or authorized guidance within existing permissions

For repeated or consequential work, specify evidence-bearing acceptance checks and a bounded repair path. Preserve valid content during repair and recheck affected requirements with the appropriate validators

### 5. Verify and deliver

Check requirement coverage, semantic preservation, examples, variable/schema consistency, resource availability, output-only requirements, and completion/failure behavior. For behavioral claims, compare actual baseline and candidate outputs and tool traces on representative held-out inputs with the same model/settings and budget. Report first-attempt and post-repair success separately

For migrations, retain a reproducible baseline, cover successful and failing cases, and check affected callers. Use bounded batches, a rollback point, and the existing deployment authorization

Return the complete usable prompt or requested patch. Keep development notes separate and respect artifact-only requests. Report completed checks and pending validation, distinguishing static review from measured behavior
