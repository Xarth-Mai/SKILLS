# Instruction Design Antipatterns

Use this reference as a set of diagnostic hypotheses, not as a deletion checklist or content to paste into a generation prompt. A signal needs a concrete contract mismatch, demonstrated impact, or target-model evidence before it supports a fix. Explicit user preferences, real boundaries, useful context, and working recaps remain valid even when they match a pattern

## 1. Failure-world dominance ("pink elephant")

**Signal:** The instruction surface spends substantial context describing outputs, phrases, structures, or behaviors the model is supposed to avoid.

**Why it matters:** Those patterns become salient context and can crowd out the representation of the desired result. The prompt also becomes harder to maintain as the blacklist grows.

**Correction:** Specify the target behavior and observable success criteria. Keep a hard prohibition only when the boundary itself is important; make it narrow and operational.

## 2. Negative-pattern catalog

**Signal:** A long list enumerates undesirable wording, styles, mistakes, or examples.

**Why it matters:** The list teaches a detailed distribution of unwanted patterns while giving relatively little information about the preferred distribution.

**Correction:** Replace the catalog with a compact specification of the desired style, structure, evidence standard, or decision rule. Keep only independently necessary hard boundaries.

## 3. Boundary without useful next action

**Signal:** The prompt states a limit but does not define what the agent should do when the limit is reached.

**Why it matters:** The model must invent its own fallback, often inconsistently.

**Correction:** Add the appropriate behavior at the boundary: narrow the claim, request authorization, use a safe fallback, surface uncertainty, or stop.

## 4. Repeated emphasis instead of better instruction design

**Signal:** The same requirement appears multiple times with stronger typography or imperative language.

**Why it matters:** Repetition consumes context without clarifying the decision and can create accidental priority conflicts.

**Correction:** State the rule once, make its trigger and expected behavior explicit, and define priority only when a real conflict exists.

## 5. Abstract quality labels without decision criteria

**Signal:** Requirements rely on terms such as high quality, professional, deep, natural, robust, or elegant without defining what those terms mean for the task.

**Why it matters:** The model cannot reliably infer which observable tradeoffs should change.

**Correction:** Translate important quality goals into inspectable properties or selection criteria relevant to the domain.

## 6. Over-specified open workflow

**Signal:** A flexible task is forced through a long, fixed sequence even though several approaches could succeed.

**Why it matters:** The procedure can block useful adaptation and encodes assumptions that are not true for every request.

**Correction:** Specify the result, key invariants, and decision criteria. Preserve fixed sequencing only where order has concrete semantics.

## 7. Under-specified fragile workflow

**Signal:** A workflow with irreversible changes, permissions, retries, external side effects, or ordering constraints is described only by a broad objective.

**Why it matters:** Excess autonomy can cause duplicate mutations, unsafe retries, authorization mistakes, or inconsistent state.

**Correction:** Preserve the non-obvious invariant, authorization point, idempotency behavior, or stopping condition that protects correctness.

## 8. Single failure generalized into a universal rule

**Signal:** One incident or narrow example becomes a global requirement for all future tasks.

**Why it matters:** The patch can degrade unrelated use cases and gradually turn the prompt into a historical accident log.

**Correction:** Identify the general decision error behind the failure and add the smallest rule that addresses that class only when evidence supports it.

## 9. Speculative edge-case accumulation

**Signal:** The prompt anticipates many hypothetical cases that have not occurred and are not required by the task's risk profile.

**Why it matters:** The core objective becomes harder to discover and new rules can interact unpredictably.

**Correction:** Keep real invariants. Add new edge handling when realistic usage or concrete risk demonstrates a need.

## 10. Duplicate guarantees from a higher layer

**Signal:** A local prompt repeats policies, tool contracts, generic platform behavior, or stable rules already enforced reliably elsewhere.

**Why it matters:** Duplicates increase context cost and drift when the source of truth changes.

**Correction:** Resolve contradictions at the authoritative owner and remove copies that cause drift. Preserve a local contract detail or deliberate recap that serves the task; harmless overlap alone is not a finding

## 11. Stable policy mixed with request data

**Signal:** Long-lived instructions contain current task parameters, user materials, one-off preferences, or volatile facts, or changing values are inserted into a reusable prompt prefix

**Why it matters:** The prompt becomes harder to reuse, cache, reason about, and update safely.

**Correction:** Separate durable behavior from per-request inputs and context. Preserve stable instructions on every request when the protocol requires them; evaluate cache reuse using the actual assembly order and recorded usage rather than treating repeated transmission as a defect

## 12. Conflicting instructions without a decision rule

**Signal:** Two reasonable requirements can pull in different directions, but the prompt does not define which consideration wins or how to trade them off.

**Why it matters:** Behavior becomes dependent on incidental wording or position.

**Correction:** State the relevant priority or decision criterion only for the conflict that actually exists.

## 13. Example that adds no information

**Signal:** An example merely restates an already-clear rule or schema.

**Why it matters:** It spends context without reducing ambiguity and may accidentally overfit the model to incidental details.

**Correction:** Remove it. Keep examples that demonstrate a subtle boundary, house style, or genuinely ambiguous pattern.

## 14. Example contaminates the target distribution

**Signal:** A negative example includes detailed unwanted phrasing or structure that the generation prompt otherwise would not need to mention.

**Why it matters:** The example increases salience of the pattern being discouraged.

**Correction:** Prefer a positive representative example or move negative diagnostics into a review-only context.

## 15. Missing completion or stopping condition

**Signal:** Iterative search, revision, retry, or external action has no meaningful condition for ending.

**Why it matters:** The agent may stop too early, continue without benefit, or repeat costly actions.

**Correction:** Define an observable completion condition proportional to the task's cost and risk.

## 16. Overbroad Codex skill description

**Signal:** The skill description uses catchall wording, exhaustive capability lists, or broad neighboring domains to maximize invocation.

**Why it matters:** Discovery becomes noisy and the skill is injected into unrelated tasks.

**Correction:** Describe the actual capability and the situations in which it applies; add an exclusion only when it prevents a likely misroute.

## 17. `SKILL.md` carries all conditional detail

**Signal:** Mode-specific procedures, schemas, large examples, and occasional edge guidance all live in the always-loaded entrypoint.

**Why it matters:** Every invocation pays the context cost and important routing becomes harder to see.

**Correction:** Keep shared purpose, essential constraints, and routing in `SKILL.md`; move substantial conditional material to focused references and deterministic repeated logic to scripts when warranted.

## 18. Cross-skill or tool dependency assumed without a contract

**Signal:** Instructions depend on another skill, tool, resource, or environment without establishing that it is available or explaining the responsibility split.

**Why it matters:** The workflow becomes brittle and may silently fail in a different target environment.

**Correction:** Refer to another skill or tool only when the workflow genuinely requires it and the target environment provides it. Define which component owns which concern.

## 19. Review contaminates the generation prompt

**Signal:** The final rewrite copies the review's catalog of failure patterns into the instructions used for generation.

**Why it matters:** Diagnostics become generation context, increasing salience and instruction load.

**Correction:** Keep the diagnosis in the review output; rewrite the production prompt as a compact specification of desired behavior and necessary boundaries.

## 20. Rewrite expands scope or permission

**Signal:** A cleanup introduces new external actions, broader authority, a different product choice, or extra responsibilities that were not part of the original task.

**Why it matters:** Instruction improvement has silently changed the user's intent or authorization model.

**Correction:** Preserve original scope and permissions. Treat any expansion as a separate user decision.

## 21. Tool description differs from the implementation

**Signal:** Parameters, side effects, failure modes, or claimed outputs differ from the callable tool, or the description omits a distinction needed to choose it safely

**Why it matters:** The model can follow the description correctly and still perform the wrong action or overclaim what the result proves

**Correction:** Align the contract with observed implementation behavior. Add the missing semantics; move substantial tutorials and unrelated conversational steering to their instruction owner

## 22. Model-specific advice without current evidence

**Signal:** A cleanup treats a model habit, API feature, or migration recommendation as universal across providers and runtimes

**Why it matters:** Removing a working guard or fallback can regress the target environment even when the advice applies elsewhere

**Correction:** Verify the actual target and supporting documentation or behavior. Preserve required version pins, business limits, and exact interfaces; flag uncertain behavioral claims for a before-and-after probe

## 23. Deterministic work delegated to model judgment

**Signal:** The model computes fixed arithmetic, validates a schema, or executes a fully determined transformation that existing code can perform

**Why it matters:** Repeated inference adds variability and cost without providing a necessary decision

**Correction:** Reuse deterministic code for that operation while preserving the model's actual interpretation task. Verify runtime support before replacing a prompt or fallback with an API feature

## Review priority

Prioritize findings in this order when applicable:

1. scope, permission, or destructive-action errors;
2. trigger and routing errors;
3. conflicting or misleading decision rules;
4. context contamination that changes generated behavior;
5. missing invariants or stopping conditions in fragile workflows;
6. unnecessary complexity and maintenance cost;
7. cosmetic wording issues.
