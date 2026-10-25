# Evaluation scenarios

These cases define checks, not evidence that they passed. Keep expected outcomes out of the agent's task input. Use disposable copies of the same fixture for each variant and record model/settings, available tools, exact prompt, file hashes, actions, artifacts, and results

## Contract

| ID | Requirement and origin | Observable check |
| --- | --- | --- |
| C1 | User brief: one portable product-to-engineering Skill | Completes the requested product task without requiring sibling Skills or prescribing a global theme |
| C2 | ZIP and legacy: respect action mode and existing choices | Audit/plan leaves application files unchanged; build produces a scoped artifact; existing brand/data semantics remain |
| C3 | ZIP and legacy: proportionate action | Small changes do not trigger a discovery workshop, dependencies, or unrelated redesign |
| C4 | ZIP and legacy: complete interactions | Pending/error, repeated actions, latest intent, focus, and interruption work where affected |
| C5 | Legacy: Web accessibility and content resilience | Keyboard activation, usable reduced motion, long/localized text, and focus survive the change |
| C6 | User brief and existing review policy: evidence before claims | Actual artifacts and checks support conclusions; unavailable browser/device/user checks are explicit |
| C7 | User brief: source-backed independent synthesis | Source paths/revisions and licenses are inspectable; inherited notices remain; upstream scripts/processes are not required |
| C8 | Confirmed migration choice | New package is independent, old entrypoint is removed, README and Codex discovery use the new name |

## Core probes

| ID | Task and fixture | Acceptance |
| --- | --- | --- |
| E1 | “这个面板看着很乱，检查代码，先不要修改” with a page and known brand tokens | Evidence-grounded locations and impact, no invented visual observation, no file changes or forced restyle |
| E2 | “把设置页的‘确定’改成‘保存’，其他不动” with a native form | Only scoped label change, activation semantics retained, proportionate check |
| E3 | “给现有列表加收藏，直接落地” with an asynchronous persistence API and injectable errors | User can save/unsave, failed writes leave truthful state, repeated presses obey a deliberate policy, no fake success, useful checks |
| E4 | “侧栏关闭后马上重开会又消失，修好并支持减少动效” with deferred close completion | Latest open state wins, zero-duration path completes, final geometry and focus remain usable |
| E5 | “修好窄屏中文长标题和放大文字的布局，保留现有风格” | Content/actions remain reachable; no page-wide clipping or zoom disabling; actual rendering claims have evidence |
| E6 | “浏览器不可用，审查这段弹层代码是否可交付，先不要改” | Useful static findings, no mutation, no fabricated runtime/accessibility pass, no complete refusal merely for missing browser |
| E7 | “给这个柱状图增加加载和更新动效” with positive/negative/missing values and interrupted updates | Truthful values and identity, distinct entrance/update behavior, reduced-motion path; no prescribed shared-progress algorithm for all cases |
| E8 | “给原生桌面工具设计首次使用流程，只给方案” with platform and audience constraints | Portable product reasoning, platform-specific unknowns explicit, no forced Web APIs, no implementation |

Exercise E2–E5 independently for attribution, or as a combined repair task when measuring whole-task completion; report which protocol ran. Keep unexecuted cases `NOT RUN`. The inherited [Web regression probes](legacy-scenarios.md) cover additional gestures, scope boundaries, and intentional design exceptions

## Discovery probes

Without explicit invocation, test a product scope request, an interface repair and a product activation/retention decision as positive cases, and backend indexing, publishing-only, standalone image generation, and calculation-only/data-cleaning requests without a product decision or experience design as negative cases. Distinguish the host listing the Skill from the model actually choosing it

## Comparison and stopping

Compare the supplied ZIP baseline with the candidate under the same prompts, fixture, model configuration, tools, and allowance. Record unknown settings instead of claiming they were controlled. A first pass and a repair pass are separate results; do not report the best retry as first-attempt success

Judge task completion and all applicable requirements from diffs, executed checks, and output evidence. Avoid scoring by matching preferred wording. Include a known failing and a known passing fixture to check any deterministic evaluator. Keep development cases separate from untouched holdouts

If execution is unavailable, complete static/package review and report behavioral tests as blocked or not run. A small paired sample supports a limited observation, not a general adherence or design-quality improvement claim
