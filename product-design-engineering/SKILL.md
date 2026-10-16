---
name: product-design-engineering
description: "Discover and refine product needs, diagnose unclear UI/UX problems, design coherent interactions and motion, implement user-facing features, and verify experiences across platforms. Use for product journeys, visual hierarchy, cognitive load, content clarity, interaction behavior, design engineering, and experience reviews. Recognize established problem patterns and reuse solutions that fit project constraints. Adapt effort to the task; not for backend-only work, deployment alone, or image/data tasks without experience design."
---

# Product Design Engineering

Turn product intent into a coherent, useful, expressive, technically sound experience. Identify consequential gaps, make deliberate decisions, implement within scope, and verify what users encounter. Ground design in product identity, project conventions, platform behavior, and evidence

## Scope and operating mode

- Select the needed phases: **Frame** (problem, user, scope), **Audit** (diagnose), **Design** (decide and specify), **Build** (implement), **Review** (challenge and verify). Handle local edits directly; cover the relevant journey and states for an end-to-end feature
- For authorized build/polish work, inspect, decide, implement, and verify. Review-only/plan-only work produces findings/a plan **without editing**. Commits, publication, deployment, contacting users, production data changes, and irreversible operations require applicable authorization
- Preserve product choices, brand, content, business/privacy decisions, data semantics, APIs, interfaces, and unrelated work. Surface conflicts and demonstrated problems using current code, revision, rendered state, and the user's latest direction
- Use relevant specialist Skills/tools when available and continue with available capabilities otherwise. Follow the project's established process for complex skill authoring or review
- Investigate material omissions thoroughly; present consequential choices, reasons, checks, and essential risks concisely

## 1. Ground the actual experience

Inspect relevant instructions, specifications, UI/artifacts, tokens, components, navigation, state/data contracts, runtime, dependencies, tests, and surrounding consumers. Scope the investigation to the affected flow

For each material feature or change, connect four lenses:

1. **User goal** — who is doing what, when, and why; what success feels like in this product.
2. **User-facing meaning** — words, hierarchy, defaults, state, pricing/permission consequences the user can understand.
3. **Action path** — entry, prerequisites, main action, feedback, recovery, return; whether the user can discover and complete it.
4. **Engineering truth** — which source of truth, permission, platform behavior and data lifecycle make the experience reliable.

Match screenshots to **their captured version** and verify findings against current code. Distinguish supplied facts, verified implementation, observation, hypothesis, and preference; ground research, metrics, device and model claims in actual evidence

Resolve small, reversible gaps with a reasoned assumption. Ask only when a missing decision materially changes product scope, authorization, correctness, or difficult-to-reverse impact. Load [Product and UX](references/product-ux.md) for new/changed user journeys.

## 2. Diagnose before designing

Translate experience complaints into inspectable candidates. For each consequential finding, use:

`Observation → exact evidence/state → probable root cause (or hypothesis) → user cost → smallest coherent correction → verification`

Select relevant diagnostic questions:

- **Product and journeys:** Is the main user outcome reachable? Does a component solve the user's task, or expose implementation machinery? Do statuses across screens agree? Are payment, consent, deletion and recovery semantics truthful?
- **Information and cognition:** Is the next relevant action discoverable? How much must the user remember, compare, infer or precisely target? Are advanced details available without interrupting ordinary work? Is necessary context lost through over-collapsing?
- **Visual craft:** What catches the eye first, second, third, and should it? Are meaningful groups clear? Do alignment, type, contrast, spacing, density, surfaces, icon optics and navigation chrome form a consistent hierarchy? Does every decoration have a role?
- **Interaction and motion:** Do actions acknowledge immediately, transition from the current state, survive repeated intent and interruptions, and remain operable without decorative motion?
- **Engineering and access:** Can target-platform users read, touch, navigate, edit, recover and trust what they see under real data, keyboard, accessibility preferences, slow networks and lifecycle transitions?

Rank findings by user impact, scope, confidence, and reversibility. Label style preferences as preferences; report a clean audit when the evidence supports it

For nontrivial changes, connect symptoms and evidence to candidate **problem families**. Test each hypothesis against existing mechanisms, contracts, prerequisites, and counterexamples. Consider standard-library, platform, official framework guidance, or established solutions; choose the smallest fit for the task's data, security, and runtime constraints, with an observable check

Research unfamiliar or consequential details as needed and distinguish inspected sources from remembered practice. Explain a concrete mismatch before choosing a local alternative to an established solution

Load [Problem families and prior art](references/problem-families-and-prior-art.md) for unfamiliar, cross-cutting or recurring product-experience problems. Its engineering examples support the user-facing task within this Skill's existing scope

For diagnosis involving complexity or nontechnical audiences read [Cognitive ergonomics](references/cognitive-ergonomics.md); for aesthetics and layout read [Visual](references/visual.md) and [Experience craft](references/experience-craft.md).

## 3. Make a specific design decision

Recommend a coherent solution matched to the product and context. Explain consequential alternatives and tradeoffs; choose rules and values for a concrete purpose

### Prevent avoidable experience defects before building

For a meaningful screen or interaction change, settle the relevant decisions before writing UI code or finalizing a mockup; a narrow edit follows existing conventions without a design workshop

- **Necessity before wording:** decide what to remove, show, simplify or move to contextual detail based on the user's decision, action and trust needs; preserve explicit content requirements and material consequences
- **User meaning:** express the user's situation, outcome and next step while retaining the precision needed for expert tasks, pricing, permissions and truthful states; use [Cognitive ergonomics](references/cognitive-ergonomics.md)
- **Optical composition:** plan grouping, density, type metrics, glyph mass, baselines and hit areas at intended display sizes through the shared component; use [Experience craft](references/experience-craft.md)
- **Event semantics:** distinguish first appearance, return, explicit refresh, passive update, confirmed change and interruption; choose replay and persistent-surface continuity deliberately, including reduced motion; use [Motion](references/motion.md)
- **Density after subtraction:** recompose the task area and spacing around the remaining content and actions

Include these decisions in the existing design contract when needed; Review verifies that they survived implementation

Treat correctness, applicable accessibility, responsive operability, and explicit product/brand constraints as requirements. Use reference scales, presets, and visual treatments selectively within project conventions. Load relevant guidance before implementation:

| Concern | Reference |
| --- | --- |
| Scope, journeys, navigation, recovery, acceptance | [Product and UX](references/product-ux.md) |
| Cognitive load, progressive disclosure, decision/action costs, content | [Cognitive ergonomics](references/cognitive-ergonomics.md) |
| Visual hierarchy, typography, content, data displays | [Visual](references/visual.md) |
| Optical alignment, purposeful surfaces, visual diagnosis and design review | [Experience craft](references/experience-craft.md) |
| Easing, springs, gestures, retargeting, chart animation | [Motion](references/motion.md) |
| State, controls, accessibility, async behavior, performance | [Engineering](references/engineering.md) |
| Chat, streaming, composer coordination, tool approval and agent activity | [Agent UI](references/agent-ui.md), only for relevant conversation or agent-product tasks |
| Web/native/mini-app evidence and realistic validation boundaries | [Platform evidence](references/platform-evidence.md) |
| Risk-based functional, adverse-content and interaction verification | [Verification](references/verification.md) |

For larger changes, record a compact decision contract: **user task; candidate problem family and solution where relevant; affected screens/states; information and visual hierarchy; copy and feedback; implementation constraints; acceptance evidence.** Choose values using project conventions and platform behavior

## 4. Build the working experience

Reuse project components, tokens, accessibility primitives, and installed dependencies. Inspect shared consumers before changing shared styles or semantics. Label prototypes clearly; build requests connect actual actions and data

For a recurring gap in a *shared* convention, update or propose the smallest consistent rule at its authoritative home, align shared implementation and regression checks, and reconcile conflicting instructions within authorization. Keep isolated fixes local

Preserve source-of-truth data, errors, revision/transaction semantics, and user edits. Implement affected loading, empty, populated, failed, stale, repeated-action, cancelled, interrupted, and return states. Tie user-facing success to the underlying operation's confirmed outcome

Use the actual platform API and input model. Consult [Platform evidence](references/platform-evidence.md) for cross-runtime adaptation and check new libraries/APIs against the installed version

Use motion when it serves state change, direct manipulation, or comprehension. Decide entry versus update, timing, orchestration, interruption/reversal, reduced-motion behavior, and data truthfulness using [Motion](references/motion.md)

## 5. Review with independent counterexamples

After design or implementation, challenge the solution with relevant counterexamples:

- **User:** Can a novice recognize the main action without internal terms? Can an expert still reach advanced controls? What happens on the next visit, not only the first?
- **Visual:** Can a realistic populated screen be scanned in the intended order? What happens with long Chinese copy, many records, sparse data, bad contrast, large text and narrow widths? Are visual affordances and actual hit areas both sufficient?
- **Behavior:** If the user leaves, reverses, taps rapidly, saves during a refresh, or an API fails, does the newest intended and server-confirmed state win?
- **System:** Did the change alter financial, privacy, accessibility, data or security semantics, or break other screens sharing a component?
- **Prior art and coherence, for nontrivial changes:** Did we recognize the established problem family, inspect available proven solutions and their conditions, and avoid reinventing or misapplying one? If this is a recurring project rule, is the authoritative design/engineering specification consistent with the implementation and tests?

For substantial UI changes, verify the earlier necessity, composition and event-semantics decisions; repair a failed decision or shared implementation at its owner rather than accumulating cosmetic overrides

Propose the smallest correction for a reproduced defect. For new or significant flows, use [Verification](references/verification.md) and targeted [design diagnosis probes](tests/design-diagnosis-probes.md)

## 6. Verify what you claim

Run focused existing tests and inspect rendered output where tools permit. Use representative content and actual component constraints. Compare at the **same content, device size, theme and state**; use target-runtime/device checks for native, desktop, and mini-app interaction claims

Record each check as **PASS / FAIL / BLOCKED / NOT RUN**, identifying its evidence layer: static inspection, automated test, browser render, emulator, physical device, model/tool trace, or user task observation. Mark unavailable acceptance layers explicitly. Live-data changes and paid/external actions require applicable authorization

Deliver the artifact/patch/findings first, with key decisions, material checks, and unresolved risks. Stop when the authorized goal and relevant checks are satisfied

## Maintenance

When improving this Skill from real failures, locate the cause: **knowledge, discovery/routing, reasoning, execution/platform, or verification**. Change the relevant layer, add a similar but different regression scenario, and preserve passing cases and untouched holdouts. Evaluate behavioral improvement through comparative runs

Keep product-specific taste in its project and promote generalizable principles during authorized maintenance. Global memory and other Skill edits require their own authorization

For provenance and licensing, consult [Source map](references/source-map.md) and [Research addendum](references/research-addendum.md); for evaluation, use [Scenarios](tests/scenarios.md), [Design diagnosis probes](tests/design-diagnosis-probes.md), [Pattern reuse probes](tests/pattern-reuse-probes.md), [Preventable defects probes](tests/preventable-defects-probes.md), [Agent UI probes](tests/agent-ui-probes.md), and the existing [validation record](tests/validation.md). These are maintenance resources, not required reads for every ordinary task
