# Product Design Engineering

从产品需求、UX、UI 和动效，到工程实现、审查与验收的跨项目 Skill，替代本仓库原 `design-engineering`

主入口选择任务所需的 Frame、Audit、Design、Build、Review 阶段；专业参考按需加载，保留项目自身的品牌、技术栈与平台约定，跨平台核心之外提供较深入的 Web 指导

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
- [测试场景](tests/scenarios.md)：独立验收契约与行为探针
- [验证记录](tests/validation.md)：迁移说明、执行结果及证据限制

新增内容为独立编写；继承的 Emil 改编保留原 MIT 通知。静态校验、有限行为对照与真实用户体验是不同证据层级，具体完成范围以验证记录为准
