# Aesthetic direction and visual judgment

Load this reference for genuinely open visual direction, branding/identity expansion, aesthetic critique, or a request whose central question is *why the interface looks wrong despite technically correct CSS*. It is not a compulsory pass for routine UI edits, technical audits, or backend features. Read the current project's screens, assets, tokens and actual brief before applying any example below.

## 1. Treat aesthetics as a situated decision

Good aesthetic judgment connects the interface's purpose and identity with perceptual organization, expressive choices and actual use. Different audiences and tasks can prefer different visual languages. Design principles guide hypotheses, not universal laws or a measurable scalar called "taste".

Keep three judgments distinct:

- **Perceptual quality:** the user can find the focus and understand grouping, spatial order and relative importance.
- **Expressive quality:** typography, color, image, shape and motion form a recognizable character that fits the subject and intended emotional tone.
- **Operational quality:** the same visual decisions support reading, touch, wayfinding, status and recovery under real content and constraints.

Research on web first impressions supports a role for visual complexity and prototypicality (Tuch et al., 2012), but a low-complexity/high-prototypicality preference in those stimuli is not a requirement that all distinctive products look conservative. Similarly, the aesthetic-usability effect can make an attractive interface *seem* easier to use even when tasks fail. Measure task success separately from appeal. These studies concern sampled websites and judgments; do not transfer quantitative effects to every mobile app, language or population.

## 2. Read composition before styling

Inspect the screen as a whole before changing color or shadows. At its actual size or a scaled thumbnail, ask:

1. What is the first focal point? Does the primary task or defining content deserve that attention?
2. Where does the eye move next? Can people identify related information without tracing every border?
3. Which groups have the most visual weight? Is it proportionate to their importance?
4. Where is the dense region, and where can the eye rest? Does spacing separate *groups*, not merely individual items?
5. What is the intended character, and which rendered choice makes it visible?

Use perception and Gestalt principles as diagnostic tools:

- **Proximity, similarity and common region** make related items read as groups. First correct grouping and alignment; borders and cards are supplementary cues when meaningful boundaries require them.
- **Figure–ground and contrast** direct attention. Reserve strong differentiation for decisions, states or expressive focal elements that need it; contrast must also protect legibility.
- **Repetition with variation** creates rhythm across components and sections. Too little variation flattens hierarchy; excessive variation weakens the system.
- **Optical balance** depends on actual visible mass, not only the center coordinate. Glyph shapes, corner curvature, color saturation and imagery can shift perceived weight. Inspect at rendered size before adding offsets.
- **Negative space** expresses both separation and emphasis. Empty space has a purpose when it reinforces reading order, not when it is an artifact of arbitrarily fixed heights or removed content.

These are observations to test against the real composition. Do not enforce an 8-point grid, golden ratio, a prescribed number of columns, perfectly symmetric layouts, or a single whitespace density across unrelated products.

## 3. Select typography, color and material by role

### Typography

Typography carries information and identity at once. Pick a suitable family and hierarchy from content and audience. Compare the rendered effect of size, weight, width, line length, line-height and tracking as a unit. A display face can carry identity while ordinary body text stays readable. Chinese, Latin, punctuation and numerals have different visual metrics; mixed-language controls, numbers with units, icons and badges require optical inspection. Prefer project type styles and system fonts unless a new font demonstrably serves the brief.

### Color

Start from semantic roles (canvas, text, emphasis, selection, focus, positive/negative/caution status) and the project's existing palette. Judge **relative luminance, saturation and occupied area**, not only hue names. A saturated accent covering a small call to action differs from the same color covering the entire canvas. Check contrast in actual layered surfaces, gradients and themes. Cultural/industry associations can inform choices, but are neither universal psychology nor permission to stereotype audiences. Brand color never replaces a clear status label or other non-color cue.

### Geometry and material

Scale, alignment, corner shape, borders, shadows, translucency, texture and imagery should describe structure, affordance or character. Choose few, meaningful surface layers. Heavy shadows can be appropriate for tangible objects; flat surfaces can be appropriate for a dense tool; a soft illustration can be appropriate for a narrative view. Do not adopt glassmorphism, neumorphism, gradients, brutalism or flat design solely because it is fashionable. Apply focus, hit-target, density and contrast constraints to each.

### Imagery and icons

Prefer actual product states, authorized brand assets or properly sourced media when depicting real products or organizations. Label concept art and generated/stock imagery honestly; do not imply an invented screenshot, employee, customer or result is real. Crop at the shipping size and inspect its focal subject. Avoid tiny richly detailed assets that collapse at icon/avatar size; use simplified variants if needed. Use icons with an established visual family; do not replace comprehensible labels with ambiguous pictograms merely to make the screen quieter.

## 4. Build art direction from the subject

For a new product or a genuine visual-world redesign, formulate a brief from the actual material:

- **Subject and user:** who this is for, the context of use, what is being sold, understood or accomplished.
- **Existing truth:** recognizable assets, typography, palettes, cultural context, patterns, restrictions, and actual content that should survive.
- **Visual thesis:** one specific idea or atmosphere tied to the product, stated concretely (e.g. "a calm illustrated field notebook for personal nature observations" instead of "premium, elegant, modern").
- **Expression choices:** typography, composition, color/material, imagery and one distinctive recurring detail that support that thesis.
- **Counterexample:** which common treatment would make this product look generic, misleading or wrong, and why.

Differentiate a direction through the **combination** of content and composition rather than simply selecting an unusual hue or font. Research references when helpful; separate inspiration, approved brand assets and prohibited copying. For an open exploration, consider two or three *meaningfully different* directions, contrasted on audience fit, information clarity, distinctiveness, cost and implementation/platform reality. When the user has already fixed the direction, develop it instead of inventing alternatives or requesting another approval.

Design the actual states and useful content before decorating. Do not put a photographic hero on a data tool, turn navigation into an art installation, or use broad page rules such as "one section per viewport" unless the particular communication task benefits.

## 5. Use surface intent to calibrate expression

These intents can coexist on a page; pick the dominant job without making another classification framework a required ceremony.

| Primary intent | Visual decision emphasis | Common failure to avoid |
| --- | --- | --- |
| **Operate**: configure, manage, compare, pay | Task locality, robust controls, predictable density, truthful state | A striking composition that obscures the controls and data |
| **Read**: understand stories, reports, long content | Measure, type hierarchy, rhythm, meaningful media and anchors | Decorative interruptions and illegible large type |
| **Experience**: personal, emotional, expressive | Atmosphere, authored imagery, meaningful pace, warm detail | Unclear action paths or misleading emotional/transactional states |
| **Persuade**: explain and present an offering | Real offering, strong focal narrative, credible visual proof | Generic dashboard mockups, invented claims, decorative effects without content |

A brand system may share colors and components while using different density, composition and media across these intents. Consistency is not sameness.

## 6. Critique with evidence and alternatives

A strong critique begins with the *single highest-impact observation*, not a long list of adjectives:

`Visible evidence → expected reading/feeling/action → mismatch → likely cause → specific correction → how to check`

Useful challenge questions:

- What already works and should remain untouched?
- Is the issue **content necessity**, **layout/composition**, **type/color/material**, **component drift**, **state/interaction**, or a **wrong overarching concept**?
- Could the same correction be made by subtracting or grouping, before adding visual chrome?
- If the brief were replaced by an unrelated product name, would the visual concept still look identical? If yes, is that because of useful standard interaction conventions, or because it has no identity?
- Is a criticism actually about taste, and might a different audience reasonably disagree?

Choose a local correction for a local defect; choose a shared component change for repeated drift; recommend an identity change only if the concept itself fails and the request permits redesign. Challenge a preferred option with a plausible alternative. Do not manufacture problems in an already clear interface or spend time making a perfectly acceptable standard control "unique".

Examples:

- **"The billing page feels cheap"** may come from many competing card backgrounds and mixed numeric baselines. Test grouping, tabular numerals and semantic surface roles before replacing the palette with glass effects.
- **"The personal story page feels like an admin panel"** may require an editorial composition and imagery that reflect its narrative content while keeping edit, privacy and status actions unambiguous.
- **"The product landing page looks AI-generated"** may need genuine product imagery, a characteristic arrangement and better content specificity; merely banning gradients or adding a serif font will not solve that.
- **"The button icon is not centered"** may arise from visual mass within the icon, not flex alignment. Check its bounding path and rendered control before introducing a global offset.

## 7. Inspect and iterate at an appropriate cost

When the output is implemented UI, compare rendered results at representative sizes/states and actual target runtime where available. Review from whole-frame composition to focal region to pixel detail. Fix a batch of supported problems, then inspect again. For meaningful design choices, use a brief-linked independent critique when feasible; the designer's own confidence is not evidence.

Evaluate visual craft separately from functional correctness and brand fit. A screenshot comparison detects regression, not aesthetic merit. Avoid a single synthetic "beauty" score as an acceptance gate. Where subjective direction matters, make paired comparisons with the same content, viewport and theme; blind the reviewer to which version is newer and inspect disagreement. Real usability requires task observation, not image rating alone.

Stop when the user's goal and appropriate evidence threshold are satisfied. More iterations, more effects and more alternative concepts are not intrinsic improvement.

## Evidence and provenance

- Empirical scope: Tuch et al. (2012), *The role of visual complexity and prototypicality regarding first impression of websites*, [Google Research](https://research.google/pubs/the-role-of-visual-complexity-and-prototypicality-regarding-first-impression-of-websites-working-towards-understanding-aesthetic-judgments/); Lindgaard et al. (2006), *Attention web designers: You have 50 milliseconds to make a good first impression!*, [journal DOI](https://doi.org/10.1080/01449290500330448).
- Interpretive caution: Nielsen Norman Group, [The Aesthetic-Usability Effect](https://www.nngroup.com/articles/aesthetic-usability-effect/), last reviewed 2026-09-01.
- Platform guidance: [Apple Human Interface Guidelines — Design principles](https://developer.apple.com/design/human-interface-guidelines/design-principles/) and [Layout](https://developer.apple.com/design/human-interface-guidelines/layout); [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/) for applicable accessibility requirements.
- Independently synthesized from comparative review of [Impeccable](https://github.com/pbakaus/impeccable), [Taste Skill](https://github.com/Leonxlnx/taste-skill), [Anthropic Frontend Design](https://github.com/anthropics/skills/tree/main/skills/frontend-design), and [Emil Kowalski Skills](https://github.com/emilkowalski/skills). Their rules or aesthetics are not adopted wholesale. See [Source map](source-map.md) for previous integration decisions and license boundaries.
