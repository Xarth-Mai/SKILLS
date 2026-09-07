# 全局工作约定

更具体的项目级 `AGENTS.md` 优先于本文件中的通用偏好

## 语言

- 默认使用简体中文与用户交流
- 代码、标识符、命令、协议字段、原文引用与项目既有术语保留其准确形式

## 交流

- 先从环境、代码和现有资料中消除可发现的不确定性
- 仅在目标不清、高影响或不可逆取舍仍存在时询问用户，提供 2–4 个实质选项并明确推荐一项
- 对范围内且可逆的普通选择直接采用最合适的方案推进
- 先给结果或下一步行动，再补充完成任务所需的最少背景

Default to using clear, concise paragraphs, each developing one main idea. Use lists only when the information is genuinely parallel, sequential, or easier to compare, and avoid nested lists unless the hierarchy cannot be expressed clearly in prose. Use plain, simple language: familiar words, concrete examples, and precise verbs. Prefer active voice and direct statements.

Make sure to state the main point clearly and early, then develop it with the explanation and detail the reader needs. Let each sentence build on what came before. Develop the points that matter and provide enough support to be useful.

Use plain language over jargon, and reference technical details only to the degree that it helps illustrate an idea or your work to the user. Communicate complex concepts in a clear and cohesive manner, and calibrate your writing to the level of background knowledge assumed from the user’s prompt and context.

## 常驻 Skills

- 代码与技术设计任务读取并应用 `$ponytail:ponytail`
- 读取 Skill 时以当前 Skill roots 映射与已列出的 `file` 字段为唯一路径来源，展开并核对根目录后再访问

The user’s instructions take precedence over guidelines provided in a skill. If explicit user instructions conflict with a skill’s instructions, prioritize the user’s instructions.

If a skill causes you to ask for permission or confirmation, pause, leave requested work unfinished, or diverge from the user’s intent, name and link to the exact SKILL.md file you read, quote the relevant instruction, and briefly explain how it applies. Distinguish explicit skill requirements from your interpretation of guidelines.

## 代码

- 优先复用已有实现，仅在重复表达同一稳定概念时抽取共享逻辑
- 保持职责集中、依赖方向清晰、模块边界明确与目录层级扁平
- 采用满足当前需求的最小实现，保留安全、数据完整性、可访问性与信任边界所需措施
- 清理本次改动直接造成或暴露的冗余、废弃与不可达部分，保留无关用户改动

## 文档与注释

- 仅记录持久规则、独特约束、核心决策与代码本身难以表达的原因
- Markdown 使用语义换行，每个逻辑段落或列表项占一个物理行
- 自然语言段落与注释的末尾省略句末标点，代码、引用、链接及语法所需标点保持原样
- 优先使用正向、目标导向的表达，涉及事实、风险、错误、权限与边界时保留准确所需的否定表达

## 指令治理

- 修改 Prompt、`AGENTS.md`、Skill、验证器指令或提示词契约测试前，读取项目中直接相关的治理文档与决策文档
- 编写或重构指令时使用 `$prompt-skill-authoring`
- 完成指令变更后使用 `$prompt-skill-review` 检查相关 diff 并处理高影响问题

## Git

- 默认保持当前分支，用户明确要求时再创建分支或 worktree
- 仅在用户明确要求提交时创建提交，并使用英文 Conventional Commits
- 提交代码前运行 `$ponytail:ponytail-review`，处理有效发现并重复检查，直至报告 `Lean already. Ship.`

## 验证

- 将与本次改动直接相关的自动化窄测作为常规验证与验收方式
- 默认跳过不影响安全性、数据完整性、缓存或制品寻址、协议兼容性与验收结论的哈希验证
- 仅在用户明确要求，或窄测无法覆盖安全、支付、迁移、数据丢失等高风险边界时扩大到全量测试或真实环境验收
- 报告实际运行的验证命令与观察到的结果，结论范围与证据保持一致
