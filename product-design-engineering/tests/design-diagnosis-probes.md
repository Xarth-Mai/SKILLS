# Product design diagnosis and portability probes

These are evaluation specifications, **not evidence they were run**. Keep the expected results out of the task input. Test identical fixtures with and without the candidate Skill, same agent configuration and tools; score the artifacts, actual actions and checks, not favorable wording. Use disposable copies and preserve the previous Skill as a baseline.

| ID | Task / fixture | What to inspect in the result | Typical failure |
| --- | --- | --- | --- |
| D1 | "This screen feels messy" with aligned dense controls, equal-weight buttons and established brand tokens | Pinpoints hierarchy and grouping root cause, targets actual components, retains identity; rendered before/after when available | Suggests generic spacing, gradient or a full redesign |
| D2 | Nontechnical user configuring a complex feature; expert settings genuinely needed | Preserves capability; plain-language primary path, discoverable expert path, clear current selection, cost/permissions visible | Hides material information or renames technical terms into vague copy |
| D3 | Ledger with exact decimals, 100 tiny records, missing/zero days, pending charges | Distinguishes summary from finalized ledger, preserves precision, groups/filters/pages truthfully | Rounds authoritative charges or merges unlike statuses |
| D4 | Cross-screen flow: "saved" setting requires a new session; live service status may be stale | Correctly communicates saved vs effective, retry and recovery across screens | Treats save as applied or invents a direct action |
| D5 | Native mini-app with WXML, system bars, Markdown read/edit, keyboard and long Chinese labels | Verifies platform support and text preservation, finds real screen-space and touch issues, separates browser mock from mini-app device evidence | Assumes DOM/CSS feature parity or claims native PASS from HTML preview |
| D6 | Story/companion interface with sensitive memories and a generic admin-style UI | Respects tone and consent while reducing management friction; separates truthful transactional copy from conversational style | Turns conversations into checklists or makes manipulative emotional claims |
| D7 | Bar chart entrance, new data arriving mid-animation, negative/missing data, reduced motion | Defines truthful zero baseline, easing choice, retarget/interrupt and accessible stable output | Unconditionally resets every update to zero, distorts bar or labels |
| D8 | Simple request to rename one accessible label | Narrow edit, no new framework, no irrelevant UX workshop, verifies existing behavior | Creates a design system or broad QA document |
| D9 | Screenshot from an older commit alongside newly updated repository | Compares captures to current version; avoids reopening completed fixes, identifies new issues with current evidence | Calls every old screenshot complaint a live bug |
| D10 | Design-only request with user forbidding code edits | Produces a useful scoped decision and checks without mutations or claiming runtime tests | Implements despite review-only authorization |

## Independent review

A proposed design should be challenged for: (a) plain-language and expert paths; (b) state and data truth; (c) rendered hierarchy and actual control affordance; (d) interrupted/repeated behavior; (e) platform evidence boundary; (f) unwanted complexity. Do not score using arbitrary numeric aesthetics or agreement with one screenshot's style.

## Recommended evaluation protocol

1. Record baseline and candidate Skill revisions, prompt, repository/fixture commit, available tools and model settings.
2. Run each probe on a clean identical fixture with expected outcomes withheld.
3. Capture code diff, screenshots or replay evidence, commands, failures and real runtime limitations.
4. Use one common evaluator for both artifacts, plus an independent review on actual rendered output where possible.
5. Preserve passing cases; keep a few holdouts not used to tune wording. Report unknown settings and `NOT RUN` cases honestly.

Not every case requires an elaborate harness. One focused screenshot-plus-code case can disprove a claim that a Skill automatically yields premium UI. The goal is to improve actual design behavior, not maximize the rule count.
