# Companion Use with `$skill-creator`

Read this reference only when the deliverable is a Codex skill or an update to one.

## Responsibility split

`$skill-creator` is authoritative for Codex skill mechanics, including:

- skill anatomy and supported files;
- naming and discovery behavior;
- `description` and invocation policy requirements;
- `agents/openai.yaml` conventions;
- initialization and resource layout;
- progressive disclosure mechanics;
- validation and forward-testing guidance;
- packaging expectations.

`$prompt-skill-authoring` adds instruction-design judgment inside that framework. Use it to decide:

- which information actually changes the agent's decisions;
- what belongs in the always-loaded instruction surface versus conditional context;
- how much procedural control the task risk requires;
- how to express outcomes, decision criteria, boundaries, and stopping conditions;
- whether an example materially resolves ambiguity;
- whether a new rule fixes a demonstrated failure or merely adds speculative complexity.

## Normal handoff

When creating a new Codex skill, use `$skill-creator` to establish the canonical structure and required metadata. Apply this skill while writing or refactoring the instruction content. Return to `$skill-creator` for its validation and packaging workflow.

When updating an existing skill, preserve its supported structure, metadata, policy, dependencies, and unaffected behavior according to `$skill-creator`; use this skill only for the instruction-design changes actually requested.

## Keep governance canonical

Keep `$skill-creator`'s structural rules in that canonical skill and reference it when the workflow genuinely depends on those mechanics.

If a project-specific skill needs a non-obvious invariant that happens to resemble a general skill-creation rule, state the project invariant in terms of the concrete behavior it protects rather than reproducing generic creator guidance.
