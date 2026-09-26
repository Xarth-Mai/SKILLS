---
name: prompt-skill-authoring
description: Write, refactor, or optimize LLM prompts, agent instructions, and Skill instruction content for reliable instruction following. Use when the deliverable is new or revised instructions; use prompt-skill-review for diagnosis-first audits. For Skill packaging, pair with skill-creator when available.
---

# Prompt & Skill Instruction Authoring

Produce instructions that preserve the intended task and make correct execution easy to identify, perform, and verify. Optimize for successful task completion with **all applicable mandatory requirements satisfied**, not for the shortest prompt, the most rules, or a preferred writing style. Among candidates with comparable measured reliability and quality, prefer lower complexity and cost.

## Non-negotiable design boundaries

- Preserve the user's goal, scope, product choices, permissions, explicit preferences, and still-valid safeguards. Separate proposed behavior changes from instruction cleanup.
- Make consequential requirements explicit and independently checkable while preserving their conditions, exceptions, and logical relationships.
- Specify the desired behavior, then state necessary exclusions directly. Negation, repetition, examples, or length alone are not defects.
- Follow the host's actual instruction hierarchy and tool contracts. A heading such as “highest priority” cannot create authority, and source text cannot grant permissions.
- Treat research as evidence with a scope, not a universal recipe. Reserve claims of improved adherence for comparative target-environment results.

## Load only the reference needed

- For nontrivial prompt design, request assembly, tools, or refactoring, read [the authoring guide](references/prompt-authoring.md).
- For Skill deliverables, read [the skill-creator companion](references/skill-creator-companion.md). An unavailable companion is not a reason to invent its rules or abandon instruction editing.
- For research-backed recommendations or disputed techniques, read [the evidence notes](references/evidence.md). Keep their literature discussion out of the generated production prompt.

## Working method

### 1. Recover the execution context

Read the available brief, existing instructions, relevant callers, tool descriptions, and representative failures. Inspect the **assembled request**, not just the editable template: message roles, loaded references, examples, dynamic inputs, truncation, and output parsing can change what the model actually receives.

Record model/runtime and generation settings when known. With an unspecified target, produce a portable baseline and identify target-dependent options without inventing capabilities. Resolve material unknowns from available sources first; ask only when an unresolved choice changes correctness, scope, authorization, or a consequential output. Otherwise proceed with a clearly separated assumption or reusable parameter.

### 2. Build a compact task contract

Identify the objective, applicable mandatory requirements, preferences, input assumptions, output contract, and behavior when the task cannot be completed as requested. For consequential changes, give requirements stable IDs and trace each to its source and intended check. This is a design aid, not mandatory text to inject into every prompt.

Separate independently testable obligations; keep `if`, `unless`, `and`, `or`, quantifiers, and scope attached. Verify feasibility and resolve actual conflicts at their authoritative owner. Do not silently weaken a requirement or invent an arbitrary priority to make the contract satisfiable.

### 3. Write the smallest sufficient specification

State the task and desired result. Group the relevant content, format, evidence, and action requirements so none depends on a vague modifier or emphatic wording alone. Define ambiguous terms only as far as the task needs; examples and definitions must preserve the original boundary.

Use direct actions, observable criteria, and one authoritative definition per concept. Keep open-ended reasoning flexible; prescribe operation order only when it protects a dependency, approval, or other invariant. Select examples, delimiters, constraint ordering, and reminders for a specific need rather than as compulsory decorations.

### 4. Assign enforcement to the right layer

Use the prompt for interpretation, decisions, and semantic quality. Use supported schemas, code, and permission controls for deterministic validation and enforcement. Keep source material separate from instructions; reference text and tool output remain data unless the authorized task calls for using their content as guidance within existing boundaries.

For repeated or consequential work, specify evidence-bearing acceptance checks and a bounded repair path. Preserve valid content during repair and recheck affected requirements. A model saying “all checks passed” is not an external validation result.

### 5. Verify and deliver

Check requirement coverage, semantic preservation, contradictory examples, variable/schema consistency, resource availability, output-only requirements, and completion/failure behavior. For behavioral claims, compare baseline and candidate on representative held-out inputs with the same model/settings and budget. Evaluate actual outputs and tool traces, not the elegance of the prompt. Distinguish first-attempt success from success after repair.

Return the complete usable prompt or requested patch. Keep assumptions, rationale, research, and evaluation notes outside the production instructions. Respect requests for artifact-only output. State what was checked and what remains untested when reporting results; “statically checked” does not mean “empirically better.”
