# Product and UX decisions

Use for a new capability, an unclear product request, or a change to a user journey. Work from the brief and available evidence; an existing product can need discovery just as a new one can

## Frame the smallest useful outcome

- Describe who is trying to do what, in which situation, and what currently prevents completion. Identify existing workarounds and the trigger for using the product; distinguish an observed need from a proposed solution
- Consider emotional or social needs when supported by the context, without inventing a persona or the user's feelings. Label an untested product assumption and identify the smallest observation that could challenge it
- Compare retaining the current behavior, simplifying it, and adding a capability when the choice is consequential. Prefer a complete end-to-end task over many disconnected features
- Weigh impact, evidence confidence, effort, dependency, and reversibility. Use a scoring framework only when its inputs help decide; missing numbers remain unknown
- Define success in terms of task outcomes and relevant guardrails, such as successful completion without duplicate effects or recovery without lost input. Use observed baselines when available; a build request does not authorize new analytics collection

## Walk through the journey

| Moment | Questions that change the design |
| --- | --- |
| Entry | Can the intended user discover the action and tell whether it is available? Does a permission or prerequisite explain what to do next? |
| Orientation | Are location, object identity, current state, and the next action clear? Do labels match the user's vocabulary? |
| Action | Are defaults safe and useful? Is essential information visible when needed? Are intermediate choices meaningful rather than just fewer clicks? |
| Feedback | Can the user distinguish working, saved, failed, and stale information? Is completion backed by the actual operation? |
| Recovery | Does failure preserve valid input and explain a usable next step? Can the user cancel, retry, or undo when the product supports it? |
| Return | What survives navigation, refresh, interruption, or another session? Is back navigation predictable and unsaved work handled deliberately? |

Inspect new, experienced, interrupted, and error-recovery use where relevant. Reduce unnecessary recall and decisions without hiding critical conditions, pricing, permissions, or destructive consequences. Expert walkthroughs produce findings or hypotheses; they do not establish actual abandonment rates

## Decisions that need explicit acceptance

For a feature, describe the normal task and the affected failure/recovery paths. State observable results rather than adjectives such as “intuitive” or “premium”

For example, a save action may need to show the server-confirmed state, explain a failed request without losing edits, and prevent a repeated press from producing duplicate records. Whether it uses optimistic feedback, blocks a second action, or queues intent depends on the existing data contract and user task

For visual decisions, connect reading order or action to a concrete change and compare at the same content and viewport. For unresolved consequential assumptions, propose the smallest useful user test or evidence check

A useful feature handoff can fit in a few sentences: user task, recommended scope, journey and affected states, consequential tradeoff, acceptance evidence, and remaining uncertainty. Reuse existing project documentation when persistence is needed
