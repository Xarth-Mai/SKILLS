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

If the answer is unclear, shorten, merge, relocate, or remove it.

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

## Make quality testable

Translate important quality requirements into properties the model can inspect. Examples include whether major claims are supported, terminology remains consistent, each section has a distinct purpose, required fields are present, or the final artifact satisfies a schema.

For iterative work, define when further searching, retrying, revising, or tool use should stop. The strength of the stopping condition should match the cost and risk of continued action.

## Use examples only when they add information

Examples are valuable when a rule or schema leaves a meaningful boundary ambiguous: a subtle classification, house style, unusual output pattern, or representative edge case.

Keep examples few and representative. Their job is to demonstrate the target pattern, not to decorate the prompt or exhaust the space of possible inputs.

## Refactor with minimal semantic change

When improving an existing prompt:

1. Recover the behavior it is trying to preserve.
2. Keep real constraints and user choices.
3. Merge semantically duplicated rules.
4. Replace vague requirements with decision-relevant criteria where necessary.
5. Move conditional knowledge to the context that needs it.
6. Separate stable instructions from dynamic request data.
7. Add completion or stopping criteria only where the workflow needs them.
8. Leave already-clear instructions intact when a formatting change would not improve decisions or maintainability.
