# Companion use with skill-creator

Use this reference when the artifact is a Skill. Keep instruction design separate from host-specific packaging.

## Responsibility split

Use an available `skill-creator` for the host's supported anatomy, discovery metadata, UI metadata, initialization, packaging, and structural validation. This authoring Skill owns task contracts, requirement expression, semantic preservation, trust boundaries, and behavioral evaluation design. Host rules and actual tool schemas remain authoritative.

If `skill-creator` is unavailable, preserve the existing valid structure and consult the target host's current documentation when needed. Complete the instruction work and distinguish checks actually performed from unavailable host validation. Do not assume an invocation, validator, or dependency exists.

## Entrypoint and references

Keep the entrypoint focused on when the Skill applies, its objective, essential boundaries, working method, and deliverable. Place substantial examples, detailed procedures, and research in local references with explicit read conditions. Every mandatory invariant needed on all executions belongs in the entrypoint or another layer guaranteed to be loaded.

Keep references reachable from `SKILL.md` and usable when the Skill directory is installed alone. An optional sibling Skill may help; an undeclared sibling file must not become a required dependency. Load only the selected reference rather than the entire library.

Make `description` distinguish the actual intent from neighboring tasks. Keep execution details in the body. Align `agents/openai.yaml` with the description, real dependencies, and invocation policy; preserve existing permissions.

## Validate two different things

1. **Discovery and packaging:** valid frontmatter and names, existing paths, compatible metadata, supported tools, and positive/negative trigger examples.
2. **Instruction behavior:** whether invoking the Skill produces a correct prompt or audit, and whether the resulting prompt performs well on its own target task.

A valid package does not demonstrate correct routing. A well-written generated prompt does not demonstrate downstream adherence. Test these layers separately when the runtime is available.

## Canonical references

Checked 2026-09-26; verify current host details before a format migration.

- [Agent Skills specification](https://agentskills.io/specification): portable structure, metadata, local resources, and progressive disclosure.
- [OpenAI Skills documentation](https://developers.openai.com/codex/skills): host activation, creator workflow, and optional UI metadata.

These are packaging references, not evidence that one phrasing achieves a higher adherence rate.
