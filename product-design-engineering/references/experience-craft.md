# Visual diagnosis and experience craft

Use for screens described as generic, cluttered, empty, misaligned, flat, heavy, or "functionally correct but not good enough". Do not equate elegance with more white space, more animation, uniform cards, or imitation of a platform showcase.

## Diagnose the visual reading order

At the **actual viewport and content**, identify the first three attention destinations, the intended next action, and the visual grouping of related information. Decide whether the problem is caused by competing emphasis, unclear sections, redundant decoration, narrow/wide measure, unbalanced density or incorrect hierarchy.

For each material correction, articulate the **relationship being clarified**: e.g. account total versus daily transactions; section title versus editable document; current selection versus optional details. A color, border, spacing or type adjustment is justified when it strengthens that relationship.

Check the entire viewport, not individual cropped components. A beautifully spaced component can make the whole screen feel sparse, force critical actions below the fold, or amplify redundant headers.

## Five practical lenses

1. **Hierarchy and grouping:** Is the primary content obviously primary? Do proximity, alignment, content width, type weight and contrast agree about group membership? More space *between* groups than *within* is a useful starting hypothesis, not a numerical mandate.
2. **Type and copy:** Is the type scale appropriate to language, density and reading intent? Can long CJK text and mixed Latin identifiers wrap? Are headings repetitious because the platform bar already gives the page name? Are numbers comparable and units correct?
3. **Geometry and optics:** Check icon glyph mass versus bounding box, visual rather than purely mathematical centering, baseline alignment, chevrons and badges, rounded corners, button heights, internal padding, and visual weight of symbols. Confirm that optical adjustments do not shrink interaction targets.
4. **Surfaces and chrome:** Decide where editorial whitespace suffices, where grouped content needs a mild surface, and where an actionable/status area needs a stronger boundary. Use a small coherent vocabulary of surfaces/borders/radii. For fixed navigation, compare same-color continuity against a subtle tonal or divider distinction in the *actual native platform*.
5. **Rhythm and density:** Inspect repetition of row separators, help text, timestamps, counters, placeholder decorations and persistent controls. Remove duplicate explanations or relocate optional detail before removing real substance. Inspect one record, realistic populated records and maximum plausible content.

### Surface choice by purpose

- **Editorial or narrative content:** readable column, intentional whitespace, light dividers; avoid enclosing every paragraph in nested cards.
- **Document, form or selected object:** a coherent content surface can establish where the object begins and ends, especially for reading, editing and Markdown.
- **State and operation:** make action boundaries and status legible; distinguish primary, secondary, destructive, disabled and pending states.

These are roles, not required components. Sometimes a single surface is enough; sometimes no border is needed. Keep product character while changing information structure.

## Design optical alignment rather than patching it later

Plan alignment during component design, not only after visual review:

- Identify the **perceived content center**: icon visible mass can differ from its SVG viewBox or container; letters, Chinese glyphs and numeral/unit pairs have distinct baselines and visual weight
- Determine the appropriate shared alignment mechanism (flex/grid alignment, consistent line-height, baseline pairing, icon sizing, internal padding) before adding local transforms or magic offsets. A centered box does not prove centered content
- Judge the full control or card in context, not only an isolated glyph. Check active and inactive states, loading label substitutions, accessibility text scaling, and touch target stability
- Check brand marks and functional icons **at their real smallest display sizes and crop shapes**. A richly detailed asset may require a separate simplified small-size variant rather than shrinking the full artwork
- If the runtime rendering still looks off, allow a small optical correction supported by before/after evidence, preferably in the shared component. Never accumulate per-page offsets to compensate for an unresolved shared source

After content deletion, inspect whether grouping and density still support the user's main task. Rebalance layout rather than reintroducing explanatory text or decorative blocks solely to fill white space

## Design review from symptom to fix

| Symptom | Check before changing | Likely minimal remedy | Disconfirming evidence |
| --- | --- | --- | --- |
| Feels messy although aligned | Too many equal-weight headings/actions/surfaces? | Reduce secondary weight, group by user goal, remove redundant chrome | Intended experts need simultaneous comparison |
| Feels empty | Oversized intro, weak content measure, missing grouping? | Rebalance page rhythm and task area | Editorial breathing room is intentional and tested |
| Feels dirty or noisy | Borders/shadows/colors used for every group? | Simplify surface roles and rely on proximity | Denser data truly needs visible row separation |
| Feels off-center | Actual glyph mass, mixed baselines, container padding? | Tiny optical adjustment after inspecting at target size | Geometry already looks balanced in runtime |
| Feels hard to operate | Control looks like passive caption, or hit box too small? | Increase affordance and active region | Existing whole-row interaction is accessible and discoverable |
| Feels generic | Brand/story disconnected from interaction and content? | Make hierarchy, imagery and motion purposeful | Prescribed neutral enterprise system is appropriate |

Do not report the rightmost column as a failure without observations. Give exact target selectors/components, state and viewport when possible.

## Craft is not a static screenshot

Inspect loading skeletons, partial updates, error overlays, sticky/fixed bars, keyboard, long text, scroll position, links, disabled and selected states. A beautiful hero screen cannot compensate for poor form errors or a hidden submit control. On data screens, verify that aggregation, zero baseline, numerical precision and missing values remain truthful.

Where motion is requested, visual composition and animation must agree: a chart entrance should not deform rounded caps, labels, hit targets or axis geometry; a dialog transition should preserve location and user control. Prefer restrained coherent motion; an inert static view can be the better design.

## Implementation review and judgment

Make the *smallest coherent set* of changes across related screens, not a set of isolated cosmetic patches. Reuse tokens, but allow purposeful variation between narrative pages, settings and records. If a design is subjective, present a comparison at matching content and ask for an actual preference only when consequential.

Before declaring a visual improvement, inspect a rendered before/after at matching viewport, theme, content and state; for platform chrome and native controls, use that platform's preview/device. Code review can identify risk but cannot establish how the layout looks to a user.
