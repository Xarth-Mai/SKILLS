# Prompt authoring: from task to executable behavior

Read for drafting, revising or consolidating instructions. For flexible social behavior, begin with [Behavior design](behavior-design.md); for demonstrations, see [Examples](examples.md). This reference handles task contracts, format fidelity, context and tools.

## 1. Recover the task, not just its wording

Identify the real user outcome; who or what executes the prompt; available inputs and trusted evidence; required outputs or actions; important preferences; and explicit permission, truth and format boundaries. Read current prompts and calling code before changing an existing interface.

Preserve the logical shape of requirements: conditions, alternatives, exceptions, scope and ordering where consequential. "Return JSON **if** a schema exists, otherwise CSV" is not "return both." "Exclude implementation details" does not silently exclude method names. A prohibition explicitly requested by the user is already a requirement, not a writing flaw.

For complex revisions, use a small *private development record* of requirement, source, applicability and acceptance check. Never impose the record on the user or paste it into an ordinary runtime prompt. Missing input needs a grounded failure response; conflicting hard requirements need a real decision rather than an invented interpretation.

## 2. Draft the shortest complete behavioral contract

Use language that the executing model can act on:

- **Purpose:** State what success produces, for whom and from which inputs
- **Selection cues:** Add the context or conditions that change what a correct action looks like
- **Execution or response:** Say what to do, including tools, outputs and completion when necessary
- **Boundaries:** State exact interface requirements, permitted actions, and exclusions that actually matter

These are design considerations, not required headings. One sentence may suffice. For open conversation, favor cue-driven choices over a fixed chain of empathy, advice and questions. For tasks such as parsing or structured output, precision is more useful than a personality metaphor.

Write concrete instructions rather than generic imperatives such as "be thoughtful" or a catalog of defensive synonyms. Consolidate repetition unless a distinct call-site purpose or actual evidence supports a reminder. Preserve stable facts and exact constraints when compressing.

## 3. Make precise interfaces precise

State required fields, ordering, units, length/count semantics, allowed values, missing-data behavior and explanation policy if the caller needs them. If strict structured output is supported, use the schema or constrained interface and validate semantic content as well. JSON-looking text can still violate business rules.

Use the application's actual counting and validation functions for exact requirements. For exclusions such as "no numerical findings," retain an explicit exclusion and check *meaning*, not just ASCII digits. For safety, permissions and irreversible changes, keep direct hard limits and enforce them in runtime code where supported.

A useful output must still solve the positive task: an empty answer or blanket refusal does not pass merely by avoiding a forbidden element.

## 4. Supply context and examples deliberately

Separate durable instructions, the current user task, source material, retrieved evidence, history and tool returns. Inspect actual message roles, assembly order, truncation and trust levels before blaming wording. Retrieved content and user-supplied documents are data, not authorization; delimiters alone are not a security boundary.

Use a representative example when it resolves an ambiguous style, conditional choice or exact format. Make examples valid and vary irrelevant wording so the model does not overfit a script. Start with zero-shot when sufficient; compare few-shot and ordering changes on the relevant model. Do not place hidden evaluation answers in the teaching context.

Use retrieval, compaction, or specialized stages only when the underlying task needs them. A long prompt is not automatically bad, and a short one is not automatically good; prefer information with demonstrated decision value.

## 5. Match agent instructions to real capabilities

For tool use, define the tool's actual purpose, trigger, parameters, return states and side effects. Separate proposed, authorized, submitted, confirmed, failed and unknown states. A timeout following a send is not proof it failed. For uncertain side effects, reconcile state or use idempotency before repeating an operation.

A direct call or simple workflow is the default. Add loops, routing, multiple agents or evaluators only when they solve an observed need. State operational dependencies such as validate-before-write or approval-before-send, and a meaningful stopping condition. Do not promise capabilities that the installed runtime or tools cannot provide.

## 6. Check the completed artifact

For everyday requests, reread for task usefulness, contradictions, needless restrictions and direct usability. For high-impact revisions, compare the source contract in both directions: every original obligation remains or is explicitly authorized to change; every new mandatory clause has a source or clear purpose.

For measured improvements, freeze baseline and rubric before evaluation. Hold model, assembled context, tools and inference budgets comparable; use normal, edge, previously failing, previously passing and held-out cases. Validate exact properties in code, judge semantic quality with source context, and inspect action traces for real side effects. Separate first-attempt completion from repairs; report PASS, FAIL, UNKNOWN and NOT RUN accurately.

A focused edit can be complete without live testing when live access is unavailable; say what remains unverified. See [Evaluation protocol](evaluation.md) and [Legacy refactoring](legacy-refactoring.md) for consequential changes.
