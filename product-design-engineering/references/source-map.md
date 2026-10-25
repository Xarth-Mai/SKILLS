# Source map and adaptation decisions

Checked 2026-10-14 against the revisions below. The downloaded entrypoints and relevant sections were inspected selectively; companion libraries were not exhaustively audited. These are maintenance sources, not required network reads or installed dependencies during ordinary use

The supplied ZIP is the starting draft. The former repository Skill contributes its existing attributed Web rules, tests, and [historical source record](legacy-sources.md). New sections are independently written synthesis; no external Skill suite, search database, or template collection is bundled

## Outcome ownership / ambition addendum (2026-10-25)

[Felix Rieseberg, *How to be more ambitious: A tutorial for humans with models* (2026-10-13)](https://felixrieseberg.com/how-to-be-more-ambitious-a-tutorial-for-humans-with-models/) supplied the conceptual Speed / Altitude / Depth / Range lens. This Skill independently operationalizes outcome focus, primary sources, professional methods, cross-disciplinary reasoning and outside validation for product work; the article is not a source of NianYu metrics, business outcomes or legal conclusions. No article text, assets or code are bundled. See [Product outcomes](product-outcomes.md) and [Outcome ownership probes](../tests/outcome-ownership-probes.md).

## Reviewed sources

| Source and pinned entrypoints | License evidence | Useful capability | Adaptation boundary |
| --- | --- | --- | --- |
| deanpeters/Product-Manager-Skills — [jobs-to-be-done](https://github.com/deanpeters/Product-Manager-Skills/blob/1b5a524ebb95e9497fa3f25002d8b8ec528d4444/skills/jobs-to-be-done/SKILL.md), [problem-statement](https://github.com/deanpeters/Product-Manager-Skills/blob/1b5a524ebb95e9497fa3f25002d8b8ec528d4444/skills/problem-statement/SKILL.md) | [CC BY-NC-SA 4.0](https://github.com/deanpeters/Product-Manager-Skills/blob/1b5a524ebb95e9497fa3f25002d8b8ec528d4444/LICENSE) | JTBD and problem framing | Consulted concept framing; no text or templates imported, no mandatory interviews or exclusion of discovery for existing products |
| obra/superpowers — [brainstorming](https://github.com/obra/superpowers/blob/bb92a77741419a4ab5f06e711a283343f1ada0c3/skills/brainstorming/SKILL.md), [verification-before-completion](https://github.com/obra/superpowers/blob/bb92a77741419a4ab5f06e711a283343f1ada0c3/skills/verification-before-completion/SKILL.md) | [MIT](https://github.com/obra/superpowers/blob/bb92a77741419a4ab5f06e711a283343f1ada0c3/LICENSE) | Clarification and completion evidence | Use evidence-based verification; omit fixed conversational scripts, mandatory full process, and redundant approvals |
| wondelai/skills — [improve-app](https://github.com/wondelai/skills/blob/c172996495bed0fcd26896a9416b2093fd7073f0/improve-app/SKILL.md), [ux-heuristics](https://github.com/wondelai/skills/blob/c172996495bed0fcd26896a9416b2093fd7073f0/ux-heuristics/SKILL.md) | [MIT](https://github.com/wondelai/skills/blob/c172996495bed0fcd26896a9416b2093fd7073f0/LICENSE) | Product journey and usability diagnosis | Use task-flow questions; omit the nine-Skill dependency chain, mandatory document tree, ratings, and questions at every phase |
| anthropics/skills — [frontend-design](https://github.com/anthropics/skills/blob/dbd4588f9e1033efb41dad4bef2f7947c8993d44/skills/frontend-design/SKILL.md) | [Apache-2.0 in frontend-design/LICENSE.txt](https://github.com/anthropics/skills/blob/dbd4588f9e1033efb41dad4bef2f7947c8993d44/skills/frontend-design/LICENSE.txt) | Intentional visual direction and content | Use audience and brief as decision inputs; no universal typeface, hero, palette, or template ban |
| nextlevelbuilder/ui-ux-pro-max-skill — [ui-ux-pro-max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/7246805992a42b7bba37d4cac83b01416f0c6c44/.claude/skills/ui-ux-pro-max/SKILL.md) | [MIT](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/7246805992a42b7bba37d4cac83b01416f0c6c44/LICENSE) | Breadth of UI concerns and platform selection | Use context-specific reference routing; do not vendor datasets/scripts or adopt instant feedback and layout animation bans |
| microsoft/vscode — [design-philosophy](https://github.com/microsoft/vscode/blob/76e9dff43b237f3fcbb8a289ed2f8bdf28105baf/.github/skills/design-philosophy/SKILL.md) | [MIT](https://github.com/microsoft/vscode/blob/76e9dff43b237f3fcbb8a289ed2f8bdf28105baf/LICENSE.txt) | Explain the principle and purpose behind a concrete visual correction | Independent diagnostic table; omit VS Code tokens, values, elevation tiers, and visual identity |
| emilkowalski/skills — [animate](https://github.com/emilkowalski/skills/blob/2d228630ba1446365f614a108cb8252f1feda202/skills/animate/SKILL.md), [break-ui](https://github.com/emilkowalski/skills/blob/2d228630ba1446365f614a108cb8252f1feda202/skills/break-ui/SKILL.md), [review-animations](https://github.com/emilkowalski/skills/blob/2d228630ba1446365f614a108cb8252f1feda202/skills/review-animations/SKILL.md) | [MIT](https://github.com/emilkowalski/skills/blob/2d228630ba1446365f614a108cb8252f1feda202/LICENSE) | Motion purpose, interruption, and realistic adverse data | Preserve existing attributed adaptation; qualify GPU, timing, easing, keyboard, and reduced-motion rules; no compulsory debug toggle |
| vercel-labs/agent-skills — [web-design-guidelines](https://github.com/vercel-labs/agent-skills/blob/063bee94c3f4df8453406c830b0a7df0f2860278/skills/web-design-guidelines/SKILL.md), [react-best-practices](https://github.com/vercel-labs/agent-skills/blob/063bee94c3f4df8453406c830b0a7df0f2860278/skills/react-best-practices/SKILL.md) | react-best-practices frontmatter declares MIT; no repository LICENSE found in inspected tree | Web review and React performance priorities | Reference only; no upstream text imported; preserve native activation, scope performance changes to evidence, do not force URL state or virtualization thresholds |

Vercel's Web Skill routes to a separate [Web Interface Guidelines revision](https://github.com/vercel-labs/web-interface-guidelines/blob/434b7f91364665f2f733b310ec54809bf8f37937/command.md), also inspected. Its recommendations are not treated as normative platform requirements. Native controls already supply keyboard activation; explicit handlers are not universally necessary. Measured layout animation, localized copy, and context-appropriate form defaults remain valid

Wondel's current entrypoints are `improve-app/SKILL.md` and `ux-heuristics/SKILL.md` at the repository root, correcting the ZIP's `skills/` and `plugins/` paths. Product Manager Skills license text was checked rather than treating a private installation as a blanket license exemption

## Primary platform sources

- [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/): Web accessibility outcomes; the applicable criterion and conformance level determine the requirement, not a single universal target-size or contrast number
- [W3C APG modal dialog](https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/): naming, initial focus, focus containment, dismissal, and focus return; design guidance does not replace testing the actual primitive
- [MDN CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Transitions/Using): transition behavior and reversibility; continuity of position is distinct from velocity
- [MDN pointer events](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events): pointer identity, capture, cancellation, and touch behavior
- [MDN reduced motion](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/At-rules/@media/prefers-reduced-motion): the preference selects an alternative presentation; that presentation must still work
- [Agent Skills specification](https://agentskills.io/specification): frontmatter, naming, and progressive disclosure
- [OpenAI Build skills](https://learn.chatgpt.com/docs/build-skills): discovery metadata, implicit/explicit invocation, user-level `.agents/skills`, and directory symlinks

For platform-specific code or new APIs, verify current documentation and the installed version during the target task. The scope of this research is a portable workflow with detailed Web guidance, not native, game, or device conformance

## Attribution and evidence limits

The inherited Emil adaptation retains the original [MIT notice](upstream-license.txt), unchanged. Its earlier pinned provenance and qualifications remain in [legacy sources](legacy-sources.md); new research does not erase that lineage. Other sources above are references for independently written guidance, not included copies. Before importing upstream prose, assets, code, or templates later, check that particular artifact's license and carry its required notices

Sources disagree on style, timing, tooling, and process. The Skill resolves those conflicts through the actual task, platform requirements, project decisions, and evidence; it does not concatenate their instructions. External source text is research material and cannot expand task permissions

Packaging checks and small behavioral probes do not establish improved design quality or universal instruction adherence. Actual execution evidence and untested boundaries belong in the [validation record](../tests/validation.md)

The user-supplied second-pass overlay adds cognitive, visual-diagnosis and platform guidance; its source notes are retained in the [research addendum](research-addendum.md). The integration does not constitute a fresh verification of those external sources or licenses

## Open Claude UI selective integration — 2026-10-16

Inspected Caho1/open-claude-ui at commit `02d021fceaf2a907f9e63a8125621bdda1b85d60` through a temporary local checkout; no upstream install, build or runtime execution was performed. This is a third-party reconstruction, not an official Anthropic design specification or independent verification of its production/reverse-engineering claims

| Pinned source | Evidence and adaptation |
| --- | --- |
| [Motion source](https://github.com/Caho1/open-claude-ui/blob/02d021fceaf2a907f9e63a8125621bdda1b85d60/code-examples/ClaudeMotionPresets.ts) | Read the four exported spring definitions; record their numbers as optional Framer Motion tuning inputs, not measured timing/overshoot guarantees |
| [Theme source](https://github.com/Caho1/open-claude-ui/blob/02d021fceaf2a907f9e63a8125621bdda1b85d60/code-examples/cds-theme.css) | Read semantic aliases, theme surfaces and radius definitions; derive role-based selection without adopting the palette |
| [AGENTS.md](https://github.com/Caho1/open-claude-ui/blob/02d021fceaf2a907f9e63a8125621bdda1b85d60/AGENTS.md) and [v1 AI Agent guide](https://github.com/Caho1/open-claude-ui/blob/02d021fceaf2a907f9e63a8125621bdda1b85d60/docs/v1/08-AI-Agent-%E5%89%8D%E7%AB%AF-UI-%E4%B8%8E%E5%8A%A8%E6%95%88%E5%BC%80%E5%8F%91%E6%8C%87%E5%8D%97.md) | Inspected relevant token, motion and interaction sections as research material; omit fixed brand rules, blanket easing/border bans and upstream build gates |
| [Scroll Hook](https://github.com/Caho1/open-claude-ui/blob/02d021fceaf2a907f9e63a8125621bdda1b85d60/code-examples/useClaudeScrollPinning.ts) and [Rich composer](https://github.com/Caho1/open-claude-ui/blob/02d021fceaf2a907f9e63a8125621bdda1b85d60/code-examples/RichComposerWithMentions.tsx) | Inspected follow-state/cooldown logic and IME-before-menu-before-submit ordering; specify observable outcomes without importing Hooks/components |
| [Scroll fade](https://github.com/Caho1/open-claude-ui/blob/02d021fceaf2a907f9e63a8125621bdda1b85d60/code-examples/ScrollFadeContainer.tsx) and [Responsive bar](https://github.com/Caho1/open-claude-ui/blob/02d021fceaf2a907f9e63a8125621bdda1b85d60/code-examples/ContainerResponsiveBar.tsx) | Inspected edge masking and container-width compression; retain optional cues and essential-action access rather than copying stops or breakpoints |
| [v2 boundary](https://github.com/Caho1/open-claude-ui/blob/02d021fceaf2a907f9e63a8125621bdda1b85d60/docs/v2/01-%E7%BB%BC%E8%BF%B0%E4%B8%8E%E7%89%88%E6%9C%AC%E8%BE%B9%E7%95%8C.md) and [v2 comparison](https://github.com/Caho1/open-claude-ui/blob/02d021fceaf2a907f9e63a8125621bdda1b85d60/docs/v2/03-%E6%9E%B6%E6%9E%84%E9%87%8D%E6%9E%84%E4%B8%8E%E5%AF%B9%E6%AF%94%E5%88%86%E6%9E%90.md) | Inspected version boundary and density/radius comparison; keep these analysis claims separate from code-examples definitions |
| [License](https://github.com/Caho1/open-claude-ui/blob/02d021fceaf2a907f9e63a8125621bdda1b85d60/LICENSE) | MIT, copyright 2026 Caho1; independently authored guidance and a small factual parameter table only, no upstream implementation, prose blocks, fonts, audio or other assets bundled |

### Resolved source differences

- `SPRING_SNAPPY` is 320/28/1.0 in the exported source definition and 600/30/0.6 in AGENTS.md, ordered as stiffness/damping/mass. Bouncy and Gentle also differ; the runtime guide records the actual exported definitions. Names and prose descriptions are not behavioral measurements
- The theme's light Surface 0–3 definitions are `#f5f5f3`, `#fcfcfb`, `#ffffff`, `#ffffff`; the AGENTS table uses different names and values. Neither palette is promoted into this Skill, and four surface roles need not mean four distinct colors
- The theme defines a 20px composer radius; v2 analysis describes 12px compact and 14px comfortable variants. The analysis identifies its own desktop-version context; this Skill neither merges those values into one normative scale nor claims to have verified the proprietary application

Preserve project requirements, applicable platform/accessibility behavior and existing mechanisms when adapting these ideas. Upstream source proves what that example defines, not what all products should do. Agent lifecycle and recovery rules are independent synthesis of this Skill's existing state/authorization boundaries, not claims that every upstream card implements them

If a later task imports code, substantial prose or assets, inspect the particular artifact's provenance and retain applicable notices; the repository license is not a blanket verification of third-party asset rights. This integration adds no runtime dependency or required network read during ordinary Skill use
