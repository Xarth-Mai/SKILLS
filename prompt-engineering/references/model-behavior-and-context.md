# Model behavior and context engineering

Load when model-specific prompt choices, retrieved evidence, long-context use, memory or multi-turn agent state can affect the result.

## Establish the actual model input

Inspect roles and instruction hierarchy; template expansion, injected examples, retrieval, tool descriptions and outputs; output parser; token allocation and truncation; model ID/version, thinking/effort and generation limits. A template alone is not the input the model sees. Consult current target-model documentation before claiming the effects of a prompting technique.

## Choose by mechanism

| Symptom | Intervention candidates | Required evidence |
| --- | --- | --- |
| Conditional requirements are missed | State condition, alternative and exception unambiguously | Whole-task adherence, including allowed exceptions |
| Output interface breaks | Compatible schema, exact field/enum requirements, defined failure path | Parser/schema checks plus semantic correctness |
| Pattern of task mistakes | Targeted, varied examples without accidental rules | Held-out generalization; cost |
| Source data overrides instructions | Actual role/trust separation, provenance, isolation of examples/data | Injection resistance in assembled requests |
| Long-context drift | Select/retrieve relevant evidence, preserve decisions and source references, compact carefully | Multi-turn traces, recall and fidelity |
| Inconsistent persona | Separate stable personality, learned user facts, recent chat and immediate cues | Diverse, realistic conversations |
| Thinking or tool choice differs by model | Use supported controls and model-specific guidance | Target-model quality, latency and failure modes |

Do not generalize “always use XML,” “always use examples,” “always repeat,” “always show chain of thought,” or “always keep prompts short.” These are hypotheses with scope and tradeoffs, not universally valid commands. Provider guides may disagree because their models and experimental settings differ.

## Assign context ownership

Stable instructions specify invariants; task context supplies the user's current intent; retrieved text provides attributed evidence, not operational authority; tool results communicate confirmed state; memory preserves selected durable facts with timestamps, provenance and update/deletion semantics. Control duplication, relevance, staleness and visibility. Long-run compaction should retain critical constraints, exact identifiers, decisions and recoverable source references. A summary of an action is not proof it succeeded.

Test with the same underlying task before and after a context change; check where source evidence was lost, stale facts won, previously passing cases regressed, or costs changed. Prefer retrieving useful evidence to stuffing every document into a prompt.

Sources: [Anthropic — Effective context engineering for AI agents](https://www.anthropic.com/research/effective-context-engineering-for-ai-agents); [Anthropic — Prompting best practices](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices) (living, model-dependent); [Anthropic — Multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system); [Evidence and limits](evidence.md).
