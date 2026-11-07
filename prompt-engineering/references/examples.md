# Authoring examples: outcomes, cues, and completion

Read when the user needs a new prompt or a substantial behavioral rewrite and examples would resolve a genuine ambiguity. These are illustrative designs, **not measured winners or one-size-fits-all templates**. The better versions preserve the stated task; real use still requires target-model testing.

## 1. Natural conversation and personality

**Brief:** A companion should sound familiar, respond to feelings without scripted therapy, sometimes disagree, and stop adding a question to every message.

**Brittle instruction:**

```text
不要客服腔，不要总是追问，不要敷衍，不要过度共情，不要太冷漠，
不要重复用户的话，不要总给建议，不要冷冰冰地结束
```

**Behavior-centered instruction:**

```text
你是与对方逐渐熟悉、拥有自己兴趣和判断的人
留意这句话是在分享、玩笑、求助、倾诉还是结束话题，回应其中真正触动你的部分
你的好奇、关心、开心或不同意见可以自然进入交流，表达强度随关系和情境变化
当对方需要办法时认真帮忙，想聊天时接话或分享；真的想知道或缺少关键信息时提问
自己的话已经说完整时，就自然停下，给对方选择回应的空间
回忆共同经历、描述用户近况和报告实际操作时，以可靠记录为依据
```

**Why:** It connects cues to motivation, action and stopping. It preserves independent personality and factual boundaries rather than replacing all judgments with bans. Test teasing, questions that really are needed, quiet endings and differing persona styles.

## 2. Exact writing contract

**Brief:** Summarize supplied research in background → content → conclusion order, exclude numbers and implementation details, allow method names, and return only the summary.

**Brittle instruction:**

```text
认真概括文章。不要犯错，不要啰嗦，不要写没用的信息，也不要写数据或方法
```

**Task-centered instruction:**

```text
根据提供的正文撰写中文摘要，依次说明研究背景、研究内容和主要结论
保留正文支持的核心发现及适用范围；可以提及方法名称，但不展开操作过程
摘要不包含样本量、数值结果、比例或统计指标
仅输出摘要正文；缺少正文时，仅输出“缺少正文”

正文：
{{article}}
```

**Why:** The exact exclusion remains explicit, while method names and details are distinguished instead of silently banning both. Format, source grounding and missing-data behavior are complete. Do not copy this example when the user's exclusions differ.

## 3. Tool use with real side effects

**Brief:** An assistant drafts a reply from a support ticket and sends only after explicit approval of that draft.

**Brittle instruction:**

```text
你是负责任的助手。大胆行动，确保客户得到回复。不要出错
```

**Task-centered instruction:**

```text
根据工单已知事实和客户诉求准备准确、可直接使用的回复草稿，指出影响答复的未知事实
先展示草稿。只有用户明确批准当前这一版草稿，才能调用发送工具
发送后根据工具返回的确认结果报告状态；超时或结果未知时先核实状态，再决定是否需要新的操作
无法确认已发送时如实说明，不把提交请求等同于送达
```

**Why:** The useful draft, authorization boundary, uncertain outcome and stop condition coexist. The runtime must still enforce approval, tool schemas and idempotency; prompt wording is not a transaction guarantee.

## 4. Refactoring a legacy prompt

**Brief:** Remove repetition from a customer-support instruction while retaining customer-specific drafting and approval-before-send.

**Before:**

```text
帮助用户准备客服回复，不要敷衍，不要不认真，不要忘记认真，不要忽视诉求
根据工单明确客户诉求和已知事实，写出对应的回复草稿
只有用户明确批准这一版草稿才可发送
不要未经批准发送，不要擅自发送
```

**After:**

```text
根据工单明确客户诉求与已知事实，写出具体、准确、贴合对方问题的回复草稿
草稿供用户确认；仅在用户明确批准当前版本后发送
```

**Why:** Multiple stylistic warnings become one observable task standard; duplicate sending bans retain their actual permission condition. If the original system also defines failed-send behavior, preserve that separate contract. Never equate shorter text with proven better downstream adherence.

## How to use these

Choose the closest *decision pattern*, not the closest surface wording. Adapt the goal, cue, boundary and interface to the user's task. For an exact JSON protocol, prioritize schema and examples with exact fields. For a persona, use varied multi-turn examples only when needed; do not make the sample reply a mandatory script. See [Behavior design](behavior-design.md), [Prompt authoring](prompt-authoring.md), and [Evaluation](evaluation.md).
