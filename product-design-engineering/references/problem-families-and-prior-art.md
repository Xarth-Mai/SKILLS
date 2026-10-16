# Problem families and prior art

Load this reference only when a user-facing product or design-engineering problem is cross-cutting, unfamiliar, or likely to recur. This is a *recognition aid*, not a mandatory pattern catalog and not a dependency on any specific framework

## Recognize the class, not just the symptom

1. State the observed failure or friction and its evidence. Separate user-visible symptoms from causes and preferences
2. Name the underlying problem family in plain terms; a formal pattern name is useful but optional. List one or two plausible alternatives when evidence is insufficient
3. Inspect the repository for current owners, abstractions, specifications, tests, framework versions, and callers. Determine whether it already solves part of the problem and why that solution did not apply
4. Identify relevant established approaches from first-party platform or framework docs, standard libraries, professional design guidance, and reputable maintained implementations. Search external sources when needed and permitted; follow the host requirements for current or uncertain facts. Check publication/version, assumptions, limitations, and licensing before carrying over code or prose
5. Compare *fit*: does the pattern protect the actual invariants? Does it apply on this platform, under this data consistency model, with this product tone, at the expected scale? Do the benefits exceed its dependencies and complexity?
6. Choose the smallest coherent implementation and an observable acceptance check, including a counterexample. If a shared convention is warranted, identify the project's single authoritative home and keep code, specs, and tests aligned

Do not invent source-backed endorsements or pretend to have verified an external page when only drawing on prior knowledge. A pattern is a candidate solution, not automatic proof of correctness. Avoid catalog searches for straightforward changes that already have an unambiguous local idiom

## Recognition prompts and established approaches

| Symptoms and failure family | Useful solution families to evaluate | Common misapplication |
| --- | --- | --- |
| Read-only screens flash loading, forget data on tab change, mislabel network delay as empty | Cache-as-data, stale-while-revalidate, background revalidation, query keys, cache invalidation, distinct `not fetched` vs confirmed empty | Treating cached balances, permissions, or transactions as authoritative; bringing React-only dependencies into other runtimes |
| Many booleans describe incompatible UI or business states | Explicit state models, state machines, valid transitions, invariant checks | Building a heavyweight state-machine framework for a one-off binary toggle |
| Repeated clicks, retries, or network uncertainty create duplicate actions | Idempotency keys, server-confirmed success, transaction boundaries, retry backoff | Believing disabling a button ensures backend idempotence |
| Requests race or old responses overwrite new selections | Request identity, cancellation/generation guards, latest-intent policy, optimistic concurrency | Cancelling an unrelated legitimate operation; treating all old work as invalid |
| Multiple errors flood a screen, partial content disappears | Error ownership, aggregation/deduplication by cause, scoped recovery, last-known-good preservation | Hiding distinct failures; silently replacing failure with zero or empty state |
| Screens exhibit inconsistent layout, controls, tokens and motion | Existing platform conventions, semantic design tokens, reusable layout primitives, component contracts, design-system governance | Enforcing visual sameness when flows have meaningfully different needs |
| The interface makes common tasks confusing or technically framed | Information architecture, progressive disclosure, recognition over recall, defaults, familiar interaction patterns, error prevention and recovery | Hiding essential costs, permissions or advanced capability to make a screen look simpler |
| Data writes or multi-step workflows become inconsistent | Transactions, optimistic concurrency, outbox/saga where justified, reconciliation | Choosing distributed workflow machinery for a simple local update |
| Performance degrades under real workloads | Measure critical path, caching, batching, virtualization, backpressure, observability | Adding memoization or a cache without proving the actual bottleneck |
| Recovery after crashes or network failures is unreliable | Retry policy, state persistence, idempotence, timeouts, circuit breakers when relevant | Retrying non-idempotent operations blindly or masking permanent failures |
| Security or privacy assumptions spread across UI and APIs | Threat modeling, least privilege, authorization boundaries, OWASP-style verification | Using UI visibility as an authorization boundary |

These examples can be relevant in product-led engineering. For backend-only tasks, the general engineering process or specialist Skill owns the work; this Skill should not broaden its implicit trigger merely because a code pattern exists

## Source choice and local truth

The project's accepted decisions, current implementation, versions and data contracts decide feasibility. For general expertise, prefer the applicable primary source: platform human-interface guidelines; language/runtime and framework documentation; security standards such as OWASP; reliability guidance such as established well-architected frameworks; well-documented architecture and concurrency patterns; and tested in-repository practice. Community guidance can inspire alternatives, but is not a substitute for compatibility or evidence

Apple HIG is authoritative for Apple-platform conventions and often informative elsewhere, but does not automatically override WeChat mini-app APIs or a web product's established behavior. Similarly, TanStack Query/SWR explain a useful client-cache model without obligating a React dependency or making stale data appropriate for high-trust transactional states. Prefer to adapt a model when the library itself does not fit

## Project-level consolidation

When a defect reveals a recurring policy gap, capture **the decision**, not another long incident history:

- One owner: the existing canonical design/architecture/interaction specification (or a new one only if none exists)
- One contract: problem category, where it applies, exceptions, shared behavior, and source-of-truth boundaries
- One implementation: the smallest appropriate reusable mechanism, without premature abstraction
- One proof: a representative automated or runtime check and a counterexample for incorrect application

Correct or deprecate conflicting older rules at their owners when in scope. Avoid creating parallel pattern catalogs, duplicate components or detached task notes that later agents cannot discover. For design-only work, identify the required changes; do not edit the repository without authorization
