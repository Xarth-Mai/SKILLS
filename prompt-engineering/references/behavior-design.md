# Behavior design: guide decisions, not just forbid mistakes

Read when writing or improving prompts that must shape flexible behavior, tone, personality, or decisions. Educational ideas such as modeling, scaffolding and formative feedback are **design analogies**, not evidence that an LLM learns like a person. Measure effects on the target model.

## Define the behavior worth producing

Start with the useful outcome, then describe only the cues and choices that make it achievable:

- **Purpose:** What should this model accomplish for the user?
- **Situation:** Which inputs, intentions, relationships or tool states should change its response?
- **Judgment:** What matters when choosing among valid responses?
- **Action:** What should it actually say or do, including a successful stopping point?
- **Boundary:** What must remain true for accuracy, safety, permissions or an exact interface?

These are authoring questions, **not** a five-step script to paste into every prompt. A short task may need one sentence. A strict protocol may need precise fields and exclusions rather than a personality-like description.

## Use a situational mechanism when behavior is flexible

Give the model a reason to choose, not a mandatory gesture for every turn. A conversation companion may attend to a joke, complaint, request or goodbye differently; interest or concern may lead to a response, a question, useful help or a natural ending. Personality can influence what seems salient and how the character expresses it.

Weak: "Never sound like customer support. Never ask unnecessary questions. Never over-explain."

Stronger: "Respond as a familiar friend to the part of the message that matters most. Share a genuine reaction or perspective; ask when you're curious or missing information needed to help. When the thought is complete, let the exchange rest."

The stronger instruction identifies purpose, cues, choices and a stopping condition. It is not a guarantee of superior performance; test it against real dialogue, including cases where a question is necessary.

Keep the character's perspective distinct from factual claims about the world, actual user history and completed tool actions. Imagination and roleplay can be expressive; assertions about real actions and shared memories need evidence.

## Distinguish guidance from hard boundaries

Translate vague defensive wording into desired behavior when doing so preserves intent:

- "Don't be careless" → "Check the supplied facts and address the specific request"
- "Don't keep asking questions" → "Ask for a decision or missing fact when it affects the next action; otherwise finish naturally"
- "Don't be verbose" → "Cover the necessary information at the detail the task warrants"

Keep direct exclusions when the exclusion **is** the contract: prohibited content, exact format, privacy, security, authorization, irreversible side effects, or a caller's parser rules. A negative instruction is not automatically a defect. Do not replace "send only after approval" with vague warmth or initiative.

## Teach by showing, selectively

Add a short representative input/output example when a requirement is hard to infer from prose, especially nuanced style, boundary cases or exact formats. Contrast a brittle response with a better one only if the distinction teaches a decision criterion. Vary irrelevant details to avoid accidental templates.

Examples are evidence of *intended behavior*, not proof of model compliance. Never embed evaluation holdouts as few-shot examples. Keep examples truthful, within permissions, and consistent with the surrounding requirements. See [Authoring examples](examples.md).

## Scaffold only where needed

For simple tasks, deliver one directly usable instruction. For complex work, add only the supporting context, decomposition, reference material, tools and checks that the task needs. Put specialized procedures in separately loaded references or runtime tools, not every user's prompt.

Avoid imposing a fixed workflow on flexible conversation or adding a planning phase where a direct answer suffices. Preserve real action dependencies: confirm authorization, validate before mutation, reconcile uncertain side effects, and stop on confirmed completion.

## Improve through observable feedback

When behavior is poor, examine the actual assembled prompt, context, tool schema, model settings and output/trace. Locate the first relevant wrong choice. A repeated trailing question may arise from an example, previous conversation, missing stop cue, or model tendency; another prohibition may not fix it.

Change the smallest causal element, preserve established good behavior, and test the new version on matched cases plus unseen cases. Inspect unnecessary questions **and** required clarifications; task completion **and** concise presentation; persona expression **and** factual integrity. Report untested effects as unverified.

The aim is fewer *unhelpful instructions*, not fewer instructions at any cost.
