# Cognitive ergonomics and usable decisions

Use when users face dense settings, jargon, unclear next steps, repeated navigation, overwhelming choices, long explanations, or interfaces that feel technically complete but exhausting to use. This is general experience guidance, not a claim about ADHD or a diagnosis of any user.

## Attention, memory and action are separate costs

For the main task, inspect:

- **Discovery cost:** Can users recognize the relevant control and whether it is available without searching every group?
- **Interpretation cost:** Do labels, units, choices and system statuses use the audience's language? Does the user have to translate implementation terms?
- **Memory cost:** Must the user remember a step, value, error, selection, relationship, or previous screen to finish the current step?
- **Decision cost:** Which choices change outcomes, and which are unneeded configuration presented prematurely?
- **Interaction cost:** Number and precision of taps/clicks, backtracks, context switches, keyboard reentry and waiting without useful feedback.
- **Recovery cost:** After interruption or failure, can they safely resume without losing input or reconstructing state?

Do not optimize an arbitrary tap count at the expense of clarity, trust or safety. A meaningful confirmation for deletion or charges is desirable friction.

## Content necessity before microcopy

Within the user’s explicit content and interaction requirements, choose the least burdensome truthful presentation before polishing wording:

- **Remove:** the detail has no meaningful effect on the intended user's next decision, trust or recovery, and remains available where legitimately needed (for example, in detailed accounting rather than beside a balance)
- **Show directly:** the action is short, safe and usually wanted; an expandable wrapper adds an unnecessary step and creates empty surface area when closed
- **Simplify:** the information is necessary but expressed in implementation language; replace it with the user's action, outcome and consequence
- **Move to context:** diagnostics, model parameters, advanced configuration or accounting precision matter to a subset of users; make them discoverable without interrupting routine work
- **Keep explicit:** material prices, real restrictions, permission changes, irreversible actions, confirmed versus pending states and recovery guidance. A clean screenshot is not permission to conceal them

After removing copy or controls, revisit page hierarchy and density. Do not invent filler to occupy the gap; also do not over-collapse useful action areas merely to create blank space. Compare novice and expert tasks before deciding a disclosure is unnecessary

## Decision sequence

1. State the user's immediate question in ordinary language: "Can I start?", "What will this cost?", "Did it save?", "What do I do now?"
2. Identify the smallest information and action needed **at that moment**. Place those in the natural scanning order.
3. Move optional expertise, long explanations and diagnostic data to contextual details, secondary pages or explicit disclosure. Preserve discoverability and an accurate summary; do not bury consequences.
4. Ensure the screen communicates **where I am, what is true now, what I can do, what happens next**. A saved setting may still be pending effect; show that distinction.
5. Check the experience for a newcomer and a returning/expert user. A default-simple interface still needs efficient expert access.

Use progressive disclosure to respect task sequence, not to indiscriminately hide entire screens. If a collapsed item conceals a fee, privacy change, error, irreversible consequence, or currently selected value, expose enough context before the consequential action.

## Density and list design

Information density is not just item count. Ten well-grouped high-value items can be easier to use than three vague rows. Evaluate repeated headers, microtext, card borders, timestamps, decorative icons and technical metadata as sources of visual noise.

Use aggregation when the user first wants a total or trend; provide drill-down when they want an audit trail. Do not aggregate unlike statuses into a misleading total. For payments, separate **estimated usage**, **final charge**, **pending amount**, and **account balance**; preserve exact ledger access and accounting precision even if the overview is rounded for readability.

For large collections, choose the least costly mechanism that serves the task: group by date or meaning, collapse zero-value repetition, paginate/load more, filter or search when the user actually needs it. A numeric cap on visible items is a tuning hypothesis, not a law. Check the empty, one-item, many-item, and unusual-item cases.

## Content and microcopy

- Prefer **outcome language** for default tasks: describe what happens when pressed, rather than naming a Provider, Token, session identifier or backend file. Keep exact technical terms inside genuinely advanced interfaces or when they are necessary to act safely.
- Keep labels short enough to scan but complete enough to disambiguate. A vague "Manage" is not automatically better than a specific "Manage chat model".
- Pair expressive brand language with literal instructions. Brand tone is welcome for welcome screens and storytelling; errors, pricing, identity, permissions and deletion must remain unmistakably factual.
- Lead with the result of an operation, then the next useful action. Do not announce success before the backend confirms it, or disguise a failure in poetic language.
- Distinguish "saved", "available in the next session", "still checking", "failed" and "last confirmed". Avoid transferring internal workflow steps to the user unless genuinely required; explain required user actions in situ.
- Format information so scanning is easy: meaningful headings, close association of label/value, one clear emphasized action for a task, secondary navigation that looks clickable, and accessible expanded detail.

## Emotional and conversational products

An efficient **management interface** need not dictate the companion's **conversation style**. Natural conversation can include digression, delight, silence, humor, and open-ended sharing; it is not a progress tracker. Do not require every conversational reply to summarize, give an action or end with a question.

Avoid manipulative urgency or emotional claims tied to money, engagement statistics, relationships or reminders. Do not present an AI's inferred feelings or generated history as observed facts. Let users control persistent records and understand what deleting one representation does to other data sources.

## Anti-patterns

- Hiding essential charges/controls to obtain a clean screenshot
- Renaming technical concepts to warm but meaningless phrases
- Making tiny standalone text links the only path to a key action
- Turning every page into a wizard, a single oversized card, or a mandatory call to action
- Requiring a numeric limit on paragraphs, choices, list rows, or taps without regard to task
- Presenting every optional detail simultaneously "for transparency"
- Forcing concise/task-oriented assistant habits onto chat companionship

## Practical diagnostic probe

Ask: *Without prior context, can a real intended user tell what this screen does, what is currently true, and what happens after the next tap?* If the answer seems uncertain, identify the exact copy, grouping, state, or control responsible and propose an observable correction. A reviewer prediction is a hypothesis until tested with users.
