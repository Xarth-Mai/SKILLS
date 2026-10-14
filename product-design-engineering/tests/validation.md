# Migration and validation record

## Baselines and semantic migration

- Repository baseline: `7340cc0fc0c8ddc618a3c57a23c39fbe8c662868`, former `design-engineering` package
- Supplied baseline: `product-design-engineering.zip`, retained unchanged for paired probes outside the repository
- Authorized change: replace the former Skill with a product-to-QA entrypoint, preserve a cross-platform core and detailed Web guidance, install into Codex without committing or publishing

| Contract | Disposition and location |
| --- | --- |
| C1 | ZIP's adaptive modes retained in `SKILL.md`; platform portability explicit; optional companion integration retained |
| C2–C3 | Legacy scope and action boundaries retained in `SKILL.md`; small tasks bypass broad framing |
| C4–C5 | Legacy layout/type rules moved to `visual.md`, controls to `engineering.md`, gesture/interruption/preference rules to `motion.md`; shared-consumer and semantic completion constraints retained |
| C6 | ZIP evidence matrix strengthened in `verification.md`; package, runtime, rendered, device, and human evidence separated |
| C7 | Source map pins inspected upstream revisions; inherited Emil MIT notice and historical qualifications retained |
| C8 | New name replaces old directory and README entry; one installed discovery entry, no compatibility Skill |
| Chart composition | ZIP's unconditional shared-progress expectation replaced with a scoped positive-bar example and truthful-transition acceptance |
| Experience accumulation | Explicit maintenance request records a supported reusable case; ordinary tasks do not edit global instructions or memory |

## Executed checks — 2026-10-14

| Layer | Result | Evidence and scope |
| --- | --- | --- |
| Package | PASS | `python /home/lzzz/.codex/skills/.system/skill-creator/scripts/quick_validate.py product-design-engineering`; YAML/name/UI metadata, 21 internal Markdown links, standalone reference containment, unchanged inherited MIT notice |
| Static review | PASS | Independent `prompt-skill-review` pass against the ZIP and legacy package found no consequential static defects; this is not a behavioral guarantee |
| Read-only audit comparison | PASS, both variants | Separate agents inspected identical fixtures and reproduced persistence/close-handler failures with Node VM mocks, left all three application files byte-identical, and explicitly withheld browser/device claims; covers E6 and the read-only boundary of E1 |
| Build comparison | Executed | Separate agents repaired identical local Web fixtures under the same combined task covering E2–E5; each produced actual code, browser assertions, and a screenshot |
| Common browser checks, ZIP baseline output | 12/13 normal; 14/14 reduced | One normal-mode failure: the closing panel can receive focus during its exit; this was missed by that agent's own checks |
| Common browser checks, candidate output | 13/13 normal; 14/14 reduced | Persistence success/failure/retry, duplicate suppression, nonmodal focus, exit non-interactivity, reopen race, close completion, 320/375/768 px action reachability, and native form behavior |
| Evaluator negative control | Expected failures observed | Original unrepaired fixture passes only 2/13 normal and 2/14 reduced checks; the common evaluator detects its known persistence, timing, layout, focus, and label defects |
| Rendered observation | PASS, scoped | Parent inspected candidate before/after PNGs at 375×812: the original action area lies outside the visible viewport; repaired title wraps and both actions remain visible with existing colors |
| Local installation | PASS | Directory symlink from `~/.agents/skills/product-design-engineering` to the repository package; no prior same-name or legacy installation found in checked user/admin roots |
| Codex discovery | PASS | Codex CLI `0.162.1` app-server `skills/list`, `forceReload: true`: exactly one new entry, `scope: user`, `enabled: true`, expected canonical path and UI metadata, no matching errors |

The browser runs used `/usr/bin/chromium --headless --no-sandbox --disable-gpu --allow-file-access-from-files --virtual-time-budget=3000 --dump-dom`, separate temporary user-data directories, and `--force-prefers-reduced-motion` for the reduced variant. They read only disposable local pages. Initial sandbox runtime failures were resolved through the environment's approved escalation; they are environment failures, not failed Skill inputs

Codex discovery was queried through the installed CLI's generated protocol schema: `initialize`, `initialized`, then `skills/list` with the repository cwd and `forceReload`. The initial sandbox invocation could not initialize Codex's SQLite runtime; the approved local invocation succeeded. Discovery verifies host registration, not implicit model selection

## Comparison limits

Each variant had one independent build run and one independent audit run, with a fresh application copy and explicit Skill path. The agents inherited the parent model/settings with no override; exact model version, sampling, and total token budget were not exposed and are not claimed controlled. Both received the same task, fixture, tools, and time allowance. These are development probes, not untouched holdouts or a statistically meaningful benchmark

The candidate agent's own browser checks reported 12/12 normal and 13/13 reduced; the baseline agent reported 14/14 and 15/15. Those different self-authored suites are not comparable scores. The parent subsequently used one common evaluator on both actual outputs. No repair was made after those common results; the observed difference is a single-case result, not evidence of general superiority

E2 was exercised inside the combined task, not as a standalone proportionality probe. E3 repairs an existing placeholder rather than testing greenfield product discovery. E5 checks narrow layouts but not enlarged text/browser zoom. E7 chart behavior, E8 native-platform planning, the remaining legacy cases, and implicit positive/negative routing are NOT RUN

Real services, physical devices, full keyboard traversal, screen readers, browser zoom, GPU smoothness, native/game behavior, and human usability are NOT RUN. A local screenshot and DOM assertions do not prove those acceptance layers

## Raw evidence and reproduction

Session artifacts are in `/tmp/pde-evaluation`: immutable `baseline/` and `candidate/` Skill snapshots, `fixture/`, separate build/audit copies, exact `build-task.txt` and `audit-task.txt`, four agent reports, `static-review.md`, `common-check.js`, `common-results.json`, browser DOM outputs/screenshots, and `discovery.json`

`evidence.zip` in that directory bundles the small reproducibility artifacts without browser profiles. `evidence-manifest.json` contains hashes. These are local temporary evidence paths, not Skill runtime dependencies or a promise of permanent storage; retain the archive elsewhere if long-term replay is needed

For another comparison, copy the original fixture separately per variant, provide only the selected Skill and raw task (not expected outcomes), and inspect actual code/actions. The common-check HTML loads each app through an iframe and executes the same behavioral assertions. Keep first attempts distinct from any later repairs and record unavailable checks honestly

## Migration and rollback

The old `design-engineering` directory was removed only after byte-comparing it to the preserved baseline and validating the new package. README now uses the new entrypoint and source links; no compatibility Skill or second automatic entry was added. Existing unrelated Skills, repository instructions, branch, and Git index were not changed

To undo this uncommitted migration, preserve any subsequent edits first, recover the old package and README from the baseline revision, and remove only this new package and its matching user-level symlink. No commit, push, publication, or real project acceptance was performed
