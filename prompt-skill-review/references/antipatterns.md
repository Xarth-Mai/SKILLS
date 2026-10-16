# Diagnostic patterns

A pattern suggests a question. Support findings with the intended contract, an actual conflict, a representative failure, or scoped target-model evidence. Judge requested cleanup by its stated goal and each clause's contribution to behavior, decisions, or necessary boundaries

## High-impact checks

| Pattern | Establish before flagging | Smallest useful repair |
| --- | --- | --- |
| Lost requirement or scope drift | An obligation, condition, alternative, exception, or permission changed | Restore the original logic and trace it to its owner |
| Goal lost behind exclusions | Output can obey all bans while failing to perform the task | Define useful completion and required positive content |
| Ambiguous consequential boundary | Plausible interpretations produce materially different outputs | Define the intended scope from evidence; label unresolved assumptions |
| Unsatisfiable or conflicting requirements | The same applicable output/action must and must not have a property | Resolve at the real owner or expose the conflict; do not invent a priority |
| Misleading example | An example violates a rule or teaches an unintended mandatory pattern | Replace or label it; retain exact syntax where the contract depends on it |
| Wrong authority or source leakage | User data, retrieved text, or a tool result is treated as an instruction with permissions it lacks | Separate roles/data, align runtime enforcement, and test the boundary |
| Tool or schema mismatch | Claimed arguments, side effects, success evidence, or output differ from the actual interface | Correct the contract or caller; retain necessary implementation limits |
| Failure response breaks output protocol | Missing input triggers prose in JSON-only output, invented fields, or fabricated facts | Use an agreed schema state or host error path |
| Fragile workflow lacks an invariant | Side effects, retries, approvals, or dependencies have a concrete failure path | Add the invariant, authorization gate, idempotency rule, or bounded stop |
| Flexible work has a needless fixed procedure | The sequence blocks valid approaches or relies on false assumptions | Specify outcome and decision criteria; retain genuinely required order |
| Context assembly hides requirements | Required rules or evidence are omitted, truncated, overwritten, or never loaded | Fix assembly/routing before tuning prose |
| Deterministic validation replaced by confidence | Existing exact checks are bypassed by a model's self-approval | Run the actual check; reserve semantic judgment for meaning |
| Semantic checking replaced by a proxy | Digit/keyword scan is treated as proof of meaning-based compliance | Keep the scan as a signal and add grounded semantic review |
| Unbounded or destructive repair | Revision repeats side effects, removes valid information, or lacks a budget | Target failed requirements, preserve valid regions, and recheck dependents |
| Unsupported performance verdict | A static review, small cherry-picked sample, self-score, or altered rubric is called an adherence improvement | Separate evidence levels and run a controlled comparison |
| Skill discovery/dependency defect | Description misroutes a real neighboring request or a required resource is unavailable | Narrow routing or make the dependency explicit and supported |

## Checks that require nuance

### Positive behavior and necessary boundaries

Check whether the prompt gives the model a concrete behavior to produce. For persona prompts, look for a relationship between perceived cues, emotion, motivation, and action, with a response suited to the situation. Turn useful guidance into positive behavior definitions

Delete redundant negation, defensive disclaimers, and clauses whose purpose is already covered. Keep required content/format exclusions and boundaries protecting permissions, safety, data integrity, or irreversible actions, with their conditions and exceptions. Keep diagnostic catalogs in review material; use a focused counterexample when it resolves a real ambiguity

Requested cleanup can proceed on these semantic grounds. Attribute model failures or performance gains to wording only with relevant comparative evidence

### Repetition and prompt length

Consolidate conflicting duplicates and obsolete definitions. Retain grounding, required local contracts, and reminders with a distinct purpose or demonstrated benefit. Remove text whose decision value is absent or superseded. Measure results and input cost for performance claims; inspect truncation and placement on target tasks

### Order, emphasis, and authority

A hard-to-easy ordering result concerns estimated constraint difficulty in tested settings. It does not establish a global ranking of business importance or instruction authority. Test ordering of independent requirements; preserve dependencies. Typography is not a conflict-resolution policy.

### Roles, reasoning, and examples

Assess functional roles, tone, and user-requested characterization by the behavior they guide. Apply persona research within the tasks and models it studied

Review observable decisions, required operational steps, and requested user-facing explanations; leave internal reasoning flexible

Review examples for factual grounding, boundary clarity, and output consistency. Choose their number and detail for the ambiguity they resolve

### Retired workflow rules

Confirm retirement against current callers, contracts, and available history. Replace obsolete catalogs with the current intended behavior. Preserve a concise exclusion when it still prevents a real routing, permission, data-truth, or artifact-integrity failure. An unfamiliar rule is not necessarily obsolete.

## Severity and evidence

Use severity for consequences: a scope/permission violation or an impossible required contract can block deployment; a localized quality loss may need a focused fix; cosmetic differences need no finding. Do not turn this into a numeric score without a defined scoring model.

Label evidence independently:

- **Confirmed static defect:** directly supported by conflicting instructions, missing required data/resources, or a contract mismatch.
- **Observed failure:** reproduced or recorded in the target execution, with input/settings and output/trace available.
- **Hypothesis:** plausible model-dependent risk awaiting a comparative test.

Only include a hypothesis when it is useful and specific enough to test. A failure occurrence is not, by itself, proof that a particular phrase caused it.

## Primary-source anchors

Checked 2026-09-26. These sources motivate checks, not automatic findings:

- [InFoBench, Findings ACL 2024](https://aclanthology.org/2024.findings-acl.772/): decomposed requirements; evaluation does not prove a list-format advantage.
- [What Prompts Don't Say, Findings ACL 2026](https://aclanthology.org/2026.findings-acl.441/): implicit requirements can be fragile, but adding every requirement does not consistently help.
- [Order Matters, Findings ACL 2025](https://aclanthology.org/2025.findings-acl.646/): position effects under a scoped experimental setup.
- [Prompt Repetition, 2025 preprint](https://arxiv.org/abs/2512.14982): a counterexample to blanket anti-repetition advice, not a universal agent recipe.
- [Persona study, Findings EMNLP 2024](https://aclanthology.org/2024.findings-emnlp.888/): objective QA findings, not a ban on creative roles.
- [IHEval, 2025 preprint](https://arxiv.org/abs/2502.08745): conflicts between sources and instruction priorities.
- [OpenAI reasoning guidance](https://developers.openai.com/api/docs/guides/reasoning-best-practices): model-specific starting points, not cross-provider laws.
