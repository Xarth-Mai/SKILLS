# Behavioral diagnosis: find and test the cause

Use when the failure repeats or spans prompts, model, context, tools, memory, runtime or evaluation. Do not assert a mechanism solely because it sounds plausible.

## Establish the failure

Recover intended and observed behavior, concrete triggering input, actual assembled messages, relevant model/version and settings, tool invocation/result, state before and after, the affected user task, and successful counterexamples. Distinguish **confirmed static mismatch**, **reproduced behavior**, **hypothesis awaiting a discriminating test**, and **preference**.

| Visible symptom | First discriminating question | Candidate owner |
| --- | --- | --- |
| “I remembered” but no stored memory | Was a write tool called and did storage confirm it? | Tools/runtime/state |
| Works in console, fails in product | Are roles, context, model, settings, tool schema and budgets equal? | Request assembly/runtime |
| Agent selects the wrong action | Are tools semantically distinct and are schemas usable? | Tool description/interface |
| Agent treats retrieved page as instruction | Was low-trust data promoted to authority? | Context boundary |
| Drift after long conversation | Was an invariant, source or user fact dropped or contradicted? | Context/memory |
| Duplicate transaction after timeout | Did retry reconcile actual outcome or use an idempotency key? | Runtime/transaction |
| Agent loops after completion | Can loop observe a confirmed result and stop? | Agent control |
| Persona apologizes unnaturally | Does phrasing, examples, recent context or model behavior trigger it? | Prompt/context/model |
| Candidate only scores better by LLM self-rating | Does an independent grader and held-out trace show progress? | Evaluation |

Test the earliest plausible owner with controlled fixtures or A/B; vary one factor when possible, keep model/runtime/budget constant, check successful prior cases, and treat unobservable facts as unknown. Fix at the owning layer, not by adding warnings to every prompt.

## Counterfactual project retrospective

For a later fix or adjustment, ask what could have been known at the first release: original triggering conditions, earliest relevant design contract, established prior art, smallest preventable test, and evidence that only emerged later. When testing agent foresight, give it a pre-fix snapshot **without disclosing the future repair**. Distinguish avoidable defects from legitimate market-discovered features. Capture reusable preventive checks only for generalizable causes.

## Evaluation gate

Use independent actual output/action checks, not word count, static prettiness or model self-certification. Confirm whether a shorter/more sophisticated instruction improved full task outcomes. A clean review is a valid outcome. If target-model evaluation is unavailable, report it as NOT RUN while completing safe authorized edits.
