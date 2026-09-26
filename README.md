# My Skills

用于整理我创建的 Skills，并记录我正在使用的第三方 Skills。

## 自建 Skills

- [grill-me](./grill-me)：通过连续追问澄清目标、约束、隐含假设与替代方案，并在 Plan mode 自动启用。
- [prompt-skill-authoring](./prompt-skill-authoring)：编写、重构提示词与 Skill 指令；以完整保留需求、明确执行契约和可验证的指令遵循为目标。
- [prompt-skill-review](./prompt-skill-review)：审查需求覆盖、冲突、权限与运行时契约，提出有证据的修正，并区分静态检查与实测改进。

## 提示词 Skills 的配合方式

写作或重构时使用 `$prompt-skill-authoring`；诊断、审查或比较现有指令时使用 `$prompt-skill-review`。两者可独立安装，Skill 格式相关工作可配合可用的 `skill-creator`。

核心目标是任务有效完成且所有适用的强制要求同时满足。正向表述、否定约束、示例、重复和约束排序都服务于这个目标，不作为脱离模型与任务的固定教条。

研究依据见 [Evidence and limits](./prompt-skill-authoring/references/evidence.md)；比较方法见 [Evaluation protocol](./prompt-skill-review/references/evaluation.md)。附带的 [回归用例](./prompt-skill-review/references/regression-cases.jsonl) 是开发探针，不是已运行的 benchmark。静态检查通过不代表下游模型遵循率已提升

## 第三方 Skills

- [i-have-adhd](https://github.com/ayghri/i-have-adhd/tree/main/skills/i-have-adhd)：让输出更适合 ADHD 阅读与执行，突出下一步、编号步骤、明确时间并保持进度可见。
- [Ponytail](https://github.com/DietrichGebert/ponytail)：优先采用 YAGNI、标准库和原生能力，推动最小且正确的实现。
