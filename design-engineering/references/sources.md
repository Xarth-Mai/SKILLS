# Sources and adaptation notes

## Scope and provenance

This is a curated adaptation for `Xarth-Mai/SKILLS`, not an official Apple or Emil Kowalski distribution. The entrypoint combines selected design-engineering ideas into one implementation-and-review Skill; it is not a mirror of the upstream bundle.

Reviewed on 2026-09-27. Primary upstream: [emilkowalski/skills](https://github.com/emilkowalski/skills), commit [`d16ebe60d09a5ba2afcb7054ede9d0a10c9f6128`](https://github.com/emilkowalski/skills/commit/d16ebe60d09a5ba2afcb7054ede9d0a10c9f6128). The selection below is deliberately limited to the six entrypoints discussed for this task; it is not a claim that the current upstream has only six Skills.

The six linked `SKILL.md` entrypoints were read for this adaptation. Their additional upstream reference files were not imported, and this package does not require the upstream repository at runtime.

## Selection map

| Upstream entrypoint | Retained in this Skill | Adaptation or omission |
| --- | --- | --- |
| [apple-design](https://github.com/emilkowalski/skills/blob/d16ebe60d09a5ba2afcb7054ede9d0a10c9f6128/skills/apple-design/SKILL.md) | Immediate feedback, direct manipulation, interruption, velocity handoff, spatial continuity, typography, preference fallbacks | Principles remain brand-neutral. Glass, blur, Apple physics constants, and a particular visual style are not defaults. Press feedback is separated from action commitment. |
| [emil-design-eng](https://github.com/emilkowalski/skills/blob/d16ebe60d09a5ba2afcb7054ede9d0a10c9f6128/skills/emil-design-eng/SKILL.md) | Purpose/frequency judgments, coherent component states, trigger-aware surfaces, motion tuning, testing the rendered result | Reuse the project's tokens and stack. Numeric ranges are starting points, not universal rules. Omit prescribed opening messages and mandatory Before/After tables. |
| [review-animations](https://github.com/emilkowalski/skills/blob/d16ebe60d09a5ba2afcb7054ede9d0a10c9f6128/skills/review-animations/SKILL.md) | Evidence at a concrete location, interruption and accessibility checks, impact-ordered fixes | Review the evidence rather than defaulting to a defect. Accessibility is part of correctness, not the last polish tier. No mandatory verdict, issue quota, or aesthetic score. |
| [improve-animations](https://github.com/emilkowalski/skills/blob/d16ebe60d09a5ba2afcb7054ede9d0a10c9f6128/skills/improve-animations/SKILL.md) | Inspect stack and shared tokens, verify candidates, scope fixes and acceptance checks | Merge into one small working loop. The current request selects implement/review/plan behavior; no forced subagent fan-out, `plans/` tree, or repeated approval cycle. |
| [find-animation-opportunities](https://github.com/emilkowalski/skills/blob/d16ebe60d09a5ba2afcb7054ede9d0a10c9f6128/skills/find-animation-opportunities/SKILL.md) | Filter motion by purpose, frequency, speed, and interference with the task | Integrate as a decision gate. No quota for added effects, no automatic stagger, and no replacement of established destructive-action safeguards with a hold gesture. |
| [animation-vocabulary](https://github.com/emilkowalski/skills/blob/d16ebe60d09a5ba2afcb7054ede9d0a10c9f6128/skills/animation-vocabulary/SKILL.md) | Useful implementation terms: origin, interruption, spring, momentum, crossfade, reduced motion | Use terms where they clarify a decision; omit a separate glossary Skill and the requirement to reproduce definitions verbatim. |

## Deliberate qualifications

These changes reconcile upstream heuristics with a general-purpose Web/Codex workflow; they are local design decisions, not quotations from Apple:

- **CSS transitions and interruption:** upstream text includes both broad warnings about CSS interruption and examples recommending retargetable CSS transitions. Use CSS transitions for simple reversible state changes; use an appropriate gesture/spring implementation for velocity continuity. Do not claim that all CSS animation restarts from zero.
- **Rendering performance:** prefer transform/opacity, but do not promise GPU execution from a property name, API, or library shorthand alone. Real layout changes can justify measured layout animation. Broad blur prescriptions and unconditional `will-change` are omitted.
- **Timing, easing, and keyboard input:** keep frequent actions immediate. Do not turn a particular daily-use count, a 300 ms boundary, custom easing, or an input device into an unconditional rule. Keyboard feedback remains available. The larger-surface 200–350 ms range is a local starting heuristic, not a platform requirement.
- **Gesture math:** preserve direction and units, use recent velocity samples, handle cancellation, and verify the installed library's handoff. Do not copy an unsigned whole-gesture average or unlabelled velocity threshold into production.
- **Accessibility and lifecycle:** retain focus, semantics, usable final geometry, and a non-gesture path when motion is removed. A global transform reset or an opacity-only hidden state can break the interface.
- **Design identity:** visual hierarchy, readable type, predictable controls, and useful feedback take precedence over imitating Apple surfaces. Typography choices are checked against actual fonts and scripts rather than universally tightening headings.
- **Scope:** one Skill complements existing website-building, lightweight coding, and dashboard workflows. It does not change publishing permissions, require Figma, or install an animation library simply to fulfill its own instructions.

## Platform and implementation references

These primary references were consulted to check platform behavior and packaging. They are maintenance links, not required browsing on every invocation. Browser support and library APIs still need checking for the target project.

- [Apple — Designing Fluid Interfaces, WWDC18](https://developer.apple.com/videos/play/wwdc2018/803/): immediate response, redirection, gesture tracking, and the distinction between highlighting on touch-down and committing on touch-up.
- [MDN — Using CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Transitions/Using): property transitions, timing, and browser behavior.
- [MDN — Using the Web Animations API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API/Using_the_Web_Animations_API): programmatic animation control and lifecycle.
- [MDN — Pointer events](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events): pointer identity, capture, cancellation, and touch-action.
- [MDN — Animation performance and frame rate](https://developer.mozilla.org/en-US/docs/Web/Performance/Guides/Animation_performance_and_frame_rate): rendering work and the cost of animated properties.
- [MDN — prefers-reduced-motion](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/At-rules/@media/prefers-reduced-motion): adapting effects to a user preference.
- [W3C — WCAG 2.2](https://www.w3.org/TR/WCAG22/): accessibility criteria, including input alternatives, focus, contrast, target size, and moving content.
- [W3C APG — Modal dialog pattern](https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/): focus, keyboard interaction, modal behavior, and naming.
- [OpenAI — Build skills](https://developers.openai.com/codex/skills): `SKILL.md`, progressive disclosure, local discovery, optional `agents/openai.yaml`, and explicit/implicit invocation.

## Attribution and license notice

Selected material was adapted from the MIT-licensed upstream. Its [original license](https://github.com/emilkowalski/skills/blob/d16ebe60d09a5ba2afcb7054ede9d0a10c9f6128/LICENSE), including `Copyright (c) 2026 Emil Kowalski`, is preserved verbatim in [upstream-license.txt](upstream-license.txt) so that the notice accompanies an independently installed Skill directory. The repository's existing root `LICENSE` is unchanged.

This curation has not been shown by a target-runtime comparison to improve model output quality. [Validation scenarios](validation.md) describe how to test routing and behavior; static packaging checks are a separate result.
