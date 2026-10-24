# Agent systems: professional design and diagnosis

Load for tool-using assistants, agentic loops, stateful tasks, side effects, handoffs, or tool-selection failures.

## Choose architecture by task

Start with direct model calls. Add retrieval and deterministic checking where warranted. Choose fixed workflows for known dependencies, routing for distinct intents, parallel execution for independent work, an evaluator/optimizer when there is a useful external criterion, and an adaptive agent loop only when tool observations determine the next step. Multi-agent designs need genuine context isolation or useful parallelism; they increase coordination and failure costs. Define explicit completion signals, effort/tool budgets and escalation conditions.

## Treat tools as model-facing interfaces

Distinct names and trigger descriptions should help agents choose correctly. Include precise parameters, units, supported enums, prerequisite identifiers, error/failure semantics, partial results, permissions and irreversible consequences. Prefer task-oriented tools and context-efficient responses with filters/pagination when appropriate. Validate schemas and authorization in code, not solely text. Tool response truth must determine claimed success.

## Model action lifecycle

Distinguish proposed, authorized, submitted, confirmed, failed, uncertain, interrupted and resumed. A timeout after a write does not establish failure; reconcile against authoritative state or use idempotency before any retry. For paid/external actions obtain the applicable approval; do not silently retry ambiguous commits/sends. Runtime owns durable state, rate and cost controls, audit and enforcement. Prompts guide decisions only within that actual capability.

## Trace and evaluation

Capture the assembled request, model configuration, tool specifications, decision/action with arguments, returned evidence, state changes, retries, limits, and final authoritative outcome. Locate first incorrect action and its causal context. Evaluate task completion, permission integrity, redundant calls, recovery from interruption, stop behavior, latency and token cost. Use dry-run fixtures for destructive actions. For context handoffs, pass durable artifact references and essential invariants rather than lossy summaries.

Sources: [Anthropic — Building effective agents](https://www.anthropic.com/engineering/building-effective-agents); [Anthropic — Writing effective tools for agents](https://www.anthropic.com/engineering/writing-tools-for-agents); [Anthropic — Multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system); [Anthropic — Demystifying evals for AI agents](https://www.anthropic.com/research/demystifying-evals-for-ai-agents).
