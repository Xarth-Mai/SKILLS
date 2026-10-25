# Product Design Engineering

从用户价值和产品方向、UX、UI 和动效，到工程实现、审查与验收的跨项目 Skill，替代本仓库原 `design-engineering`

主入口选择任务所需的 Frame、Audit、Design、Build、Review 阶段；专业参考按需加载，保留项目自身的品牌、技术栈与平台约定，跨平台核心之外提供较深入的 Web 指导

非平凡体验问题先从症状和证据识别候选问题类型，检查项目已有机制与成熟方案的适用条件，再做最小实现和验证；简单局部修改直接沿用既有约定

## 使用

- “用 `$product-design-engineering` 给现有产品加收藏功能，直接落地并验证失败与重复点击”
- “用 `$product-design-engineering` 检查这个页面为什么显得杂乱，先不要修改”
- “用 `$product-design-engineering` 设计这个流程，说明重要取舍和验收标准”

支持自动选择，也可以显式调用；不依赖其他 Skill、Figma 或特定 UI 框架。缺少浏览器或设备时仍可进行有依据的代码检查，并如实标记未完成的验收

## 本地安装

在支持用户级 `.agents/skills` 的 Codex 中，将此目录放入 `~/.agents/skills/product-design-engineering`，或建立指向仓库中此目录的软链接。官方支持目录软链接，仓库更新可以直接反映到安装内容，见 [Build skills](https://learn.chatgpt.com/docs/build-skills)

安装前检查同名路径，已有目录需先比较内容，避免覆盖本地修改。只保留一个有效的新技能发现入口；旧 `$design-engineering` 改为 `$product-design-engineering`。安装后下一轮可用；发现异常时检查实际加载列表

## 维护与证据

- [SKILL.md](SKILL.md)：任务路由、工作方法和交付边界
- [来源映射](references/source-map.md)：研究版本、许可证据和改编取舍
- [认知与操作负担](references/cognitive-ergonomics.md)、[视觉诊断](references/experience-craft.md)：信息理解、操作路径与视觉细节
- [平台证据](references/platform-evidence.md)：Web、原生、小程序和 CLI 的适用边界
- [视觉与 Tokens](references/visual.md)、[动效](references/motion.md)、[工程交互](references/engineering.md)：语义选择、可选弹簧参数、IME 和容器自适应，保留项目自身约定
- [Agent UI](references/agent-ui.md)：仅在对话或 Agent 产品中按需加载，覆盖滚动归属、流式消息、授权和执行状态
- [研究补充](references/research-addendum.md)：本次更新包提供的来源与证据限制
- [问题类型与成熟方案](references/problem-families-and-prior-art.md)：按需识别模式、检查反例与适用条件
- [产品结果与商业判断](references/product-outcomes.md)：产品方向、增长、定价、结果证据与可预防问题，按任务需要加载
- [模式复用探针](tests/pattern-reuse-probes.md)：症状驱动任务、测试环境和独立验收条件，尚未执行
- [测试场景](tests/scenarios.md)：独立验收契约与行为探针
- [设计诊断探针](tests/design-diagnosis-probes.md)：复杂设置、账目、旧截图和跨平台等十个评估场景
- [可预防缺陷探针](tests/preventable-defects-probes.md)：实现前的信息取舍、光学布局与动效事件决策，执行状态见验证记录
- [结果责任与前瞻性探针](tests/outcome-ownership-probes.md)：结果判断、现金与积分区分、历史缺陷盲测和任务比例控制，尚未执行
- [验证记录](tests/validation.md)：迁移说明、执行结果及证据限制
- [Agent UI 与输入探针](tests/agent-ui-probes.md)：品牌保留、IME、流式滚动、状态与跨平台场景，尚未执行

新增内容为独立编写；继承的 Emil 改编保留原 MIT 通知。静态校验、有限行为对照与真实用户体验是不同证据层级，具体完成范围以验证记录为准
