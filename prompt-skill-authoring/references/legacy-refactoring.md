# Contract-preserving legacy refactoring

Use when rewriting existing instructions or implementing a migration plan. This is an engineering procedure, not a claim that a particular format improves every model. Keep production instructions focused on their task; the migration records belong with development evidence.

## 1. Accept a source-grounded handoff

Recover the existing prompt and revision, authoritative requirements, relevant callers and assembled messages, input/output interfaces, tools and permissions, examples, known failures, previously successful cases, and proposed acceptance checks. Read the underlying material, not only the reviewer's summary. Record unavailable context rather than invent it.

For a collection, identify the unit of change: one independent prompt, or a coordinated set of shared instructions and consumers. A directory is not necessarily a behavioral boundary. Inspect generated/deployed copies and their generator; edit the maintained owner rather than a disposable copy. A filtered Markdown export does not prove referenced scripts or assets are absent.

Classify recovered provisions as confirmed requirements, preferences, obsolete/incorrect provisions with evidence, or unresolved intent. Preserve conditions and exceptions. Historical output may reveal a useful dependency or an old bug; evaluate it against the contract before treating it as expected output.

## 2. Choose the rewrite scope deliberately

Use a local patch for a localized defect. Use a structural refactor when intertwined rules, duplicated ownership, mixed task modes, or accumulated patches prevent a coherent specification. A coherent old prompt may still receive an experimental candidate when optimization is requested; label the intervention and its unverified benefit.

Preserve business semantics while freely improving organization where justified. Do not force a new template, split every phrase into a bullet, remove all repetition, or convert every exclusion into positive prose. Useful operational detail and tested reminders can survive a full rewrite.

Keep changes to product behavior, model selection, fees, permissions, external side effects, data truth, and accepted output interfaces separate from wording cleanup. Implement such changes only when authorized and covered by appropriate tests. No amount of improved wording can repair an unavailable tool or an impossible task contract.

## 3. Check semantics in both directions

For consequential changes, maintain a compact change record:

| Requirement | Source and condition | Candidate location | Disposition | Acceptance check |
| --- | --- | --- | --- | --- |
| R1 | Current brief: draft only | Action boundary | Preserved | No send call |
| R2 | Legacy text: remove method details | Content rules | Preserved | Names remain allowed if the contract allows them |

Use explicit dispositions such as preserved, clarified without narrowing, relocated, confirmed obsolete, authorized behavior change, or unresolved. Explain consequential removals, added obligations, changed defaults, and changed exceptions; a line-by-line commentary is unnecessary.

Check original-to-candidate coverage and candidate-to-source justification. A new prohibition, mandatory artifact, approval gate, source requirement, or fallback is a behavior change unless supported by the contract. Preserve exact identifiers, template variables, enum values, machine-read headings, artifact names, and protocol-sensitive examples when their consumers depend on them. Move or rename them only with coordinated caller changes and tests.

## 4. Validate without redefining success

Freeze the acceptance contract before judging the candidate. Inspect two distinct risks:

- **Semantic drift:** requirements were lost, strengthened, weakened, or given different conditions. Use source-based review and interface tests.
- **Behavioral regression:** meaning is preserved, but the target model executes less reliably. Compare actual outputs/actions on baseline and candidate.

Include representative normal cases, known failures, previously successful cases, conditional branches and permitted exceptions. Test combined requirements and shared callers. Keep holdout cases out of rewriting and example selection. Exact output-string equality is useful for protocol constants, not for flexible prose quality.

Do not test action prompts by replaying real sends, purchases, deletion, or publication. Use fixtures, dry-runs, or isolated environments. Obtain the required authorization for paid calls and sensitive inputs. Compare equivalent settings and budgets; report capability limits and absent execution honestly.

## 5. Separate candidate creation from replacement

Keep a reproducible baseline containing prompt/resource versions, relevant assembly and runtime settings, and parser/validator versions. No need to introduce a new platform when Git and the existing test harness suffice.

Work in bounded units with an identifiable parent revision. Treat a shared contract and its dependent changes as one coordinated unit; do not release incompatible halves. Record the accepted gate and rollback point before promotion. A Git revert alone may not restore generated or deployed copies, so identify the existing sync/deployment mechanism.

When model execution is unavailable, complete authorized edits and static checks, deliver the candidate and test plan, and mark behavioral validation pending. Do not claim equivalence or silently replace live prompts. Continue unrelated safe work instead of blocking a whole collection on one unresolved requirement.

## 6. Deliver a reviewable candidate

Return the usable patch, concise semantic change record, affected callers, actual static/behavioral results, unresolved decisions, and rollback reference. Keep candidate quality, behavioral evidence, and deployment readiness separate. A second review should use the original contract and sources, not merely approve the author's rationale.
