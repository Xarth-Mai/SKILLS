# Risk-based verification

Pick checks based on change scope and risk; don't manufacture long test matrices for simple visual edits

## Compact acceptance matrix

| Dimension | Minimum meaningful evidence |
|---|---|
| User job | Primary journey completes, including expected feedback |
| Correctness | Data, validation, errors and state transitions match requirements |
| Continuity | Repeated action, interruption, navigation and async updates behave coherently where applicable |
| UI | Visual hierarchy, clipping, responsive/content extremes, optical issues checked on relevant screens |
| Accessibility | Semantic labels, keyboard/touch/focus, contrast, text scale, reduced motion as supported |
| Performance | No observed major jank/lag; measurable tests on critical interactions where possible |
| Integration | Contracts, callers, and existing shared components unaffected beyond intended scope |
| Evidence | Exact tests/manual steps performed, result, and what's not verified |

## Negative and edge cases

Use realistic values: extremely long but plausible names; missing optional fields; zero/one/many items; empty and maximum permitted inputs; localized strings; negative/large chart values; slow/failed requests; rapid operations; cancellation; unmount/navigation; dark/light themes; small/large displays; reduced motion

Derive limits from actual schemas and contracts. Feed adverse values through existing fixtures, props, or API mocks instead of editing markup to manufacture a failure. Use the component's real container width, not only the full viewport. Keep synthetic data and controls in tests or local development rather than shipping a debug toggle

For Web layout, inspect a representative narrow viewport and enlarged text/zoom, plus supported themes and input methods. A root-font change is not equivalent to browser zoom; report which was used. Compare useful before/after states and inspect screenshots when visual claims matter

For interaction, exercise failure, rapid reversal, cancellation, and reduced motion as applicable. Assert the semantic result, focus, and ability to continue, not merely that a CSS class changed. A headless run does not prove physical touch behavior, GPU smoothness, listening quality, or human usability

## Evidence and stopping

Keep package/static checks, automated behavior, rendered observation, real-device checks, and user acceptance distinct. For each material acceptance condition, record the command or steps, result, and evidence. Use `PASS` only for an executed check, `FAIL` for an observed violation, `BLOCKED` for a required check prevented by a concrete obstacle, and `NOT RUN` for an unexecuted check

Fix reproduced defects within the authorized scope and rerun their checks plus affected regressions. Stop when relevant checks pass and no unresolved finding requires another change. A missing tool limits the claim, not all useful work; report the remaining gap instead of inventing a pass

Local disposable previews and fixtures are suitable for development checks. Real business data, production, external side effects, and device acceptance require the applicable authorization. Review-only requests may use read-only inspection and non-mutating checks; they do not authorize code edits or adding test controls to the application

## Review questions

- Is the underlying user or product problem actually fixed, or merely restyled?
- Did the solution introduce more choices, motion, controls, dependencies or latency than the benefit warrants?
- Is the change consistent with the current product system without erasing intentional differences?
- Can a skeptical reviewer reproduce each important claim from explicit evidence?
- Are the highest-risk assumptions identified for later observation rather than being presented as facts?

## Report template (adjust size)

**Result** — finding or implemented change

**Reasoning** — high-impact issue and why the chosen solution fits

**Verification** — specific checks performed and outcomes

**Open items** — only consequential unknowns or unverified claims
