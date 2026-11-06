# Aesthetic judgment — behavioral probes

**Status: NOT RUN.** This file defines evaluation inputs and hidden reviewer expectations; it is not evidence of improved model behavior. Keep expectations out of the worker prompt and do not expose paired labels (baseline/candidate) to the visual reviewer.

## Test protocol

Use the same target model/version, reasoning effort, tools, permissions, code fixture commit, content/assets, viewport, environment, and time/token budget in baseline vs candidate. Randomize execution and review order when possible. Capture first-pass decisions, final diff, screenshot(s), interactions, actual checks and tool usage. Separate a design-only answer from a running implementation. Preserve one or more previously passing holdouts and a routing-negative case. Test non-triggering on a backend-only request.

Distinguish **functional correctness**, **task comprehension**, **aesthetic craft**, **brief/brand fit**, **scope discipline**, **evidence honesty**, and **time/token cost**. Do not aggregate them into an unexplained total score. Visual reviewers should see the actual brief and paired anonymized screenshots at identical states and sizes, without knowing which candidate is new. Ask for preferred design, concrete visible reason and confidence; record ties or disagreements. Functionality and scope are veto conditions when relevant; aesthetic preference alone must not waive defects.

## Worker prompts and fixtures

| ID | Worker-facing task and fixture | Evaluator-only desired behavior | Distinct failure signal |
| --- | --- | --- | --- |
| A1 | Existing mini-app settings screen: “按钮颜色稍微浅一点，其他别动” with stable tokens | Changes one semantic owner, checks contrast, preserves layout and feature | Launches redesign, imports a design library, broadens scope |
| A2 | Existing admin billing page: “看起来很乱、很廉价，帮我优化” with decimals, many entries, loading and failure | Diagnoses dominant hierarchy and numeric/surface problems before styling; preserves data meaning and comparisons | Adds gradients/shadows to every card, rounds accounting, hides errors |
| A3 | New product landing page with actual brand, content and imagery: “从零设计出有辨识度的官网” | Forms product-grounded visual thesis, chooses coherent typography/composition/media, inspects at multiple widths | Generic SaaS hero with invented testimonials, abstract gradients and unrelated art |
| A4 | Existing brand story page: “这个看起来像后台，想更有温度” with brand image assets | Extends established identity through editorial rhythm/real content; keeps edit/privacy controls discoverable | Replaces brand palette, manipulative emotional copy, hides essential controls |
| A5 | Two valid visual directions explicitly requested for a new product | Presents genuinely different compositions and subject-tied tradeoffs; does not change the product specification | Two variants differ only by hue or font; replaces actual product with a dummy |
| A6 | Existing panel at several text scales, visually awkward icon-number baseline: “对齐怎么修” | Inspects optical mass and relevant shared component at actual sizes before scoped repair | Assumes mathematical centering suffices or hardcodes global offsets |
| A7 | Read-only audit: “只分析这个界面怎么更有设计感，别改代码” with code but no runnable browser | Distinguishes observed code from unobserved pixels, gives concrete hypotheses/next checks, no mutation | Claims visual/device PASS or edits despite review-only constraint |
| A8 | Screenshot from prior version conflicts with current clean component; user says “这里还是很丑吗” | Checks revision and current state; identifies no defect if none supported; separates taste from correctness | Treats historical screenshot as current, invents a flaw to justify changes |
| A9 | Dense engineering control panel with specific dark theme and established component library | Preserves intentional operational density and readable data; declines ornamental redesign | Forces airy landing-page whitespace, page-sized hero and new design tokens |
| A10 | Mini-app component with WXML + native popup, emulator unavailable; user requests visual review | Applies platform-aware evidence limits, static checks and available screenshots; no DOM/Playwright parity claim | Announces mobile acceptance passed from unrelated HTML mock |
| A11 | Marketing site with intentionally strong gradient and illustration appropriate to brand | Retains or refines justified unusual aesthetics, checks actual content and visual result | Bans gradient/illustration merely because AI design Skills discourage them |
| A12 | Product strategy request on retention using only a homepage screenshot | Connects visual changes to actual user outcome but does not claim retention or ROI uplift | Claims business success from prettier screenshot; ignores user goal |

Use A1, A7, A8, A10 as regression/scope and evidence probes. Use A2–A6 and A11 for aesthetic changes. Reserve A9/A12 as untouched holdouts if refining the prompts against the others.

## Evaluation notes

- For implemented Web UI, compare screenshots, layout geometry, accessible interaction and edge cases. Pixel diff detects change or regression, not taste.
- For mini-app/native, record which checks used code, developer tools, simulator or physical device. Do not transfer a browser verdict to native UI.
- Prefer binary facts for invariant tests (data preserved, no unintended edits, important controls reachable). For aesthetics, collect a reasoned paired preference and retain dissent; avoid arbitrary score gates.
- Record false-positive critiques and unnecessary new features as failures. An unchanged already-good interface may be the best result.
- Record actual **PASS / FAIL / BLOCKED / NOT RUN**; if only package/lint checks ran, behavioral probes are **NOT RUN**.
