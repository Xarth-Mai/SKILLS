---
name: spec-lifecycle
description: "Manage technical specs and design decisions with a minimal Markdown lifecycle in docs/proposed, docs/implemented, docs/rejected, and docs/archived. Use when initializing the convention, drafting or reviewing a spec, recording acceptance or rejection, completing implementation, archiving superseded designs, or keeping specs aligned with code. 适用于初始化 Spec 管理、记录技术决策、验收完成、否决或归档方案。"
---

# Spec Lifecycle

在任意代码仓库中使用 Markdown + Git 管理技术规格（Spec）与长期设计决策。规范固定为 `docs/` 下四个目录；不引入分类子目录、索引、数据库或审批框架。

## 何时应用

- 用户明确要求初始化、引入、整理或审计 Spec 生命周期时，使用本 Skill。
- 用户要求编写、批准、实现、否决、归档某个 Spec 时，使用本 Skill。
- 项目已经采用本规范，当前代码变更影响相关的已实现 Spec 时，主动同步文档。
- 不要仅因一次普通修复、代码清理或局部调整，就强行创建 Spec 或替未采用本规范的项目初始化目录。
- 服从仓库自身的 `AGENTS.md` 和用户给定的更具体约束；冲突时说明差异。

## 固定目录

```text
docs/
├── proposed/
├── implemented/
├── rejected/
└── archived/
```

Spec 直接放在相应目录，使用具有稳定语义的 `kebab-case.md` 文件名，例如 `profile-sandbox-isolation.md`。移动时保持文件名不变。不要额外创建功能/架构分类目录或汇总索引。

| 目录 / Status | 含义 | 进入条件 |
| --- | --- | --- |
| `proposed` | 待决策，或已批准但未完成 | 有待实施/验收的设计 |
| `implemented` | 已实现、已验证、当前有效 | 有实现与验收证据 |
| `rejected` | 已明确否决或放弃 | 有明确的否决决策与理由 |
| `archived` | 曾经实现、现已失效 | 已废弃、过时或被替代，并记录原因 |

`proposed` 中使用 `Decision: open` 或 `Decision: accepted` 区分讨论中和已批准；**批准不等于实现完成**。其他目录不使用 `Decision` 字段。

## 工作流程

### 1. 先检查，再编辑

1. 确定当前仓库根目录，阅读适用的 `AGENTS.md` 与既有 Spec。
2. 查看目标文件及 Git 工作区变化，区分现有用户修改与本次任务范围；不要覆盖无关改动。
3. 查找相同主题的既有 Spec；优先更新原文件，避免多个文件描述同一项当前决策。
4. 核实代码、配置、测试和相关 PR/提交。明确区分「代码已存在」「测试已通过」「尚未验证」。

### 2. 初始化项目

仅在用户明确要求引入本规范时：

1. 创建 `docs/proposed/`、`docs/implemented/`、`docs/rejected/`、`docs/archived/`。
2. 如果空目录需要在 Git 中保留，可放置 `.gitkeep`；目录有 Spec 后可删除其 `.gitkeep`。
3. 在用户要求将规范固定到项目时，向 `AGENTS.md` 合并以下最小规则，保留原有内容；不要重复插入：

   > Manage technical Specs as Markdown files directly in `docs/proposed/`, `docs/implemented/`, `docs/rejected/`, and `docs/archived/`. The `Status` field must match the directory. Use `Decision: open | accepted` only for proposed Specs. Move to implemented only after implementation and verification. Record rejection/archive reasons and keep implemented Specs aligned with code. Use the `spec-lifecycle` Skill when available.

4. 已有文档迁移先逐一检查实际状态；状态不明确时保留原位置或列出待核实项，不能凭文件标题推断已实现。
5. 初始化工作不应擅自修改业务代码。

### 3. 新建或修改 Spec

对需要长期留存的架构选择、接口契约、数据模型、安全边界、重要功能方案创建 Spec。优先清楚描述问题、设计、备选方案、验收条件；无需为空章节填充套话。

基础模板：

```markdown
# <Spec Title>

Status: proposed
Decision: open

## Background
问题、约束和目标。

## Design
拟采用的方案、行为和关键边界。

## Alternatives
考虑过的方案和取舍理由。

## Acceptance Criteria
可验证的完成条件。

## Implementation
尚未实现；实施时补充代码位置及验证证据。
```

规则：
- `Status` 必须与所在目录名一致，合法值仅为 `proposed`、`implemented`、`rejected`、`archived`。
- 仅在 `proposed` 使用 `Decision: open | accepted`。
- 标题、`Status`、背景、设计和适用的验收依据应明确；章节可以按主题增删或重命名。
- 不虚构测试、PR、代码路径、审批结果或用户决策。
- `implemented` 必须陈述**实际落地的设计**，而非仅保留早期设想。
- `rejected` 保留原方案上下文，并明确写出 `## Rejection Reason`。
- `archived` 保留历史实现上下文，并明确写出 `## Archive Reason`；如存在替代 Spec，提供相对链接。

### 4. 生命周期转换

- **Proposed（open → accepted）**：仅在决策确已明确时更新 `Decision`；文件仍在 `proposed/`。
- **Proposed → Implemented**：检查验收条件、代码和验证结果；更新设计为真实实现，记录实现路径、测试命令/结果或等效证据；移至 `implemented/` 并更新 `Status`，移除 `Decision`。未验证时仍留在 `proposed/`，列明欠缺证据。
- **Proposed → Rejected**：在用户或有权决策者明确否决时，保留方案内容，补充 `## Rejection Reason`，移至 `rejected/` 并更新 `Status`，移除 `Decision`。不得将「暂缓」擅自解释为否决。
- **Implemented → Archived**：确认旧方案确已不再有效；补充 `## Archive Reason`、替代方案链接（如有），移至 `archived/` 并更新 `Status`。新实现如需单独设计，应有自己的 Proposed/Implemented Spec。
- **重新启用历史方案**：默认创建新的 `proposed/` Spec 并引用旧 Rejected/Archived 文档，而不是改写历史记录。

使用 Git 移动/重命名文件，保留可追溯性；不要删除被否决、归档的决策历史。状态变更涉及多个相关 Spec 时，核实交叉链接并同步更新。

### 5. 维护与审计

当代码变更影响 `implemented/` 中的描述时，在同一任务内同步更新该 Spec。发现代码和文档冲突时，调查实际行为与决策，不把「改一行 Status」当作修复。

审计时检查：
- 四个目录是否存在，是否有非规范分类目录或重复的当前 Spec。
- 每份 Spec 的路径、`Status` 与 `Decision` 是否一致。
- `implemented` 是否有实现位置及可靠验收依据，且内容符合现状。
- `rejected`、`archived` 是否记录理由；被替代的 Spec 是否可追溯。
- 所有相对链接是否有效；是否存在与用户修改冲突的操作。

只对能够核实的部分作出结论。若代码、测试或权限不可用，明确标识「待验证」，不要推断通过。

## 向用户交付

简短报告本次创建、更新或移动的文件，说明相应状态和理由；如涉及 `implemented`，列出实际验证方式和结果。若没有修改文档，说明原因。避免输出无关的项目管理内容。
