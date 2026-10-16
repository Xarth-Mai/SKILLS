# Preventable experience defects — paired evaluation probes

Full implementation probes: **NOT RUN**. Limited design-only derivatives were executed; see the [validation record](validation.md). The cases below remain evaluation specifications, not implementation results. Do not send this file (which contains evaluator expectations) to the worker being evaluated. Create separate clean fixtures for each baseline/candidate run; use identical model, tools, target code, time budget, authorization, and evaluator

## Worker task inputs (one at a time)

| ID | User-facing task to send to worker |
| --- | --- |
| F1 | 这是积分余额页面，帮我做成简洁好用的正式产品页面，功能逻辑不要变 |
| F2 | 面向普通人的设置首页，做一版清楚好懂的文案和操作布局，保留高级配置能力 |
| F3 | 把账户页的数字余额、积分单位、状态图标和按钮排好，要求在小屏上看着协调 |
| F4 | 现有积分页面把兑换码表单折叠起来了，帮我减少用户操作和空白，展开方式可以调整 |
| F5 | 连接从“待确认”转成“已连接”，做出流畅成功动画；原有状态与配色保留 |
| F6 | 页面首次加载、返回、切 Tab、下拉刷新都有计数动效，帮我整理成自然的体验 |
| F7 | 品牌插画是正方形的，想用于很小的小程序入口和圆形头像，直接设计落地方案 |
| F8 | 完善一个需要用户确认支付金额及自动续费条款的支付页面，尽量清爽 |
| F9 | 现有 UI 对齐正确、文案清楚，只调整指定按钮颜色，别动其他 |
| F10 | 手机端原生下拉刷新后，页面从顶部闪一下，帮我诊断和修复，保留原生手势 |
| F11 | 设计一个专业开发者 API Key 配置页，让开发者完成必要设置和错误排查 |
| F12 | 某个状态指示器视觉元素消失后又出现，帮我把中间空白帧消掉，保证可访问性 |

## Fixture construction requirements

Fixtures are **not included**. Create disposable examples representative of the target project and authorize either design-only or build explicitly. Vary target platform (Web, WeChat mini-app), theme, text length and realistic state data. For F1 include a ledger with fractional carry-forward but no change to authoritative accounting; for F4 include an actual short safe inline redemption path; for F5/F12 include component unmount/remount and background replacement; for F6 include an actual render lifecycle and explicit refresh event. F8 requires legally or operationally material information; F9 deliberately has no general product issue. Verify the user brief does not explicitly require the supposedly redundant content

## Evaluator-only expectations

| ID | Evidence of useful *initial* decisions | Failure signal |
| --- | --- | --- |
| F1 | Determines whether sub-unit settlement explanation is needed in overview; may remove overview-only noise but preserves full ledger truth and shortage feedback; rebalances content density | Merely rewrites every caption; hides accounting or changes billed values |
| F2 | Retains needed controls; default language describes user goals; exact technical names remain where legitimately needed | Replaces every technical noun with vague poetic labels or removes expert access |
| F3 | Plans baseline/glyph/number-unit optical relationships before choosing CSS; checks actual rendered size and varying labels | Claims flex centering guarantees optical alignment; adds arbitrary per-page offsets |
| F4 | Challenges unnecessary collapsible wrapper; chooses direct exposure where safe, balances density and tests typical flow | Always keeps accordion for feature richness, or removes it without considering screen size |
| F5 | Stable shared circular surface; crossfade/reveal only internal state, no transient blank or false success; interruption/reduced-motion valid | Unmounts old icon/background before replacement exists, flashes empty canvas |
| F6 | Explicit animation contract for first appearance, return, passive data update, user refresh and completion; no unintentional replay on return | Replays on every `onShow` or disables animation globally |
| F7 | Tests actual 24–48px and round crop, permits simplified small-size mark rather than downscaling rich art; brand consistent | Only generates full-res complex logo and assumes downscale succeeds |
| F8 | Keeps material price, consent and renewal consequences before commitment; unnecessary decoration removed | Hides material charges under “clean UI” rationale |
| F9 | Narrow scoped edit, no unsolicited visual redesign, relevant check only | Adds a lengthy UX rework or modifies unrelated screens |
| F10 | Checks actual `scroll-view`/native refresh mechanics and top bounce; maintains gesture, no false platform claims | Globally disables rebound without considering native refresh or claims verified on device without device test |
| F11 | Preserves precise API Key/Provider/error identifiers required by expert users; improves grouping without hiding diagnostics | Unconditionally translates/removes technical terms needed to complete the task |
| F12 | Keeps persistent surface continuous, handles interruptions and stable final frame, verifies real states and reduced motion | Solves by increasing animation duration while leaving a blank transition frame |

## How to compare

1. Capture baseline Skill revision and candidate revision, fixture commit, model, platform, authorizations, tools, evaluation budget
2. Give the worker **only** the individual user task and its fixture, not this rubric or expected outcome. For routing tests, do not force-invoke a Skill; for controlled skill-quality comparison, explicitly invoke the chosen version
3. Compare decisions **before implementation** when the task warrants it, then actual code/UI results and tests. Beware post-hoc rationalization in reports
4. Judge with one common evaluator and actual render or device evidence when available. Treat `NOT RUN`, `BLOCKED` and `FAIL` separately
5. Retain passing cases and use untouched holdouts. Do not infer general improvement from one positive run, a linter, or a Markdown diff

An initial design that avoids a problem is better than one that introduces it and later detects it in Review. This evaluation is meant to measure that difference
