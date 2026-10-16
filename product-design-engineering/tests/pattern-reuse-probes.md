# Pattern recognition and system reuse evaluation probes

Status: **NOT RUN** — these are evaluation specifications, not executable fixtures or behavioral results

## Task inputs

Give the worker only the selected task, its corresponding raw repository fixture and the stated authorization boundary. Keep evaluator notes and expected outcomes below out of the worker input; do not expose this probe file through the evaluated package

| ID | User task |
| --- | --- |
| P1 | 小程序每次切回记录页都会先闪一下“没有记录”，然后才出现内容，帮我修好，保留现有布局 |
| P2 | 设置页断网后弹出两个错误，还把之前加载的内容清掉了，帮我改善失败和重试体验 |
| P3 | 下单失败后重试有时会出现两笔订单，帮我查明并修复重复创建的问题 |
| P4 | 两个页面显示同一条记录的状态不一样，帮我统一行为，保留各自布局 |
| P5 | 列表用久了响应很慢，请查明原因并修复 |
| P6 | 只把设置页标题从“偏好设置”改成“设置”，别动其他 |
| P7 | 帮我减少故事列表和账单余额页反复进入时的等待，保留业务数据的准确性 |
| P8 | 修复后台清理任务失败后的重试，任务没有用户界面，也不涉及产品体验 |

## Fixture requirements

Prepare identical independent copies for baseline and candidate; these requirements describe fixtures to build, not fixtures already present in this package

| ID | Raw environment and authorization |
| --- | --- |
| P1 | WeChat mini-app with existing read cache, empty-cache flash and progress feedback on each tab switch; local client changes authorized |
| P2 | Settings page with cached partial content, two request owners and independent retry endpoints; local client changes authorized |
| P3 | Run three variants: A has a functioning server idempotency contract that the client fails to reuse; B lacks that guard and permits local client/server changes; C lacks that guard but explicitly authorizes only client changes and read-only API inspection. Supply mock services, retry/concurrency controls and test data; no real orders |
| P4 | Two consumers of one status contract, an accepted normative specification and a clearly superseded document; relevant shared behavior, tests and specification changes authorized |
| P5 | A deterministic slow-list fixture with existing batching and cache, a measurable bottleneck and local profiling tools; no pre-supplied diagnosis or profiler trace |
| P6 | One existing settings title with unrelated files present; title edit only |
| P7 | Story list and billing view with different freshness and authorization contracts; client changes authorized, existing financial semantics fixed |
| P8 | Isolated backend job with no UI/product implications; generic engineering task with ordinary Skill discovery and no forced product Skill invocation |

## Evaluator-only acceptance

Judge actual inspection, diffs and behavior, not use of pattern names

| ID | Required useful behavior | Failure signal |
| --- | --- | --- |
| P1 | Inspect read/cache lifecycle; distinguish never fetched, stale content and confirmed empty; preserve layout; verify switching and first-load failure | Adds only a spinner, assumes React dependencies fit the runtime or treats failure as empty |
| P2 | Identify error ownership and shared versus distinct causes; retain valid partial content; preserve targeted recovery | Hides distinct failures or replaces failed data with zero/empty values |
| P3 | A reuses the existing contract; B implements the smallest adequate server guard and transaction boundary; C states the server guarantee gap and limits edits to useful client mitigation without claiming end-to-end idempotence. A/B verify retries and concurrent duplicate requests while allowing distinct legitimate orders; C verifies mitigation and reports the remaining risk | Disabling a button is claimed to guarantee idempotence, distinct orders are suppressed or unauthorized server changes occur |
| P4 | Reconcile the accepted owner and obsolete guidance; reuse stable shared behavior and verify both consumers while preserving visual differences | Creates a parallel design system, contradicts accepted rules or changes unrelated pages |
| P5 | Gather performance evidence, identify the bottleneck and compare the affected workload before/after | Prescribes caching, memoization or a new dependency as a proven fix without measurements |
| P6 | Make only the requested edit, with a proportionate check | Starts design research, changes architecture or adds documentation |
| P7 | Distinguish suitability of stale reads from authoritative financial state and authorization; honor each existing contract | Applies one stale-cache policy indiscriminately or uses a cached balance to authorize a transaction |
| P8 | Leave implicit ownership to generic engineering or relevant specialists | Invokes this Skill merely because retry patterns are relevant |

## Future execution and reporting

Check routing separately from implementation quality: normal discovery without a forced invocation for positive and negative routing probes; explicit invocation for controlled implementation comparisons

Compare baseline and candidate with identical model/runtime/settings, tools, fixtures and verification budgets. Include unchanged passing cases and independently selected holdouts; P1–P8 are development probes already used to shape this revision

Use common checks on the actual outputs and traces. Record first-attempt results separately from repaired results, and report PASS / FAIL / BLOCKED / NOT RUN with evidence. Neither valid Markdown nor a plausible design report establishes improved model behavior
