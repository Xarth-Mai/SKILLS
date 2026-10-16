# My Skills

用于整理我创建的 Skills，并记录我正在使用的第三方 Skills。

## 自建 Skills

- [grill-me](./grill-me)：通过连续追问澄清目标、约束、隐含假设与替代方案，并在 Plan mode 自动启用。
- [prompt-skill-authoring](./prompt-skill-authoring)：编写、重构提示词与 Skill 指令；以完整保留需求、明确执行契约和可验证的指令遵循为目标。
- [prompt-skill-review](./prompt-skill-review)：审查需求覆盖、冲突、权限与运行时契约，提出有证据的修正，并区分静态检查与实测改进。
- [product-design-engineering](./product-design-engineering)：从产品需求、UX、视觉与动效到工程实现和验收，主动补齐重要遗漏并给出决策依据；跨平台核心、Web 专项深度，替代原 `design-engineering`
- [spec-lifecycle](./spec-lifecycle)：用 Markdown + Git 管理技术规格与设计决策，覆盖提案、实现、否决和归档，并以实际验证证据同步状态与代码

## 提示词 Skills 的配合方式

写作或重构时使用 `$prompt-skill-authoring`；诊断、审查或比较现有指令时使用 `$prompt-skill-review`。两者可独立安装，Skill 格式相关工作可配合可用的 `skill-creator`。

核心目标是任务有效完成且所有适用的强制要求同时满足。默认使用具体、高信息密度的正向行为定义；每段塑造行为、提供判断依据或规定必要边界。清理冗余否定、防御性免责声明和重复约束，保留必要排除及其条件。人格提示词连接感知、情绪、动机与行动

研究依据见 [Evidence and limits](./prompt-skill-authoring/references/evidence.md)；比较方法见 [Evaluation protocol](./prompt-skill-review/references/evaluation.md)。附带的 [回归用例](./prompt-skill-review/references/regression-cases.jsonl) 是开发探针，不是已运行的 benchmark。静态检查通过不代表下游模型遵循率已提升。

## 第三方 Skills

- [i-have-adhd](https://github.com/ayghri/i-have-adhd/tree/main/skills/i-have-adhd)：让输出更适合 ADHD 阅读与执行，突出下一步、编号步骤、明确时间并保持进度可见。
- [Ponytail](https://github.com/DietrichGebert/ponytail)：优先采用 YAGNI、标准库和原生能力，推动最小且正确的实现。
- [Emil Kowalski — Skills for Designers and Engineers](https://github.com/emilkowalski/skills)：`product-design-engineering` 中继承的 Web 设计工程规则来源；保留 MIT 署名和改编边界，不保存原套件

## 产品设计工程资料

`product-design-engineering` 同时参考 [Product Manager Skills](https://github.com/deanpeters/Product-Manager-Skills)、[Superpowers](https://github.com/obra/superpowers)、[Wondel Skills](https://github.com/wondelai/skills)、[Anthropic frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design)、[UI UX Pro Max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)、[VS Code design-philosophy](https://github.com/microsoft/vscode/tree/main/.github/skills/design-philosophy) 和 [Vercel Agent Skills](https://github.com/vercel-labs/agent-skills)，这些是资料来源，不是安装依赖

具体版本、许可证据、吸收内容与未采用规则见 [来源映射](./product-design-engineering/references/source-map.md)；实际检查与未验证边界见 [验证记录](./product-design-engineering/tests/validation.md)
