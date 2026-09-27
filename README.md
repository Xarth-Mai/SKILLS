# My Skills

用于整理我创建的 Skills，并记录我正在使用的第三方 Skills。

## 自建 Skills

- [grill-me](./grill-me)：通过连续追问澄清目标、约束、隐含假设与替代方案，并在 Plan mode 自动启用。
- [prompt-skill-authoring](./prompt-skill-authoring)：编写、重构提示词与 Skill 指令；以完整保留需求、明确执行契约和可验证的指令遵循为目标。
- [prompt-skill-review](./prompt-skill-review)：审查需求覆盖、冲突、权限与运行时契约，提出有证据的修正，并区分静态检查与实测改进。
- [design-engineering](./design-engineering)：为 Web UI 提供视觉层级、排版、交互反馈、克制动效和可访问性规则，覆盖实现与审查；保留项目品牌和现有技术栈。

## 提示词 Skills 的配合方式

写作或重构时使用 `$prompt-skill-authoring`；诊断、审查或比较现有指令时使用 `$prompt-skill-review`。两者可独立安装，Skill 格式相关工作可配合可用的 `skill-creator`。

核心目标是任务有效完成且所有适用的强制要求同时满足。正向表述、否定约束、示例、重复和约束排序都服务于这个目标，不作为脱离模型与任务的固定教条。

研究依据见 [Evidence and limits](./prompt-skill-authoring/references/evidence.md)；比较方法见 [Evaluation protocol](./prompt-skill-review/references/evaluation.md)。附带的 [回归用例](./prompt-skill-review/references/regression-cases.jsonl) 是开发探针，不是已运行的 benchmark。静态检查通过不代表下游模型遵循率已提升

## UI 设计工程

`design-engineering` 是一个独立 Skill，不需要同时安装原作者的六个入口。它负责设计判断、交互细节和验收，可与 `sites-building`、`ponytail` 等已有实现流程配合；不接管发布、预览基础设施或数据分析，也不依赖 Figma 插件。

实现请求会推进到修改与验证；只审查时保持只读。保留项目已有品牌、组件和 tokens，不默认套用 Apple 视觉风格，也不为增加动效引入不必要的依赖。

在 Codex 中使用：

```text
$design-engineering 优化这个页面的层级、间距和交互反馈，保留现有品牌与功能，并验证修改。
$design-engineering 只审查这个页面的 UI 和动效，给出有证据的发现，不修改代码。
```

合并后可让 Codex 的 `$skill-installer` 从 `Xarth-Mai/SKILLS` 安装 `design-engineering` 子目录；也可把完整目录放到 `~/.agents/skills/design-engineering/`（个人范围）或项目的 `.agents/skills/design-engineering/`。保留其中的 `agents/` 和 `references/`；安装方式以 [Codex 官方文档](https://developers.openai.com/codex/skills) 为准。

[来源与取舍](./design-engineering/references/sources.md) 记录固定上游版本、六类内容的整理方式及许可证声明；[验证场景](./design-engineering/references/validation.md) 提供路由与行为探针。探针尚未在目标 Codex 环境执行，不能据此声称生成质量已经提升。

## 第三方 Skills

- [i-have-adhd](https://github.com/ayghri/i-have-adhd/tree/main/skills/i-have-adhd)：让输出更适合 ADHD 阅读与执行，突出下一步、编号步骤、明确时间并保持进度可见。
- [Ponytail](https://github.com/DietrichGebert/ponytail)：优先采用 YAGNI、标准库和原生能力，推动最小且正确的实现。
- [Emil Kowalski — Skills for Designers and Engineers](https://github.com/emilkowalski/skills)：`design-engineering` 的选摘整理来源；这里只维护适配版本和来源说明，不保存原套件。
