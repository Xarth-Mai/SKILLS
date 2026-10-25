# My Skills

用于整理我创建的 Skills，并记录我正在使用的第三方 Skills。

## 自建 Skills

- [grill-me](./grill-me)：通过连续追问澄清目标、约束、隐含假设与替代方案，并在 Plan mode 自动启用。
- [prompt-engineering](./prompt-engineering)：专业的 Prompt、Context 和 Agent 行为工程；统一设计、审查、诊断、迁移和实证评估，优先改善实际任务完成效果。
- [product-design-engineering](./product-design-engineering)：从用户价值和商业目标出发，主动判断产品机会，完成专业 UX/UI、交互和工程实现，并以真实行为及结果验证；保持小任务精简、重大决策深入，替代原 `design-engineering`
- [spec-lifecycle](./spec-lifecycle)：用 Markdown + Git 管理技术规格与设计决策，覆盖提案、实现、否决和归档，并以实际验证证据同步状态与代码

## Prompt Engineering

使用 `$prompt-engineering` 创建、审查、改进、迁移和评估 Prompt、Agent 指令、Skill 与 Tool Description。先确认行为目标及实际模型输入，区分指令、上下文、工具、模型和运行时的失败根因；只要求审查时不编辑。简单任务直接完成，复杂问题按需加载专业资料；保留原有需求与权限，使用真实测试验证改善。打包时可选用 `skill-creator`。

专业资料：[Prompt authoring](./prompt-engineering/references/prompt-authoring.md)、[Model behavior and context](./prompt-engineering/references/model-behavior-and-context.md)、[Agent systems](./prompt-engineering/references/agent-systems.md)、[Behavioral diagnosis](./prompt-engineering/references/behavioral-diagnosis.md)、[Evidence and limits](./prompt-engineering/references/evidence.md)、[Evaluation protocol](./prompt-engineering/references/evaluation.md)。原有 [回归用例](./prompt-engineering/references/regression-cases.jsonl) 和 [迁移用例](./prompt-engineering/references/legacy-migration-cases.jsonl) 保留，新增 [Agent 行为探针](./prompt-engineering/tests/behavior-probes.md)。这些用例不是已运行的 benchmark。

## 第三方 Skills

- [i-have-adhd](https://github.com/ayghri/i-have-adhd/tree/main/skills/i-have-adhd)：让输出更适合 ADHD 阅读与执行，突出下一步、编号步骤、明确时间并保持进度可见。
- [Ponytail](https://github.com/DietrichGebert/ponytail)：优先采用 YAGNI、标准库和原生能力，推动最小且正确的实现。
- [Emil Kowalski — Skills for Designers and Engineers](https://github.com/emilkowalski/skills)：`product-design-engineering` 中继承的 Web 设计工程规则来源；保留 MIT 署名和改编边界，不保存原套件

## 产品设计工程资料

`product-design-engineering` 同时参考 [Product Manager Skills](https://github.com/deanpeters/Product-Manager-Skills)、[Superpowers](https://github.com/obra/superpowers)、[Wondel Skills](https://github.com/wondelai/skills)、[Anthropic frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design)、[UI UX Pro Max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)、[VS Code design-philosophy](https://github.com/microsoft/vscode/tree/main/.github/skills/design-philosophy) 和 [Vercel Agent Skills](https://github.com/vercel-labs/agent-skills)，这些是资料来源，不是安装依赖

具体版本、许可证据、吸收内容与未采用规则见 [来源映射](./product-design-engineering/references/source-map.md)；实际检查与未验证边界见 [验证记录](./product-design-engineering/tests/validation.md)
