# Product outcomes, ambition, and commercial judgment

Load for product direction, new user journeys, positioning, acquisition, activation, retention, monetization, pricing, launch decisions, or recurring failure analysis. A small localized edit normally uses existing conventions without this reference.

## Raise the level of the problem

A requested feature, screen, campaign, or report is a proposed means, not automatically the real goal. Identify the user/job, moment of need, existing alternative, expected change in behavior, and the next outcome beyond delivery. Separate **the authorized task** from **a potentially better strategy**: carry out a clear authorized task; when a materially better direction falls outside scope, make the tradeoff visible without silently replacing the user's objective or taking new external actions.

For meaningful work, ask what success would look like *after use*: discoverability, first value, repeated value, trust, voluntary payment, sustainable delivery. Trace only the portions relevant to the decision. A product may be a business, an internal service, a public good, or an artistic tool; do not impose monetization where it does not belong. For a commercial product, do not confuse feature completeness, engagement, model tokens, conversion, revenue, margin, and long-term user value.

Recognize the strategic options before committing to implementation: retain current behavior; remove friction; improve quality/reliability; change positioning, channel, offer, or price; add the requested capability; or run a small test that resolves a pivotal unknown. Prefer the action with the largest *credible* impact on the desired outcome under the constraints, rather than the most impressive-looking deliverable.

## Use genuine professional methods, not expert vocabulary

Match the question to the evidence and instruments a strong practitioner would actually use:

- **Product and users:** observed workflows, target segments, alternatives and substitutes, interview/task observations, complaint clusters, JTBD, actual first-use paths. Do not invent interviews or infer an entire market from a few anecdotes.
- **Engineering and service quality:** current source, contracts, dependency/runtime versions, failure logs, tracing, reproducible fault injections, platform and device evidence, incident and commit history.
- **Distribution and growth:** actual channel reach, qualified visits, acquisition attribution, activation, repeat use, channel costs; distinguish attractive creative from acquired, activated users.
- **Finance and pricing:** real payments, refunds, payment fees, model/provider bills, hosting and delivery costs, support, credit liabilities, willingness-to-pay evidence. A points ledger is not cash revenue; a credits-based gross margin estimate is not accounting profit.
- **Safety, trust, and law:** applicable local rules, service scope, disclosures, consent, privacy and age requirements, user controls, failure recovery. Verify current authoritative requirements when they affect launch or promotion; do not claim compliance from a mock or self-attestation alone.

Seek the earliest/rawest valid evidence instead of relying only on dashboards or executive summaries; reconcile differing time ranges, populations, identities, attribution and missingness. Critically test the user's and agent's own assumptions. Use specialized Skills, tools, or disciplines when they provide a real method or evidence—never a theatrical expert persona. Explicitly say which source, method, and outside check would overturn a recommendation. A source that cannot be accessed remains unknown, not zero or false.

## Diagnose the real constraint

For a commercial lifecycle, look along **reach → first value → recurring value → retention → voluntary payment → sustainable contribution**, while inspecting relevant quality, trust and compliance guardrails. This is a causal hypothesis map, not a mandatory funnel or fixed instrumentation schema. Product shape determines the actual journey, and the main bottleneck must be measured before claiming it.

- Define each rate's numerator, denominator, cohort, timestamp, and observation window. Distinguish observed behavior from causal inference. Segment only when sample size and exposure justify it.
- If a valid baseline exists, examine the biggest credible loss or unmet value and its causes before selecting an intervention. If not, prefer the least invasive observation or controlled task test that can discriminate the leading hypotheses.
- For pricing, model cost-to-serve and customer-perceived value together. Report *actual cash* separately from credits charged, model usage, gross bookings, refunds, user balances, and noncash subsidies. Include variable provider, payment, infrastructure and support costs when known; do not label a partial spread as profit.
- Favor a sustainable relationship with the user. Do not optimize for compulsive use, manipulated attachment, concealed charges, deceptive scarcity or other harmful behavior; stronger user autonomy and trust are product advantages, not merely growth constraints.
- Model uncertainty honestly: missing traffic/source attribution or small cohorts cannot prove a channel, feature or price is good or bad. Prefer hypotheses and a useful next test to invented ROI, conversion lifts or significance.

A minimal decision can be stated as: **desired outcome; best evidenced constraint; options and tradeoffs; chosen intervention or experiment; success/guardrail signals; outside validation; authority needed for launch.** For tiny edits, this can remain implicit.

## Anticipate revisions without inventing a roadmap

Before substantial Design/Build, imagine reading the next three months' commits. Separate three *different* questions:

1. **Predictable fixes:** Which known contracts, states, failures, races, permissions, idempotency rules or real platform constraints could be addressed now? Name the exact early test or source that would catch them.
2. **Predictable adjustments:** Which language, information density, interaction, rendering, content and model-behavior defects could be identified from representative users, data, devices or independent model traces before shipping?
3. **Potential new features:** Which capabilities are necessary for today's complete user outcome, and which depend on future evidence? Design the necessary path now; deliberately defer speculative breadth without building elaborate speculative infrastructure.

Avoid hindsight bias. A problem was preventable only if the relevant evidence, feasible checks and reasonable tradeoff were available *at the earlier point*. Unexpected market learning is legitimate product iteration, not proof that the first version failed.

When authorized to improve the Skill, evaluate foresight using a historical checkout whose subsequent fixes are hidden from the agent. Ask it to identify failure classes, evidence, and early tests *before revealing later commits*. Compare baseline and candidate on the same fixtures; include small-task, compliance, data-gap and formerly passing holdouts. Outcome changes require independent behavior or market evidence; static prose changes alone prove nothing.

## Validate outcomes with an outside judge

Match the validator to the assertion: unit/race tests and failure injection for code behavior; actual target runtime/device for UI and payment flow; traces plus independent grading/human feedback for model behavior; cohort and cash/provider records for commercial outcomes. A checkout that compiles does not prove activation, a page click does not prove conversation delivered, and a high token/engagement count does not prove user value.

Record what has been observed, what is only inferred, what is blocked by unavailable data, and the next discriminating test. If the requested work includes a plan only, do not claim growth or quality improvements are realized. Once the scope is delivered, recommend a bounded follow-up observation; never assume authority to deploy or continuously monitor.

## Source and adaptation note

This reference independently operationalizes *Speed, Altitude, Depth, Range* from Felix Rieseberg, [How to be more ambitious: A tutorial for humans with models](https://felixrieseberg.com/how-to-be-more-ambitious-a-tutorial-for-humans-with-models/) (13 October 2026). The principles here are adapted for product development, business evidence, authorization, and safe evaluation; no source prose or external Skill is imported.
