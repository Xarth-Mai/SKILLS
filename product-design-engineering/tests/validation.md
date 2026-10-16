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

## Second-pass overlay integration — 2026-10-14

Baseline: `464bd84d8929dace8aae4a9889f3c3add29c06c0`; source: the user-supplied `product-design-engineering-update.zip`. This section records the subsequent overlay integration; the earlier migration and behavioral results above describe the previous revision

Applied the replacement entrypoint, four new references and ten design-diagnosis probes. Retained existing references, tests, agent metadata, attribution and license files. The archive-root `UPGRADE.md` was read as application guidance and was not added to the repository

Preserved C1–C8 through the revised entrypoint and retained references. Added cognitive/visual diagnosis, current-revision checks and platform-specific evidence guidance. Static review restored the original explicit product/content/API preservation and conflict-reporting rule; the supplied overlay otherwise remains intact

| Layer | Result | Evidence and scope |
| --- | --- | --- |
| Package | PASS | `python /home/lzzz/.codex/skills/.system/skill-creator/scripts/quick_validate.py product-design-engineering`; frontmatter, naming and unfinished-placeholder checks |
| Local integrity | PASS | Python assertions verified 38 package-local Markdown links and standalone containment, plus byte-identical preservation of 29 tracked files outside the four integration targets; `git diff --check` passed |
| Static review | PASS, scoped | `prompt-skill-review` comparison against the baseline and supplied overlay found no remaining consequential static conflict after restoring the preservation rule; this does not establish behavioral equivalence or improvement |
| Installed path | PASS, scoped | Existing `~/.agents/skills/product-design-engineering` symlink resolves to this checkout; host discovery reload and implicit routing were NOT RUN |
| Behavioral comparison | NOT RUN | Existing E1–E8/legacy cases and new D1–D10 probes were not executed for this overlay; previous browser/model results do not validate the new entrypoint |
| External provenance | NOT RUN | New research/source-check claims originate in the supplied archive; external pages and license claims were not independently reverified during integration |

The committed baseline is the rollback source for the replaced entrypoint; preserve any later edits before restoring it or removing only the five resources introduced by this overlay


## Pattern-first incremental revision — 2026-10-16

Baseline: `464a5875999cb89a327b57326d8d0490d42360de`; candidate source: the user-supplied `product-design-engineering-proposal.zip`. Scope: local instruction changes and static validation only; behavioral A/B evaluation was explicitly excluded

Integrated pattern recognition into the existing diagnosis stage, retained the original routing exclusions and metadata, added the conditional problem-family reference, and updated the Skill README. Added the two agreed general rules to `THEAGENTS.md`; no duplicate English guidance or archive-root delivery files were installed

Reworked P1–P8 into separate symptom-only task inputs, fixture requirements and evaluator criteria. P3 distinguishes existing server protection, authorized server implementation and client-only mitigation. These remain specifications; no runnable fixtures or model results were produced

| Layer | Result | Evidence and scope |
| --- | --- | --- |
| Package | PASS | `python /home/lzzz/.codex/skills/.system/skill-creator/scripts/quick_validate.py product-design-engineering` returned `Skill is valid!` |
| Local integrity | PASS | Python path assertions checked all 42 package-local Markdown links for existence and package containment; byte comparison against HEAD confirmed 34 tracked files outside the four planned existing-file targets unchanged |
| Whitespace | PASS | `git diff --check`; new reference and probe files also checked for trailing whitespace and final newline |
| Static semantic review | PASS, scoped | Same-agent `prompt-skill-review` pass over the full diff and new resources checked proportionality, hypothesis versus evidence, shared-rule authorization, original routing exclusions and evaluation leakage boundaries; no outstanding high-impact static findings |
| Review corrections | Applied | Preserved the original description exclusions instead of the archive's broader trigger; scoped the added review lens to nontrivial changes; removed the stale four-perspective count; aligned the reference's backend exclusion with the entrypoint; split P3 by existing mechanism and authorization |
| Behavioral comparison and routing | NOT RUN | P1–P8, unchanged passing cases, independent holdouts, model A/B comparisons and host discovery were not executed for this revision; historical results above do not validate it |
| External source validation | NOT RUN for the pattern catalog | Candidate guidance is adapted from the supplied archive; no new dated HIG claim, source quotation or claim of comprehensive external verification was added |

No commit, push, installation change or real product acceptance was performed. Static consistency does not establish improved recognition, first-attempt correctness or behavioral equivalence
