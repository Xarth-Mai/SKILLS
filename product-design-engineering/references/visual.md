# Visual hierarchy and content

## Translate a complaint into a decision

| Observation | Hypothesis to inspect | Scoped intervention and check |
| --- | --- | --- |
| Everything feels equally important | Secondary surfaces, actions, and titles compete with the primary task | Adjust emphasis using existing semantic roles; compare what draws attention at the same content and size |
| The page feels crowded despite alignment | Grouping, repeated chrome, or density obscures the reading order | Separate meaningful groups and remove redundant surfaces; retain useful information and compare scanning |
| The layout feels empty | Content width or grouping weakens the relationship between information and action | Reorganize the task area before adding decoration; verify the actual populated state |
| A mathematically centered icon looks displaced | The visible glyph mass differs from its bounding box | Inspect at rendered size and adjust optical placement without breaking the hit area |
| The page feels generic | Design choices do not reflect its audience, content, or project identity | Choose a coherent direction from the brief and existing assets; do not replace a requested style merely because it is common |

These are diagnostic candidates, not automatic findings. Explain the user-facing purpose of a token or treatment before changing its value. Preserve purposeful differences between surfaces

## Visual hierarchy and layout

- Make the page's purpose, current location, primary action, and next step apparent. Use specific labels and visible state rather than relying on decoration to explain the interface
- Group related content through proximity and alignment. Make spacing between groups larger than spacing within a group. Reuse the existing spacing scale instead of adding unrelated one-off values
- Establish hierarchy through size, weight, contrast, and whitespace together. Let secondary actions look secondary while remaining readable and discoverable
- Match density to the task. A tool or dashboard can be compact; a landing page can be spacious. Add explanatory context when it reduces effort, rather than hiding everything to appear minimal
- Prefer a small, consistent set of surfaces, borders, radii, shadows, and accent roles. Use gradients, translucency, and depth when the product direction or a functional layer calls for them, not as automatic signs of quality
- Preserve semantic status colors and contrast in supported themes. Use text, icons, or structure as well as color to distinguish important states
- Check narrow layouts, long titles, translated content, empty sections, and populated states. Fix the element causing overflow rather than concealing the defect with page-wide clipping
- Let content size naturally. Use responsive constraints rather than fixed heights that clip text or create empty slabs. Keep table overflow local and preserve access to essential actions
- Check sticky headers, overlays, safe areas, and the mobile keyboard when relevant. They should not cover focused controls, primary actions, or the content being edited

## Typography and content

- Reuse the product's typefaces and scale. Without a defined typeface, start with a suitable system stack; introduce a custom font for a concrete design reason
- Tune size, weight, line height, line length, and tracking as a set. Check the actual font and language: tight Latin display tracking is not a default for Chinese or body text
- Use optical sizing when supported by the chosen font. Keep body copy comfortable, labels legible, and numeric columns aligned; tabular numerals can stabilize comparable values and counters
- Support text enlargement and browser zoom without hiding content or disabling zoom. Allow wrapping where it is useful; make truncated essential information accessible another way
- Keep copy concrete: describe what an action does, what happened, and how to recover. Preserve user content; polish is not permission to replace meaningful text with generic filler
- Reserve space for changing button labels, asynchronous content, and media when useful. Loading and success states should not cause avoidable shifts or misrepresent actual completion

## Data presentation

- Preserve units, aggregation, missing-value meaning, comparison baselines, and metric definitions. Select an encoding for the intended comparison; a visual redesign does not authorize changing the calculation
- For bars encoding magnitude, use a truthful zero baseline and handle positive/negative values deliberately. Other chart types may need different scales; make scale changes and exclusions explicit
- Keep labels, legends, status meanings, and accessible summaries usable without hover or color alone. Test zero, missing, outlier, long-label, and frequent-update states
- Compare before/after at identical data, size, and state. Static screenshots can reveal clipping and hierarchy; they cannot establish user comprehension or animation quality
