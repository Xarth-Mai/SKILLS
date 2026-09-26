# Evidence and limits

Checked 2026-09-26. This is a selected primary-source evidence map, not an exhaustive review or a measured ranking of prompts. Research supports candidate mechanisms and evaluation practices; target-model validation determines whether a particular rewrite helps.

## How to use evidence

Distinguish **research findings**, **provider recommendations**, and **engineering synthesis**. A benchmark that decomposes requirements validates an evaluation approach; it does not automatically prove that bullet lists outperform equivalent prose. A task-accuracy gain is not necessarily an instruction-adherence gain. Record model versions, task, language, context, and inference setup before transferring a result.

## Research

### R1. FollowBench — ACL 2024

[FollowBench: A Multi-level Fine-grained Constraints Following Benchmark for Large Language Models](https://aclanthology.org/2024.acl-long.257/)

Studies several constraint categories and increasing constraint load. Supports checking multiple obligations separately and testing combinations. Does not directly establish the winner between a Chinese “禁止出现…” clause and a semantically equivalent “无…的摘要” modifier.

### R2. InFoBench — Findings ACL 2024

[InFoBench: Evaluating Instruction Following Ability in Large Language Models](https://aclanthology.org/2024.findings-acl.772/)

Introduces decomposed requirement evaluation. Supports a requirement ledger and localized failure reporting. The use of model-based annotation does not make the judge infallible, and average requirement success can conceal whole-request failure.

### R3. IFEval — 2023 preprint

[Instruction-Following Evaluation for Large Language Models](https://arxiv.org/abs/2311.07911)

Uses verifiable instructions for reproducible evaluation. Supports deterministic checks where the property is actually decidable. Its mechanically verifiable tasks do not replace semantic checks for source fidelity, usefulness, or meaning-based exclusions.

### R4. DeCRIM — Findings EMNLP 2024

[LLM Self-Correction with DeCRIM: Decompose, Critique, and Refine for Enhanced Following of Instructions with Multiple Constraints](https://aclanthology.org/2024.findings-emnlp.458/)

Studies explicit constraint decomposition and critique/refinement on RealInstruct and IFEval. Supports testing evidence-bearing, targeted repair. Improvements belong to the evaluated pipeline and feedback setup; adding “check your work” to a prompt is not the same intervention.

### R5. Order Matters — Findings ACL 2025

[Order Matters: Investigate the Position Bias in Multi-constraint Instruction Following](https://aclanthology.org/2025.findings-acl.646/)

Finds position effects and an advantage for hard-to-easy ordering in the studied setting. Treat ordering as a testable parameter. Difficulty is not severity or authority, and the study is not a universal mandate to put all prohibitions first.

### R6. What Prompts Don't Say — Findings ACL 2026

[What Prompts Don't Say: Understanding and Managing Underspecification in LLM Prompts](https://aclanthology.org/2026.findings-acl.441/)

Finds fragility when prompts leave requirements implicit, but also reports that specifying all requirements does not consistently help because instruction-following limits and conflicts remain. Supports requirements discovery plus evaluation, not exhaustive rule accumulation. Explicit exclusions embedded in a phrase are not automatically unspecified requirements.

### R7. POSIX — Findings EMNLP 2024

[POSIX: A Prompt Sensitivity Index For Large Language Models](https://aclanthology.org/2024.findings-emnlp.852/)

Studies sensitivity to intent-preserving prompt variations and finds benefits from exemplars for that metric. Supports paraphrase robustness tests and trials of examples. Reduced sensitivity is distinct from higher correctness; one example is not guaranteed to improve every model or task.

### R8. Persona study — Findings EMNLP 2024

[When “A Helpful Assistant” Is Not Really Helpful: Personas in System Prompts Do Not Improve Performances of Large Language Models](https://aclanthology.org/2024.findings-emnlp.888/)

Finds no reliable aggregate improvement from persona additions on the studied factual questions. Prefer functional responsibilities to decorative expertise claims. Do not transfer the finding into a prohibition on user-requested roleplay, creative perspective, or audience specification.

### R9. Prompt Repetition — 2025 preprint

[Prompt Repetition Improves Non-Reasoning LLMs](https://arxiv.org/abs/2512.14982)

Reports gains from repeating the input on selected models and tasks, especially without reasoning. This is a counterexample to “repetition is always waste.” It does not justify universal duplication, guarantee free input tokens, or establish equivalent benefits for long-context agent instruction following.

### R10. Intrinsic self-correction — ICLR 2024

[Large Language Models Cannot Self-Correct Reasoning Yet](https://arxiv.org/abs/2310.01798)

Reports limitations of intrinsic self-correction without external feedback in the evaluated reasoning settings. Supports distinguishing a self-review from independent verification. It does not show that all revision, all critics, or all semantic review is ineffective.

### R11. IHEval — 2025 preprint

[IHEval: Evaluating Language Models on Following the Instruction Hierarchy](https://arxiv.org/abs/2502.08745)

Studies aligned and conflicting instructions across message sources. Supports testing actual message roles and lower-trust interference, not only isolated prompt text. Text labels and delimiters alone do not enforce privileges.

### R12. Lost in the Middle — 2023 preprint; TACL 2024

[Lost in the Middle: How Language Models Use Long Contexts](https://arxiv.org/abs/2307.03172)

Studies position-sensitive use of evidence in long contexts. Supports testing evidence placement and realistic context lengths. It is not direct proof that every hard constraint belongs at the start, or that every shorter prompt is better.

## Provider recommendations

### D1. OpenAI reasoning guidance

[Reasoning best practices](https://developers.openai.com/api/docs/guides/reasoning-best-practices)

Recommends clear goals, delimiters, and starting with zero-shot for the described reasoning models rather than automatic step-by-step prompting. Scope this to the model family and current API. Keep required operational steps and user-facing explanations when the task calls for them.

### D2. OpenAI structured outputs

[Structured model outputs](https://developers.openai.com/api/docs/guides/structured-outputs)

Documents supported schema-constrained output and limitations, including possible content errors. Verify support, schema subset, refusal and truncation behavior. Structural validity does not establish factual correctness or complete business-rule compliance.

### D3. Anthropic prompting overview

[Prompt engineering overview](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview)

Starts from defined success criteria and empirical tests, and notes that not every failure is best solved by prompt engineering. Use current linked model-specific guidance rather than transferring tips across all providers.

### D4. Google prompting strategies

[Prompt design strategies](https://ai.google.dev/gemini-api/docs/prompting-strategies)

Recommends specific, varied, consistently formatted examples and experimentation. Its strong few-shot recommendation differs from D1's reasoning-model starting point: this is a reason to test, not to choose a universal example count.

## Engineering synthesis used in these Skills

Trace requirements to their owners; preserve conditions and exceptions; make consequential requirements inspectable; distinguish preferences from mandatory constraints; separate trusted instructions from source data; use code for deterministic checks; pair semantic review with evidence; bound repair; evaluate held-out outputs under comparable conditions.

These are explicit design judgments informed by the sources above. No source here establishes a universally best prompt, a guaranteed advantage for lists over prose, or a general “pink elephant” mechanism that warrants deleting all negative instructions.
