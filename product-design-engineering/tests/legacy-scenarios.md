# Retained Web regression probes

Development cases migrated from the former design-engineering Skill, not executed results

## Routing probes

| ID | Prompt and available context | Expected result |
| --- | --- | --- |
| R1 | “这个表单层级不清楚，按钮也没有反馈，帮我改好。” A Web form and local preview are available. | Activate; inspect and improve the scoped UI, then verify. Do not stop after a readiness message or plan. |
| R2 | “只审查这个页面的动效和键盘体验，不要修改文件。” A component diff is available. | Activate; report supported findings without source edits or installation. |
| R3 | “数据库查询太慢，优化索引，不改 UI。” Backend-only context. | Do not implicitly activate this Skill; leave the work to the relevant implementation workflow. |
| R4 | “把现有网站发布出去，界面不用改。” Hosting workflow is available. | Do not substitute UI redesign for publishing; this Skill adds no deployment authority. |
| R5 | “给 UI 生成一张插画，不用写界面代码。” Image-generation workflow is available. | Route to image generation without a UI-code audit. |
| R6 | “计算这个数据集的留存率，暂时不制作界面。” Analytics workflow is available. | Route to data analysis, not design polish; do not alter metric definitions. |

## Behavioral probes

| ID | Explicit task and fixture | Expected result and evidence |
| --- | --- | --- |
| B1 | `$product-design-engineering` Improve spacing and hierarchy in a branded, information-dense dashboard with existing tokens. | Reuse the brand and tokens; preserve content, metric meaning, and useful density. No unsolicited glass theme, chart-number animation, or new motion library. Inspect the diff and before/after views. |
| B2 | `$product-design-engineering` Add responsive feedback to a submit button with asynchronous success/error handling. | Feedback begins on press; activation and submission semantics stay intact. No mutation on pointer-down, duplicate request, fake success, or loss of keyboard activation. Exercise cancellation and failure. |
| B3 | `$product-design-engineering` Fix a drawer whose delayed closing callback hides it after it has reopened. | Repeated open/close and reversal keep the latest state. Old callbacks cannot overwrite it; focus and hidden-state semantics remain correct. Test with normal and reduced motion. |
| B4 | `$product-design-engineering` Review a documented 350 ms layout expansion and a working reversible CSS transition. | Duration/property alone is not reported as a confirmed defect. Inspect actual behavior and context; distinguish a measured problem from a performance risk. No automatic CSS-to-library migration. |
| B5 | `$product-design-engineering` Fix a drag handle that jumps on a second touch or pointer cancellation. | Active pointer and grab offset remain stable; cancellation and lost capture are handled. Scrolling/zoom outside the gesture and a non-gesture alternative remain available. Real-device checks are reported separately from emulation. |
| B6 | `$product-design-engineering` Add reduced-motion support to a transform-positioned popover and gesture-driven sheet. | Final positioning, visibility, focus, and interaction are preserved. No blanket transform reset; zero-duration/cancellation paths do not depend on transition-end. Check CSS and JS-driven effects. |
| B7 | `$product-design-engineering` Polish a Chinese form at narrow width, with long labels and enlarged text. | No Latin-only tracking prescription, clipped labels, hidden essential overflow, zoom disabling, or obscured focused input. Inspect narrow and enlarged-text states. |
| B8 | `$product-design-engineering` Improve a page with no Figma plugin, no companion Skills, and no browser access. | Work from available code/context without inventing tools or requiring dependencies. Make useful scoped changes; browser/device checks are `NOT RUN`, not fabricated passes. |
| B9 | `$product-design-engineering` Review only a component already satisfying the brief and established design tradeoffs. | A clean review is allowed. No manufactured issues, forced Before/After table, arbitrary animation quota, or file changes. |
| B10 | `$product-design-engineering` Make an intentionally expressive onboarding illustration more playful while leaving an adjacent command palette fast. | Respect the explicit expressive scope without applying it to frequent utility interactions. Retain reduced-motion/skip behavior and immediate palette input. |
| B11 | `$product-design-engineering` Change a shared button used in a dialog, toolbar, and form. | Inspect representative consumers and preserve labels, focus, disabled/pending states, and activation semantics. Report exactly which checks ran. |
| B12 | `$product-design-engineering` “只给修复计划，不实施。” A failing modal and its source are available. | Produce scoped corrections and verification steps without source edits, installs, commits, or an unsolicited plans directory. |

## Recording results

A useful record contains the case ID, fixture commit, invocation type, loaded Skill, actual diff/tool trace, relevant rendered evidence, result, and unresolved limits. For performance claims, attach the measured workload and trace; for target-runtime quality claims, include baseline/candidate outcomes with the same settings and budget

Re-run affected probes after changes to scope, routing metadata, timing guidance, gesture semantics, or review behavior. Keep static package validation, Codex behavior, and browser/device validation as separate result categories
