# Evaluation protocol

Use for consequential rewrites, disputed techniques, production changes, or claims of better instruction following. Scale the experiment to the task and available authorization. This protocol is engineering synthesis informed by the sources below; its suggested workflow is not a benchmark result.

## 1. Separate the two evaluation layers

**Skill behavior:** Does the authoring/review Skill trigger appropriately, recover the user's contract, preserve semantics, produce a useful prompt or diagnosis, and report evidence honestly?

**Downstream behavior:** When the generated/revised prompt is used on the intended model, do its actual responses and actions satisfy the original task contract?

A Skill can produce attractive instructions that perform poorly. Test the second layer before claiming downstream improvement. Test packaging and discovery separately from both content judgments.

## 2. Freeze the test contract

Record the original brief, mandatory requirement IDs with applicability conditions, preferences, core task-quality criteria, permission boundaries, and accepted failure responses. Establish this independently of the candidate being scored. Preserve the rubric when comparing versions.

Specify for each check whether it is deterministic, semantic, or dependent on an action trace. A source-fidelity check needs the source. A “no detailed methods” check needs the intended boundary. A clean regex result alone cannot establish either one.

Define usable completion so empty answers, generic filler, unauthorized refusals, missing sections, or dropped hard constraints cannot earn a misleading pass. A legitimate failure response passes only on cases whose contract calls for it; report such cases separately from successful task completion.

## 3. Build a representative set

Include normal requests and the realistic failure surfaces: combined constraints, boundary meanings, permitted exceptions, missing input, contradictory input, misleading examples, long source material, source-embedded directives, tool failure, and output-budget limits. Select only relevant categories.

Test the language and domain used in deployment. English QA findings do not replace Chinese writing tests. Test combined requirements, not only one rule at a time.

Keep development cases separate from held-out evaluation. Once a case influences a rewrite or example, it is no longer an untouched holdout. Use intent-preserving paraphrases and harmless changes in names/order to probe brittleness without changing requirements.

The local JSONL regression cases are development probes for the Skills, not hidden tests. They contain briefs and expected checks, not model outputs. For routing cases, test normal discovery with descriptions available and no forced invocation; for authoring/review cases, invoke the corresponding baseline or candidate Skill. Add independently selected deployment cases for a real comparison.

## 4. Control the comparison

Keep model/provider and version, message roles, context assembly, available tools, reasoning configuration, sampling, output limit, and tool/retry budgets comparable. Record unsupported or unspecified settings rather than fabricating values. A fixed seed, when supported, does not prove complete determinism.

Change one main design hypothesis at a time when diagnosing causality. For a broad requested rewrite, compare the complete candidate and use targeted ablations to investigate regressions. Randomize or interleave runs when time-dependent service variation is relevant.

Run repeated independent attempts on representative cases where variability matters. Use a sample size appropriate to the decision and report counts and uncertainty; do not claim a universal minimum number of cases guarantees reliability. Obtain authorization before paid calls, sensitive-data transmission, or external side effects. Prefer fixtures or dry-runs for action tests.

## 5. Judge with evidence

Run exact validators first when the property is deterministic: schema, required keys, count semantics, enumerated values, identifiers, and actual tool-call order. Keep refusal, truncation, transport, and parsing failures visible; classify their cause rather than silently excluding them.

For semantic checks, give the judge the original task contract, source material, candidate artifact, and relevant action trace. Request `pass`, `fail`, or `unknown` for each applicable requirement, with a short evidence span or concrete explanation. Do not request private chain-of-thought or accept a bare global score.

Hide candidate identity and claimed improvements where feasible. For pairwise quality judging, vary response order and inspect disagreements. Calibrate semantic checks on human-reviewed examples and manually adjudicate consequential or ambiguous results. A second model can share the first model's blind spots; independence is not guaranteed by a different call.

Check evaluation machinery itself with known compliant and noncompliant fixtures. A validator must not accept blank output, count a skipped check as passed, or silently change the rubric.

## 6. Report the metrics separately

Let `N` be the number of scheduled comparable attempts. Each attempt is evaluated against its applicable mandatory requirements and core task-quality check.

- **Whole-request first-attempt pass:** number of first outputs that complete the task usefully and pass every applicable mandatory check, divided by `N`.
- **Per-requirement pass:** passes divided by applicable attempts for that requirement; report failures and unknowns beside it. Show both numerator and denominator.
- **Severe violations:** count and rate of predefined unacceptable events, including unauthorized actions or fabricated evidence when those violate the contract.
- **Post-repair success:** success after the same bounded repair policy, reported separately from first-attempt performance and with repair counts.
- **Cost and coverage:** input/output usage, tool calls, total latency, truncations/errors, number of cases, and which languages/tasks/context lengths were tested.

`unknown` is not `pass`. Report the unknown rate and, when useful, lower/upper bounds instead of treating uncertainty as proven failure or success. Withheld/cancelled execution must be visible and must not inflate the score. Predefine handling of infrastructure failures and report end-to-end reliability alongside any model-only diagnostic rate.

Do not equate an average of requirement pass rates with whole-request compliance. Do not compare one candidate's best-of-many result with another's first attempt. Keep quality floors so omission is not rewarded. Give paired win/loss examples and confidence intervals or clearly acknowledge when sample size supports only exploratory findings.

## 7. Repair, stop, and promote

Return a localized failure record: requirement ID, output location, expected property, observed evidence, and allowed repair scope. Change the affected portion while preserving verified content. Recheck the changed and dependent requirements, then revalidate the final whole artifact. Never replay external side effects merely to repair wording.

Stop at the configured attempt/cost bound or when no justified improvement remains. Keep unresolved results explicit and follow the contract's failure behavior.

Promote only within the tested scope: useful task quality is retained, mandatory compliance meets the agreed gate, severe violations have no unacceptable regressions, and cost stays within budget. Predefine acceptable tradeoffs instead of selecting a favorable metric afterward. No observed violations in a finite set is not a guarantee of zero future violations.

## Suggested run record

Adapt this structure to the existing harness; do not add a framework just to match the example.

```json
{
  "case_id": "case-001",
  "variant": "baseline",
  "attempt": 1,
  "model": "record actual model/version",
  "settings": {},
  "prompt_version": "record actual hash or commit",
  "artifact_path": "record actual saved output",
  "tool_trace_path": null,
  "checks": [
    {"id": "R1", "applicable": true, "status": "unknown", "evidence": "not evaluated"}
  ],
  "task_quality": "unknown",
  "repair_attempts": 0,
  "usage": null,
  "latency_ms": null
}
```

This is a schema illustration, not an execution record.

## When model execution is unavailable

Complete source review, semantic-preservation mapping, schema/link checks, and a prioritized test plan. Mark static, manual, and empirical checks separately. Do not report imagined rates, represent development probes as executed tests, or describe the candidate as universally best.

## Primary-source anchors

Checked 2026-09-26:

- [IFEval, 2023](https://arxiv.org/abs/2311.07911): verifiable instruction evaluation.
- [InFoBench, Findings ACL 2024](https://aclanthology.org/2024.findings-acl.772/): decomposed requirement judging.
- [DeCRIM, Findings EMNLP 2024](https://aclanthology.org/2024.findings-emnlp.458/): constraint-aware critique/refinement; not equivalent to ungrounded self-approval.
- [Large Language Models Cannot Self-Correct Reasoning Yet, ICLR 2024](https://arxiv.org/abs/2310.01798): limitations of intrinsic correction in the evaluated reasoning settings.
- [POSIX, Findings EMNLP 2024](https://aclanthology.org/2024.findings-emnlp.852/): intent-preserving prompt sensitivity, distinct from correctness.
- [Anthropic prompting overview](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview): success criteria and empirical tests before optimization.
