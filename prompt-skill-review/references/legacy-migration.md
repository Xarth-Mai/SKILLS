# Legacy prompt and collection migration

Use this procedure for existing instructions regardless of who wrote them or their format. Audit against the real task contract, not conformity with the authoring Skill. This is a risk-controlled engineering workflow; its routing labels are work decisions, not measured quality scores.

## 1. Inventory the actual instruction surface

Map entrypoints, descriptions/triggers, shared system/developer instructions, dynamic templates, conditional references, examples, tool descriptions, schemas, validators, and generated/deployed copies. Record source revision and callers. Identify what actually reaches the model and what the program reads back.

A Markdown-only export is useful source evidence, not a complete repository snapshot. Track each referenced script or resource as confirmed available, confirmed missing, or unverified in the full repository. Absence from a deliberately filtered export is not a missing-dependency finding.

Group work by shared contract and callers, not only by file. Inventory the whole requested scope first, then investigate and edit bounded units. Do not put an entire unrelated collection into one undifferentiated rewrite prompt.

## 2. Recover requirements without canonizing history

Read current briefs, authoritative product decisions, callers and tool contracts, existing prompt text, tests, and representative traces. Establish applicability and provenance rather than assuming one universal precedence among repository files. The host's actual instruction hierarchy and the user's authorization still apply.

Classify requirements as confirmed mandatory, preference, confirmed obsolete/incorrect, or unresolved. Do not promote every old sentence to a hard invariant, or discard a strange guard merely because its purpose is unclear. Historical successes are regression candidates, not proof that all their behavior was correct.

Use a compact source-to-requirement-to-check mapping for consequential units. Preserve permission limits, conditions, exceptions, alternatives, data provenance, exact protocol strings, and supported fallback behavior. Keep review advice and invented best practices out of the frozen business contract.

## 3. Assign a disposition and explain why

| Disposition | Evidence and action |
| --- | --- |
| Keep | No material defect established; retain working instructions. Optional optimization experiments remain possible. |
| Patch | Localized omission, contradiction, interface mismatch, or demonstrated failure; fix within a coherent design. |
| Structural refactor | Interacting rules or mixed responsibilities make local patches insufficient; recover the contract, then produce a reorganized candidate. |
| Needs requirements decision | Authoritative sources conflict, intent is materially unknown, or changing behavior/permission is necessary; isolate the decision and continue independent safe work. |

Minimum repair means minimum unrelated semantic change, not the fewest changed lines. Do not turn a hypothesis about style, order, or repetition into a release blocker. For an optimization request, state a testable intervention even when no static defect exists; do not claim the old version is invalid to justify it.

Prioritize by impact, frequency, known failures, shared reach, and reversibility. High-risk defects deserve prompt investigation, but high-risk candidates require isolated validation rather than immediate live rollout. Do not infer behavioral risk solely from file length.

## 4. Hand off structural work without losing evidence

When prompt-skill-authoring is available, provide:

- original files and revision plus authoritative context;
- assembled-request and caller/dependency map;
- confirmed requirements with conditions, preferences, and unresolved intent;
- known failures and legitimate formerly passing cases;
- protected interfaces, permitted edit scope, and proposed hypothesis;
- acceptance checks, execution authorization, rollout and rollback constraints.

Provide source references as well as the summary. The authoring Skill should recover details from the originals. This is a logical handoff, not a requirement to spawn another agent or install a sibling Skill. If unavailable, return a self-contained work package or use available authoring guidance within authorization.

## 5. Review both preservation and execution

Review coverage from old confirmed requirements to the candidate and justification from new obligations back to their sources. Inspect deletions, scope changes, fallback changes, and strengthened prohibitions explicitly. Check all consumers when a shared rule or protocol changes.

Then use the local [evaluation protocol](evaluation.md). Include formerly successful cases, known failures, task branches, exceptions, representative long inputs, and independent holdouts. Compare actual outputs and action traces under comparable settings. No static review, self-rating, or approval by another model proves behavioral equivalence.

An improved overall rate cannot hide an unacceptable permission or evidence-integrity regression. Conversely, identical prose is not required when flexible language is part of the task. Predefine the gates; do not alter them after seeing which variant wins.

## 6. Promote bounded, reversible units

Record four statuses separately: inventory/review complete, candidate edited, behavioral validation complete, and approved for deployment. “Edited” is not “validated,” and “validated on these cases” is not “universally optimal.” Use existing versioning, tests, and deployment controls where possible.

Retain the original revision, coordinate shared caller updates, identify generated/deployed copies, and define rollback through the real deployment mechanism. Use side-effect-free fixtures for action tests. Without authorized model runs, deliver static findings, candidates, and a prioritized runnable test plan; keep empirical claims and live replacement pending.

Report per-unit decisions, material findings, protected behavior, changed requirements with authority, actual tests, unresolved items, and the next release gate. An unresolved unit should not prevent unrelated verified improvements.
