# Prompt Authoring

Read this reference when creating or refactoring ordinary prompts, system/developer instructions, agent instructions, or reusable prompt templates.

## Define the target state

Express what a successful result looks like and how the model should choose among reasonable possibilities. Prefer observable properties and decision criteria over broad quality adjectives.

Useful instruction categories include:

- objective and scope;
- non-obvious context;
- decision criteria;
- real business, permission, or data boundaries;
- tool-use conditions that are not already obvious from the tool contract;
- completion or stopping conditions;
- output contract;
- examples only when they resolve genuine ambiguity.

These are optional components, not a mandatory template.

## Spend instruction budget on decision-changing information

Assume the model already understands normal prose, common software practices, ordinary reasoning, and generic task execution. Add a rule when its absence could plausibly cause a materially different choice or result.

A useful test for each sentence is:

> What important behavior would change if this sentence were removed?

If the answer is unclear, inspect the rule's owner, callers, and available failure history before removing it. Preserve useful context and working behavior; treat uncertain deletions as hypotheses rather than improvements already established

## Match control to risk

For open-ended work, specify the outcome and the criteria that matter, then let the model choose an appropriate path.

Use tighter procedures when the sequence or exact operation is itself meaningful, such as irreversible mutations, migrations, approval gates, retries with external side effects, or workflows where ordering preserves correctness.

Preserve operational invariants without turning optional conventions into absolute rules.

## Keep generation context pointed at the desired behavior

Describe the behavior, structure, evidence standard, tone, or decision process you want the model to produce. When a hard boundary is necessary, state it narrowly and define the useful action at that boundary, such as narrowing a claim, asking for authorization, using a fallback, or stopping safely.

For writing tasks, prefer criteria such as contribution, evidence, coherence, specificity, or audience fit when those properties are what actually matter.

## Separate stable instructions from dynamic input

Keep durable identity, operating principles, permissions, tool policy, and completion criteria in the stable instruction layer. Put the current task, parameters, user-provided materials, and request-specific preferences in the request layer.

Keep stable rules in their authoritative instruction layer and request-specific facts in the request context, so each piece of information has one durable home.

When cache behavior is relevant, inspect the actual request assembly and the target provider's supported semantics. Place reusable content before changing inputs where the protocol permits it, and measure cache reuse from recorded usage rather than assuming that text organization proves a saving

## Tool descriptions and deterministic work

Describe tools as executable contracts: purpose, use and non-use conditions, parameter meaning, limits, side effects, returned evidence, and failure behavior. Check the description against the implementation; keep contract detail even when it is long. Put substantial teaching examples and business workflow guidance in the relevant Skill or reference instead of repeating them in every tool description

Assign calculations, schema validation, exact transformations, and permission enforcement to existing code or structured interfaces when their inputs determine the result. Keep interpretation and ambiguous decisions with the model. Verify that the target runtime supports a proposed API feature before replacing prompt guidance or fallback code; preserve semantic validation and existing trust boundaries

## Make quality testable

Translate important quality requirements into properties the model can inspect. Examples include whether major claims are supported, terminology remains consistent, each section has a distinct purpose, required fields are present, or the final artifact satisfies a schema.

For iterative work, define when further searching, retrying, revising, or tool use should stop. The strength of the stopping condition should match the cost and risk of continued action.

For a behavioral change, compare the original and candidate on representative requests and inspect actions or artifacts against the intended outcome. Use existing evaluations when available; isolate consequential changes so regressions have an identifiable cause. Model self-assessment and format validation do not establish behavioral improvement. If no authorized model run is performed, report static checks separately and leave behavioral effectiveness unverified; restore a concise version of any rule whose removal causes a regression

## Use examples only when they add information

Examples are valuable when a rule or schema leaves a meaningful boundary ambiguous: a subtle classification, house style, unusual output pattern, or representative edge case.

Use examples to expose the relevant distinction while varying incidental length, wording, and structure when those properties are not requirements. Label illustrative examples accordingly; preserve exact examples where syntax or a required output contract depends on them

## Refactor with minimal semantic change

When improving an existing prompt:

1. Recover the behavior it is trying to preserve.
2. Keep real constraints and user choices.
3. Consolidate duplicated rules when they conflict, drift, or cause a demonstrated maintenance problem; preserve deliberate recaps and useful local contract detail
4. Replace vague requirements with decision-relevant criteria where necessary.
5. Move conditional knowledge to the context that needs it.
6. Separate stable instructions from dynamic request data.
7. Add completion or stopping criteria only where the workflow needs them.
8. Leave already-clear instructions intact when a formatting change would not improve decisions or maintainability.
