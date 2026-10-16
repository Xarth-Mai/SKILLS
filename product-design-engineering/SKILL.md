---
name: product-design-engineering
description: "Discover and refine product needs, diagnose unclear UI/UX problems, design coherent interactions and motion, implement user-facing features, and verify experiences across platforms. Use for product journeys, visual hierarchy, cognitive load, content clarity, interaction behavior, design engineering, and experience reviews. Recognize established problem patterns and reuse solutions that fit project constraints. Adapt effort to the task; not for backend-only work, deployment alone, or image/data tasks without experience design."
---

# Product Design Engineering

Turn product intent into a coherent, useful, expressive, technically sound experience. Detect consequential issues that the requester cannot yet name, make deliberate decisions, implement within scope, and verify what a user would actually encounter.

Do **not** substitute a bigger checklist, a visual trend, or a polished report for a good result. Product identity, project conventions, actual platform behavior, and evidence take precedence over aesthetic defaults. This Skill neither imposes a style nor requires companion Skills.

## Scope and operating mode

- Infer the needed phases: **Frame** (problem, user, scope), **Audit** (diagnose), **Design** (decide and specify), **Build** (implement), **Review** (challenge and verify). Combine only what the task needs. A label correction needs no discovery workshop; an end-to-end feature needs the relevant journey and states.
- For an authorized build/polish request, inspect, decide, implement, and verify. For review-only/plan-only requests, produce findings/a plan **without editing**. Do not infer permission to commit, publish, deploy, contact users, change production data, or perform irreversible operations.
- Preserve explicit product choices, brand, content, business and privacy decisions, data semantics, APIs, existing interfaces, and unrelated work. Surface conflicting requirements or demonstrated problems rather than silently replacing the brief. Do not repeat a completed fix merely because an old screenshot or review mentioned it. Confirm present code, revision, rendered state, and the user's most recent direction.
- Consult specialist Skills/tools selectively when already available. Their absence is not a blocker. For complex skill authoring or reviews, use the project's established authoring/review process; this Skill does not replace it.
- Separate **exhaustive professional consideration** from **concise user-facing choices**. Investigate enough to find material omissions; present the few changes that matter, their reasons and checks. Do not hide essential risks or requirements merely to keep visible lists short.

## 1. Ground the actual experience

Inspect the relevant project instructions, specifications, existing UI or artifacts, design tokens, components, navigation, state/data contracts, runtime, installed dependencies, and relevant tests. Inspect enough surrounding consumers to understand the flow; avoid a repository-wide excursion for a local fix.

For each material feature or change, connect four lenses:

1. **User goal** — who is doing what, when, and why; what success feels like in this product.
2. **User-facing meaning** — words, hierarchy, defaults, state, pricing/permission consequences the user can understand.
3. **Action path** — entry, prerequisites, main action, feedback, recovery, return; whether the user can discover and complete it.
4. **Engineering truth** — which source of truth, permission, platform behavior and data lifecycle make the experience reliable.

Treat prior screenshots as evidence about **their captured version**, not automatic findings against newer code. Distinguish supplied facts, verified implementation, observation, hypothesis, and preference. Do not invent user research, metrics, live-device outcomes, or model behavior.

Resolve small, reversible gaps with a reasoned assumption. Ask only when a missing decision materially changes product scope, authorization, correctness, or difficult-to-reverse impact. Load [Product and UX](references/product-ux.md) for new/changed user journeys.

## 2. Diagnose before designing

Convert "busy", "empty", "unpolished", "hard to tap", "not natural", or "something feels wrong" into inspectable candidates, not instant advice. For each consequential finding, use:

`Observation → exact evidence/state → probable root cause (or hypothesis) → user cost → smallest coherent correction → verification`

Use appropriate depth across these **questions**, rather than mechanically checking every category:

- **Product and journeys:** Is the main user outcome reachable? Does a component solve the user's task, or expose implementation machinery? Do statuses across screens agree? Are payment, consent, deletion and recovery semantics truthful?
- **Information and cognition:** Is the next relevant action discoverable? How much must the user remember, compare, infer or precisely target? Are advanced details available without interrupting ordinary work? Is necessary context lost through over-collapsing?
- **Visual craft:** What catches the eye first, second, third, and should it? Are meaningful groups clear? Do alignment, type, contrast, spacing, density, surfaces, icon optics and navigation chrome form a consistent hierarchy? Does every decoration have a role?
- **Interaction and motion:** Do actions acknowledge immediately, transition from the current state, survive repeated intent and interruptions, and remain operable without decorative motion?
- **Engineering and access:** Can target-platform users read, touch, navigate, edit, recover and trust what they see under real data, keyboard, accessibility preferences, slow networks and lifecycle transitions?

Rank issues by actual user impact, scope, confidence, and reversibility; avoid fabricated severity scores or polishing inconsequential inconsistencies. A clean audit is valid. Do not call subjective styling a proven usability defect.

For a nontrivial change, connect the observed symptom and evidence to candidate **problem families** before choosing a fix. A named pattern is a hypothesis, not proof: inspect existing project mechanisms and contracts, then consider applicable standard-library, platform, official framework guidance or established solutions. Check prerequisites, counterexamples, data consistency, security and runtime constraints relevant to the task; choose the smallest fitting implementation and an observable verification

Keep this proportional: a simple scoped edit follows the existing local convention directly. Research unfamiliar or consequential details as needed; distinguish inspected sources from remembered practice and do not claim checks that were not run. If no established solution fits, explain the concrete mismatch and design locally

Load [Problem families and prior art](references/problem-families-and-prior-art.md) for unfamiliar, cross-cutting or recurring product-experience problems. Its engineering examples support the user-facing task within this Skill's existing scope

For diagnosis involving complexity or nontechnical audiences read [Cognitive ergonomics](references/cognitive-ergonomics.md); for aesthetics and layout read [Visual](references/visual.md) and [Experience craft](references/experience-craft.md).

## 3. Make a specific design decision

Recommend a solution matched to this product and context. For significant alternatives, explain what changes and the tradeoff; otherwise choose one coherent direction. A rule or number must serve a concrete purpose, not appear because a framework recommends it.

Choose the relevant guidance before implementation:

| Concern | Reference |
| --- | --- |
| Scope, journeys, navigation, recovery, acceptance | [Product and UX](references/product-ux.md) |
| Cognitive load, progressive disclosure, decision/action costs, content | [Cognitive ergonomics](references/cognitive-ergonomics.md) |
| Visual hierarchy, typography, content, data displays | [Visual](references/visual.md) |
| Optical alignment, purposeful surfaces, visual diagnosis and design review | [Experience craft](references/experience-craft.md) |
| Easing, springs, gestures, retargeting, chart animation | [Motion](references/motion.md) |
| State, controls, accessibility, async behavior, performance | [Engineering](references/engineering.md) |
| Web/native/mini-app evidence and realistic validation boundaries | [Platform evidence](references/platform-evidence.md) |
| Risk-based functional, adverse-content and interaction verification | [Verification](references/verification.md) |

For larger changes, produce a compact decision contract: **user task; identified problem family and candidate established solution (if applicable); affected screens and state transitions; chosen information and visual hierarchy; necessary copy and feedback; consequential implementation constraints; acceptance evidence.** Avoid universal pixel, timing, border, or list-length prescriptions. Use the platform's actual idioms. When a plausible mature pattern is rejected, record the concrete mismatch instead of silently reinventing it

## 4. Build the experience, not the screenshot

Reuse the project's components, tokens, accessibility primitives and installed dependencies. Inspect shared consumers before modifying shared styles or semantics. If a design is limited to prototypes, label it as such; when asked to build, wire the actual actions and data instead of decorative mock controls.

If repeated defects reveal a missing *shared* product convention, close the loop as part of the authorized scope: identify its authoritative home; update or propose the smallest consistent rule, shared implementation, and regression check; reconcile contradictory older instructions. Do not create a new global component or document for an isolated fix, and do not silently edit product policy or unrelated pages

Preserve source-of-truth data, errors, revision/transaction semantics and user edits. Implement affected loading, empty, populated, failed, stale, repeated-action, cancelled, interrupted and return states **where relevant**. User-facing success requires evidence of the underlying operation; animation completion does not equal persistence.

Apply the *actual* platform API and input model. Do not carry Web pointer events, DOM assumptions, hover, CSS capabilities, or Apple-native behavior unexamined into mini-apps, mobile or desktop. Consult [Platform evidence](references/platform-evidence.md) when adapting a design across runtimes. Test any new library or API against the installed version.

Motion serves state change, direct manipulation or comprehension. If not helpful, omit it. If helpful, decide entry versus update, duration/easing or spring, orchestration, interruption/reversal, reduced-motion path and truthfulness of data. Consult [Motion](references/motion.md).

## 5. Review with independent counterexamples

After design or implementation, **switch from proposing to finding faults**. Challenge the solution from these perspectives:

- **User:** Can a novice recognize the main action without internal terms? Can an expert still reach advanced controls? What happens on the next visit, not only the first?
- **Visual:** Can a realistic populated screen be scanned in the intended order? What happens with long Chinese copy, many records, sparse data, bad contrast, large text and narrow widths? Are visual affordances and actual hit areas both sufficient?
- **Behavior:** If the user leaves, reverses, taps rapidly, saves during a refresh, or an API fails, does the newest intended and server-confirmed state win?
- **System:** Did the change alter financial, privacy, accessibility, data or security semantics, or break other screens sharing a component?
- **Prior art and coherence, for nontrivial changes:** Did we recognize the established problem family, inspect available proven solutions and their conditions, and avoid reinventing or misapplying one? If this is a recurring project rule, is the authoritative design/engineering specification consistent with the implementation and tests?

Do not rubber-stamp the original plan; propose the smallest correction for a reproduced defect. Do not invent issues to populate a report. For new or significant flows, use [Verification](references/verification.md) and targeted [design diagnosis probes](tests/design-diagnosis-probes.md).

## 6. Verify what you claim

Run focused existing tests and inspect actual rendered output where tools permit. Use representative content and real component constraints. Compare before/after at the **same content, device size, theme and state**. Prefer target runtime/device evidence for native, desktop and mini-app experiences; a browser mock does not prove native touch, system bars, scroll, keyboard, screen reader or animation timing.

Record evidence as **PASS / FAIL / BLOCKED / NOT RUN** with the specific check. Static code inspection, automated unit tests, browser render, platform emulator, physical device, real model/tool trace and human task test are **different** levels of evidence. Missing device access is a meaningful open check, not a license to claim pixel-perfect or finished UX. Do not alter live user data or execute paid/external actions without authorization.

Deliver the requested artifact/patch/findings first, with the key decision, material checks and unresolved risks. Prefer decisions and observable results over a wall of principles. Stop once the authorized goal and relevant checks are satisfied.

## Maintenance

When explicitly improving this Skill, convert real failures into reusable rules only after identifying the stage at which they occurred: **knowledge gap, discovery/routing failure, reasoning failure, execution/platform gap, or verification gap**. Change the narrowest relevant layer, add a similar but different regression scenario, and preserve positive behavior and untouched holdouts. Do not conclude a Skill improvement from static lint alone.

Keep product-specific taste in its project; promote only generalizable principles. Do not automatically write global memory or rewrite other Skills during normal application work.

For provenance and licensing, consult [Source map](references/source-map.md) and [Research addendum](references/research-addendum.md); for evaluation, use [Scenarios](tests/scenarios.md), [Design diagnosis probes](tests/design-diagnosis-probes.md), [Pattern reuse probes](tests/pattern-reuse-probes.md), and the existing [validation record](tests/validation.md). These are maintenance resources, not required reads for every ordinary task
