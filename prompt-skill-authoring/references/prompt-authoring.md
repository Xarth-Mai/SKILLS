# Authoring for reliable instruction following

Use the relevant sections; this is not a compulsory template. The workflow below is engineering synthesis. The local [evidence notes](evidence.md) distinguish research results from provider advice and design judgments.

## 1. Define success before changing wording

Recover what the user actually wants the model to do, the information available, allowed actions, and what a useful complete result must contain. Preserve existing constraints unless the user authorizes a behavior change.

For a consequential prompt, keep a small requirement record:

| ID | Source and scope | Requirement and applicability | Class | Acceptance check |
| --- | --- | --- | --- | --- |
| R1 | User brief; final answer | Return the requested summary, grounded in the supplied article | Mandatory | Compare claims and coverage with source |
| R2 | User brief; summary body | Omit quantitative findings | Mandatory | Semantic review; numeric scan is only a signal |
| R3 | User preference; prose | Prefer concise sentences | Preference | Rubric, subordinate to coverage |

A row is an obligation, not necessarily one sentence. Split independently failing requirements but preserve their logic. “Return JSON **or** CSV” is one choice, not two output obligations. “Explain only when confidence is low” must not become “always explain.” An optional preference is not a release-blocking constraint unless the owner makes it one.

Translate vague but consequential terms into observable behavior. Obtain the intended definition from the brief, existing examples, caller, or a necessary clarification. Do not turn “avoid detailed methods” into “ban all method names,” or “no data” into “remove all dates and numerals,” without a basis. A modifier such as “无数据” already expresses an exclusion; making it a separate sentence improves inspectability, not its logical authority.

Check that the requirements can coexist and fit the available input/output budget. Missing facts need a defined missing-data behavior, not a stronger demand for confidence. For an unresolved mandatory conflict, identify the conflict and seek the smallest necessary decision, or use a previously authorized failure response. Do not silently choose which requirement to violate.

## 2. Write actionable, scoped instructions

A useful requirement identifies the action or output property, its scope, and any trigger or exception. Add a boundary action only when the workflow needs one.

Weak: “Be rigorous and professional.”

Operational: “Distinguish source-supported findings from interpretation; attach each factual claim to the supplied evidence.”

Positive target plus exclusion: “Write a qualitative summary of the supported findings. Omit quantitative results and implementation steps.”

Use a negative instruction when exclusion is the requirement. “Do not send the draft” is clearer than a euphemism that leaves sending ambiguous. Specify what remains useful: prepare a draft and report where it is saved. There is no general need to translate every prohibition into positive prose.

Keep mandatory requirements visibly distinct from preferences when a tradeoff matters. Importance, estimated difficulty, and message authority are different concepts. Importance informs acceptance; difficulty is an empirical property; authority comes from the runtime. Ordering text does not resolve a logical contradiction.

Choose natural prose for a simple task and headings or a short list for a multi-part task. An independent check does not require a separate heading, an ID in the runtime prompt, or repeated “must” wording.

## 3. Assemble the context deliberately

Separate durable policy from the current request, examples, and source material. Inspect actual message roles and concatenation, including shared prompts that callers add. Keep one maintained definition per rule; a short local recap can still be useful where forgetting it is a demonstrated problem.

Use consistent Markdown, XML, or another host-supported delimiter to distinguish semantic regions. Delimiters are parsing aids, not security enforcement. Escape, serialize, or frame untrusted input in the application so its own tags cannot casually terminate a source section. Keep permissions and irreversible-action checks outside source-controlled text.

For long inputs, place the task where the model will actually see it and make relevant evidence retrievable. A concise task reminder near generation is a candidate intervention, not an automatic requirement. Preserve required evidence when shortening context. Confirm that neither instructions nor output are truncated before diagnosing a wording failure.

Cache-friendly prefixes may reduce costs when supported. Inspect provider semantics and recorded usage; a rearranged template by itself does not prove cache reuse.

## 4. Select techniques by the ambiguity they solve

**Examples.** Use representative input/output pairs when a boundary, house style, or format remains ambiguous. Ensure every example satisfies all applicable requirements; vary irrelevant surface details. Keep evaluation answers out of examples. Compare no-example and example variants when the benefit is uncertain. There is no universally optimal count, and lower prompt sensitivity does not by itself prove higher accuracy.

**Constraint ordering.** Keep dependent instructions together. For independent constraints, test a difficulty-informed order when failures justify it. “Hard-to-easy” research does not mean all prohibitions, high-risk rules, or difficult-looking words always go first.

**Repetition.** Consolidate conflicting copies and stale definitions. Preserve useful recaps. Deliberate repetition is an empirical option, especially for some non-reasoning setups; measure input cost, context pressure, and end-to-end results. Neither “always repeat” nor “never repeat” is a default correctness rule.

**Roles.** Define responsibility, audience, or perspective when these change the output. Keep user-requested characterization. Credentials and superlatives are not substitutes for criteria or evidence, and factual-QA persona studies do not establish that creative roles are useless.

**Reasoning.** Specify relevant evidence, decision criteria, and required explanations or calculations. Avoid demanding private chain-of-thought transcripts. Do not add a fixed thinking ritual to every model. A required operational sequence, such as validate → obtain authorization → mutate, remains valid even when internal reasoning is flexible.

## 5. Make the output contract complete

State format, required content, units, lengths, allowed fields, ordering, and explanation policy only where they matter. Keep format-sensitive examples exact. Align schema, prompt, parser, and downstream expectations.

For strict structured output, use a supported schema or constrained interface and still validate values, evidence, and business rules. JSON syntax alone does not make content correct. Represent missing data or failure within the agreed contract, or use the host's explicit error channel; do not append prose to JSON-only output.

Define counting semantics when exact length is important: words, Unicode characters, Chinese characters, bytes, and tokens are different. Reuse the application's counter. Do not rely on the model to certify exact length.

Conditional abstract template — the exclusions below are an **illustrative chosen contract**, not an automatic interpretation of every “no data/no methods” request:

```text
根据提供的正文撰写摘要，依次概括研究背景、研究内容和主要结论。

要求：
- 保留原文支持的核心发现及其适用范围。
- 不写量化结果，包括样本量、测量值、比例和统计指标。
- 不写方法名称、技术路线或操作步骤。
- 仅输出摘要正文。

正文：
{{article}}
```

Complete miniature example for that contract:

```text
输入：校园维修申请分散，处理进度不透明。研究采用问卷调查，收集了240份反馈，
并设计统一工单平台。试运行中平均等待时间缩短18%，但跨部门协作仍存在障碍。

输出：针对校园维修申请分散、处理进度不透明的问题，研究围绕统一工单平台的
建设与使用效果展开。研究发现，该平台有助于缩短维修等待时间，但跨部门协作
仍存在障碍。
```

Use this example only where its exclusion scope matches the requested contract. Every claim in its output is supported by the input. Preserve that grounding when adapting examples; do not add recommendations or stronger conclusions merely to make an abstract sound complete.

## 6. Put tools and verification where they belong

Describe a tool's purpose, trigger, arguments, outputs, limits, side effects, and failure semantics. Match the real implementation. Return values are evidence for what actually happened, not permission to assume later steps succeeded.

Use deterministic code for exact counting, schema validation, arithmetic, IDs, and permission enforcement when available. Use grounded semantic review for fidelity, relevance, whether a method is disclosed, and whether a conclusion overstates evidence. A regex that finds digits cannot fully decide whether quantitative data is present.

Add stages only when a real bottleneck justifies them: retrieval for missing evidence, planning for dependencies, validation for detectable errors, or bounded repair for known violations. More agents are not inherently more reliable. Pass only the needed context and preserve shared invariants across stages.

On repair, return the failed requirement IDs, output locations, expected property, and supporting evidence. Revise the affected region, preserve valid content, and rerun dependent checks. Set attempt and tool-use budgets in the actual workflow. At exhaustion, use the agreed unresolved/failure state instead of claiming success or looping indefinitely.

## 7. Compare candidates without gaming success

Preserve a baseline and freeze the requirement rubric independently of the candidate. Use representative normal, boundary, missing-input, long-context, and authorized tool-failure cases. Hold out cases not used to tune wording or select examples.

Keep model version, reasoning settings, sampling, token limits, input assembly, tools, and retry budgets comparable. Record any unavoidable drift. Evaluate full task usefulness and applicable requirements together: an empty summary does not pass just because it contains no prohibited data.

Measure first-attempt whole-request pass rate, per-requirement failures, severe violations, final success after bounded repair, and total cost/latency. Report uncertain checks as uncertain. Inspect regressions before promoting a candidate; a tiny sample or self-rating is not proof of optimality.

If execution is unavailable, deliver the candidate, static checks, and a runnable-by-the-host test plan. Mark behavioral effectiveness unverified. Do not make up test results or defer useful editing merely because comparative execution is unavailable.
