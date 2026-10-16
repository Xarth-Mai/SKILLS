---
name: grill-me
description: Interview the user relentlessly to expand context and surface intent, constraints, hidden assumptions, and unstated alternatives. Use automatically whenever Codex is in Plan mode. Also use when the user invokes `/grill-me`, says "grill me", "interview me", "pressure-test this", "help me think through", or when the user's first message is more decision than task — across coding, business, marketing, personal branding, SOPs, systems thinking, process design, and tough decisions.
---
# grill-me

Expand the user's understanding of what they want through focused, persistent questioning. Surface intent, constraints, hidden assumptions, and alternatives until the next concrete action is clear

## Plan mode

When Codex is in Plan mode, activate this skill automatically. Investigate the project first, then resolve consequential gaps in the goal, constraints, tradeoffs, and completion criteria before presenting an executable plan. Use Plan mode's structured user-input mechanism when available

## Core loop

1. Ask a small batch of consequential questions about the same decision branch, within the active input tool's limits. Use one focused question when its answer determines the next branch; omit questions already resolved by the user or available evidence
2. Number the questions and provide a **concise recommended answer** alongside each one, so the user can accept, reject, or edit it
3. **Follow the most consequential answer** until the decision is clear, then move to the next relevant branch
4. Resolve questions about code, files, and the project through direct inspection
5. End when the goal, constraints, important tradeoffs, and completion criteria support the next concrete action. Deliver the executable plan in Plan mode, or continue within the current authorization

## Question quality

- Advance each exchange with a question that resolves a material uncertainty
- Turn vague answers such as "probably X" into a concrete choice, assumption, or condition
- Point out contradictions and evasions respectfully, and ask what would resolve them
- Adapt to the domain, project evidence, and the user's latest answer

## Question lenses to draw from

Choose and combine lenses as the conversation develops. Use their substance in natural questions

- **First principles:** "Starting from zero, what would make this approach worth choosing?"
- **Intent and desired outcome:** What does success mean to the user personally?
- **Constraints:** Which limits on time, money, energy, values, or identity shape the decision?
- **Hidden assumptions:** "You said X — what has to be true for X to hold?"
- **Alternatives:** What is the strongest other path, and why prefer this one?
- **Pre-mortem:** "It's 12 months from now and this failed. Walk me through why"
- **Opposing case:** What is the strongest case against the plan?
- **Audience / stakeholders:** Name a specific person this serves. What do they think, fear, and want?
- **Reversibility:** What would it take to undo the decision?
- **Root cause:** Follow "Why does that matter?" to the underlying value or constraint
- **Scope:** What belongs in this effort, and what belongs elsewhere?
- **Sustainability:** Would the plan still work if it took three times as long?

## Handling half-answers

- For uncertainty, propose a concrete answer the user can revise: "Here's a possible answer — what would you change?"
- When the user challenges the question, reframe it: "What would you need to know to make this answerable?" Follow that thread
