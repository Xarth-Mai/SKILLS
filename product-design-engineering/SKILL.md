---
name: product-design-engineering
description: "Discover and refine product needs, design user journeys, build or review UI, and verify user-facing experiences. Use for product scope and acceptance decisions, UX friction, unclear visual hierarchy, interaction or motion problems, and user-facing feature implementation across platforms. Applies only the relevant depth; not for backend-only changes, deployment alone, standalone image generation, or data analysis without experience design."
---

# Product Design Engineering

Turn a product request into a useful, coherent, technically sound experience with inspectable evidence of completion

Discover consequential omissions the user may not know to mention, then resolve them within the requested scope. Product intent, project conventions, actual platform behavior, and observed evidence guide decisions; this Skill defines no universal visual theme or framework

## Scope and working mode

- Infer the mode from the request: **Frame** clarifies the problem and acceptance, **Audit** diagnoses an existing experience, **Design** specifies a solution, **Build** implements it, and **Review** challenges the result. Combine only the phases the task needs
- For an authorized build or polish request, inspect, decide, implement, and verify. For review-only or plan-only requests, return findings or a plan without editing files. This Skill supplies no additional permission to publish, send messages, commit, or change production
- Preserve explicit product choices, brand, content, data semantics, APIs, and unrelated work. Surface conflicting requirements or demonstrated problems with those choices rather than silently replacing the brief
- Use available specialist tools or Skills only where useful. Website tooling can own construction, data tooling can own metric correctness, and coding workflows can own implementation discipline. This Skill works without any companion installed
- Keep effort proportional: a label edit needs a scoped edit and check; a feature needs its journey and affected states; a new product or major flow needs deeper framing. Do not reopen settled decisions or impose a PRD on a small task

## 1. Ground the request

Inspect the relevant project instructions, current interface or supplied artifact, shared components/tokens, data contracts, dependencies, and available tests. Limit the initial inspection to the requested surface and its consumers

Review each material feature through four connected lenses: the user goal, wording the user can understand, the actual action path, and the technical constraints that determine truthful behavior. Resolve mismatches before polishing presentation.

Identify the user, situation, desired outcome, present obstacle, platform/input methods, and constraints. Separate what the user said, what evidence establishes, and what you assume. User interviews, satisfaction, measured performance, and research results must come from actual evidence

For missing details, first check the project. Decide minor reversible choices and state meaningful assumptions briefly. Ask only when the unresolved answer materially changes scope, correctness, authorization, or an expensive decision; offer a concrete recommendation

For new capabilities or journey changes, read [Product and UX](references/product-ux.md). For a local UI repair, continue with the relevant design reference without a discovery workshop

## 2. Diagnose before prescribing

Connect a complaint or opportunity to a concrete location and affected user task. Use this compact reasoning record for material issues, not as a mandatory table for every edit:

`Observation → evidence/location → cause or hypothesis → user impact → smallest useful change → check`

Distinguish broken behavior, accessibility barriers, comprehension problems, visual inconsistency, measured performance issues, aesthetic preference, and product disagreement. Prioritize consequences and reach with available evidence; do not invent frequencies or precision to produce a score

A screenshot can support visual observations, code can support implementation findings, and interaction traces can support runtime behavior. None alone proves user preference or full experiential quality. A clean review is valid; do not manufacture defects or an animation quota

## 3. Make and implement the decision

Choose one recommended solution that completes the user task. Explain consequential tradeoffs and alternatives only when they help decide. Make it clear why a rule or parameter fits this case, not merely that a source recommends it

Load the references needed for the affected work before deciding or implementing:

| Concern | Reference |
| --- | --- |
| Product scope, task flow, navigation, recovery, acceptance | [Product and UX](references/product-ux.md) |
| Visual diagnosis, layout, typography, content, data presentation | [Visual](references/visual.md) |
| Animation, gestures, interruption, reduced motion, chart transitions | [Motion](references/motion.md) |
| Interactive controls, accessibility, asynchronous state, shared components, performance | [Engineering](references/engineering.md) |
| Feature/flow acceptance, adverse data, runtime and visual evidence | [Verification](references/verification.md) |

Reuse the project's architecture, tokens, accessible primitives, and installed libraries. Inspect shared consumers before changing a common component. Check version-specific APIs when needed. Implement real data flow and affected loading, empty, success, failure, repeated-action, and interrupted states, rather than a happy-path screenshot

Apply platform conventions to the actual runtime. Web-specific APIs in the references are Web guidance; for native, desktop, mini-app, CLI, or game work, inspect the corresponding platform contracts and evidence needs. Keep general principles without pretending a Web check validates another platform

## 4. Verify, repair, and report

Run narrow checks that exercise the changed behavior and required project checks. For visual or interaction changes, inspect a local rendered result when available, using matching before/after content and relevant states. Fix observed regressions and recheck affected behavior; broaden testing only for an unresolved risk

Use realistic adverse data and interruption scenarios from [Verification](references/verification.md) for feature-level work. Live business systems, external mutations, and real-device acceptance follow the user's authorization and project requirements, not a blanket Skill mandate

If a browser, device, tool, or input is unavailable, complete the useful work that remains and name the evidence gap. Report actual checks and results, using `PASS`, `FAIL`, `BLOCKED`, or `NOT RUN` where a matrix helps. Static checks are not rendered UI acceptance; screenshots are not motion or usability tests

Deliver the requested artifact, patch, findings, or plan first, with the important decision and evidence. For an audit, give actionable locations, impact, and corrections. For a design, give the intended flow, relevant states, and acceptance criteria. For a build, report what changed, checks, and material gaps. Keep small tasks small

## Maintenance

When explicitly asked to improve this Skill from experience, record the case, observed failure, evidence, applicability, proposed rule, and a similar but different regression case. Retain project-specific preferences in the project; promote a general rule only with supported scope. Do not automatically edit global instructions or memory during ordinary product work

For source verification or rule maintenance, read [Source map](references/source-map.md). For Skill evaluation, use [Scenarios](tests/scenarios.md) and the [migration and evidence record](tests/validation.md). These are maintenance resources, not required reading on every product task
