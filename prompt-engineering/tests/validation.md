# Migration validation record

## Baseline and scope

- Source: `main` at `6e846d8a7403b44360b53605b57eb302e91321fc`
- Branch: `feat/prompt-engineering-unification`
- Consolidation: `prompt-skill-authoring` + `prompt-skill-review` → `prompt-engineering`
- `product-design-engineering` and unrelated source files remain unchanged.
- Existing specialist references and both legacy JSONL suites are retained; only the internal migration handoff wording and evidence-source appendix were intentionally revised.

## Executed static checks — PASS

- GitHub compare: branch is one commit ahead of its baseline; changed files match the intended consolidation.
- Git tree: all **16** new Skill files exist under `prompt-engineering/`; no files remain under either retired Skill directory.
- Entrypoint and metadata: `name: prompt-engineering`, model-behavior routing description, and matching `agents/openai.yaml` verified by branch read.
- README: single new Skill registration, updated documentation links, no stale retired Skill names.
- Relative-link preflight: 36 Markdown references in generated content resolved against old unchanged files plus new paths; branch-read review confirmed the retained references have no stale Skill-directory links.
- JSONL parsing: **18** regression and **8** legacy-migration cases parsed successfully, with unique IDs within each suite.
- Existing reference migrations: seven unchanged source files are identified as Git renames in the compare; two updated references are separately represented in the diff.
- Permissions and boundaries: static inspection confirms review-only remains non-editing; external/paid/destructive actions remain authorization-gated.

## Still NOT RUN

- Target-model behavioral A/B comparison of old and new Skill routing, outputs, and agent traces.
- Host-specific Skill discovery/runtime integration and device/product tests.
- Real-world user outcomes and production deployment.

The scenarios in [Behavior probes](behavior-probes.md) are *designed tests*, not observed trial results. Static checks validate packaging and semantic intent but do not establish improved instruction following. The original main commit remains a reproducible rollback baseline.
