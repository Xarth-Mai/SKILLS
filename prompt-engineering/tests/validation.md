# Migration validation status

- Baseline: main at `6e846d8a7403b44360b53605b57eb302e91321fc`
- Branch: `feat/prompt-engineering-unification`
- Intent: consolidate two former Skill entrypoints into one `prompt-engineering`; retain professional guides, JSONL fixtures, permission boundaries and review-only mode.
- Preserve `product-design-engineering` independently and unchanged.
- Static validation: verify frontmatter, files, reference paths, JSONL and README routing on resulting branch before promotion.
- Target-model A/B evaluations: **NOT RUN** (no controlled target-model harness).
- Production user outcomes: **NOT RUN** (no deployment or production configuration changes).
- Candidate in a branch is not evidence of higher instruction-following success.
