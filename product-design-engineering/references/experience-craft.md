# Visual diagnosis and experience craft

Use for visual hierarchy, density, alignment, and product-expression problems. Evaluate composition against the intended reading order, task, and product character

## Diagnose the visual reading order

At the **actual viewport and content**, identify the first three attention destinations, the intended next action, and the visual grouping of related information. Decide whether the problem is caused by competing emphasis, unclear sections, redundant decoration, narrow/wide measure, unbalanced density or incorrect hierarchy.

For each material correction, articulate the **relationship being clarified**: e.g. account total versus daily transactions; section title versus editable document; current selection versus optional details. A color, border, spacing or type adjustment is justified when it strengthens that relationship.

Check the full viewport as well as individual components: useful density, action visibility, and repeated chrome

## Five practical lenses

1. **Hierarchy and grouping:** Is the primary content obviously primary? Do proximity, alignment, content width, type weight and contrast agree about group membership? More space *between* groups than *within* is a useful starting hypothesis, not a numerical mandate.
2. **Type and copy:** Is the type scale appropriate to language, density and reading intent? Can long CJK text and mixed Latin identifiers wrap? Are headings repetitious because the platform bar already gives the page name? Are numbers comparable and units correct?
3. **Geometry and optics:** Check icon glyph mass versus bounding box, visual rather than purely mathematical centering, baseline alignment, chevrons and badges, rounded corners, button heights, internal padding, and visual weight of symbols. Confirm that optical adjustments do not shrink interaction targets.
4. **Surfaces and chrome:** Decide where editorial whitespace suffices, where grouped content needs a mild surface, and where an actionable/status area needs a stronger boundary. Use a small coherent vocabulary of surfaces/borders/radii. For fixed navigation, compare same-color continuity against a subtle tonal or divider distinction in the *actual native platform*.
5. **Rhythm and density:** Inspect repetition of row separators, help text, timestamps, counters, placeholder decorations and persistent controls. Remove duplicate explanations or relocate optional detail before removing real substance. Inspect one record, realistic populated records and maximum plausible content.

### Surface choice by purpose

- **Editorial or narrative content:** a readable column, intentional whitespace, and light dividers
- **Document, form or selected object:** a coherent content surface can establish where the object begins and ends, especially for reading, editing and Markdown.
- **State and operation:** make action boundaries and status legible; distinguish primary, secondary, destructive, disabled and pending states.

Choose surfaces for these roles, reusing a surface where it serves several needs. Preserve product character while clarifying information structure

## Design optical alignment

Plan alignment during component design:

- Identify the **perceived content center**: icon visible mass can differ from its SVG viewBox or container; letters, Chinese glyphs and numeral/unit pairs have distinct baselines and visual weight
- Choose a shared alignment mechanism (flex/grid, line-height, baseline pairing, icon sizing, internal padding), then inspect perceived alignment at rendered size
- Judge the full control or card in context. Check active/inactive states, loading labels, accessibility text scaling, and touch target stability
- Check brand marks and functional icons **at their real smallest display sizes and crop shapes**. A richly detailed asset may require a separate simplified small-size variant rather than shrinking the full artwork
- Make small, evidence-backed optical corrections at the source of the rendering issue, preferably in the shared component

After content deletion, rebalance grouping and density around the remaining content and main task

## Design review from symptom to fix

| Symptom | Check before changing | Likely minimal remedy | Disconfirming evidence |
| --- | --- | --- | --- |
| Feels messy although aligned | Too many equal-weight headings/actions/surfaces? | Reduce secondary weight, group by user goal, remove redundant chrome | Intended experts need simultaneous comparison |
| Feels empty | Oversized intro, weak content measure, missing grouping? | Rebalance page rhythm and task area | Editorial breathing room is intentional and tested |
| Feels dirty or noisy | Borders/shadows/colors used for every group? | Simplify surface roles and rely on proximity | Denser data truly needs visible row separation |
| Feels off-center | Actual glyph mass, mixed baselines, container padding? | Tiny optical adjustment after inspecting at target size | Geometry already looks balanced in runtime |
| Feels hard to operate | Control looks like passive caption, or hit box too small? | Increase affordance and active region | Existing whole-row interaction is accessible and discoverable |
| Feels generic | Brand/story disconnected from interaction and content? | Make hierarchy, imagery and motion purposeful | Prescribed neutral enterprise system is appropriate |

Use disconfirming evidence to challenge the diagnosis. Locate supported findings by selector/component, state, and viewport

## Craft across states

Inspect loading, partial updates, errors, sticky/fixed bars, keyboard, long text, scroll position, links, disabled and selected states. Keep recovery and primary actions reachable. On data screens, verify aggregation, zero baseline, precision, and missing-value meaning

Where motion is requested, preserve chart caps, labels, hit targets, and axis geometry through the transition, and preserve dialog location and user control. Choose restrained motion or a static view according to the task

## Implementation review and judgment

Make the *smallest coherent set* of changes across related screens. Reuse tokens with purposeful variation for narrative pages, settings, and records. Ask about consequential preferences using comparisons at matching content

Before declaring a visual improvement, inspect a rendered before/after at matching viewport, theme, content and state; for platform chrome and native controls, use that platform's preview/device. Code review can identify risk but cannot establish how the layout looks to a user.
