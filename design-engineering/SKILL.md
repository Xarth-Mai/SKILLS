---
name: design-engineering
description: Design, polish, implement, or review web UI hierarchy, typography, spacing, interaction feedback, motion, and accessibility. Use for making an interface clearer or better to use, tuning gestures and transitions, or auditing UI quality. Complements website-building and lightweight coding workflows; not for backend-only work, hosting, preview infrastructure, image generation alone, or data analysis alone.
---

# Design Engineering

Improve clarity, hierarchy, responsiveness, and perceived quality while preserving the product's identity and intended behavior. Borrow interaction principles, not an Apple visual theme. Prefer the smallest change that solves an observed problem.

## Scope and collaboration

- Use the current request, project instructions, design system, and supplied references to define the target. Preserve established branding, content, public APIs, and business behavior unless the task authorizes changing them.
- For implementation or polish requests, inspect, decide, make the scoped changes, and verify. For review-only requests, report findings without editing files. For plan-only requests, provide the requested plan without implementing it.
- `sites-building` can own website construction; `ponytail` can own the lightweight coding workflow. This Skill supplies design decisions and acceptance checks. Use companions only when available and relevant; it also works alone.
- For data-backed dashboards, let an available `data-analytics:build-dashboard` own metric definitions and data correctness. Improve presentation without changing their meaning. Use `imagegen` only when image assets are part of the task.
- Hosting and preview-infrastructure tasks belong to their corresponding workflows. A missing Figma plugin is not a blocker: use accessible code, screenshots, references, and browser tools instead.
- Continue from an already specified target. Ask a focused question only when a missing decision materially affects correctness or scope; otherwise choose a reversible default and proceed. Skip activation speeches and repeated approval gates.

## Working loop

### 1. Inspect the actual interface

Read the affected components, shared styles/tokens, dependencies, and project scripts. Identify the main user task, the primary action, information density, supported devices, and the existing visual language. Inspect a representative shared component before inventing a new convention.

When a runnable preview is available, observe the current page and relevant states before editing. Capture a useful baseline for visual changes. When only code or an image is available, separate visible evidence from assumptions about interaction and performance.

Scope inspection to the requested surface and its shared dependencies. Expand to the whole application only for an application-wide request or a shared defect. Ignore generated, vendored, and build-output files during source sweeps.

### 2. Choose the highest-value change

Prioritize broken behavior and accessibility, then comprehension and hierarchy, then interaction continuity and measured performance problems, then optional polish. State the intended improvement briefly; a small fix does not need a separate design document.

For a new interface without an established direction, choose a coherent type scale, spacing rhythm, surface hierarchy, and motion character suited to its audience. Treat these as project choices, not universal numerical rules. For an existing interface, reuse its choices unless they cause the observed problem.

### 3. Implement with the existing stack

Reuse components, tokens, native elements, and installed libraries. Prefer CSS for simple state changes and existing primitives for menus, dialogs, and gestures. Add a dependency only when the required behavior justifies it; check the installed version's actual API before writing library-specific code.

Keep shared-component changes intentional: inspect representative consumers and preserve their states. Apply design and interaction changes together rather than adding animation after functionality has been redesigned independently.

### 4. Verify and deliver

Run the relevant project checks and exercise the changed states when tools permit. Reinspect the rendered result, fix observed regressions, and stop when the requested outcome is met. Use the acceptance pass below and report remaining limitations honestly.

## Visual hierarchy and layout

- Make the page's purpose, current location, primary action, and next step apparent. Use specific labels and visible state rather than relying on decoration to explain the interface.
- Group related content through proximity and alignment. Make spacing between groups larger than spacing within a group. Reuse the existing spacing scale instead of adding unrelated one-off values.
- Establish hierarchy through size, weight, contrast, and whitespace together. Let secondary actions look secondary while remaining readable and discoverable.
- Match density to the task. A tool or dashboard can be compact; a landing page can be spacious. Add explanatory context when it reduces effort, rather than hiding everything to appear minimal.
- Prefer a small, consistent set of surfaces, borders, radii, shadows, and accent roles. Use gradients, translucency, and depth when the product direction or a functional layer calls for them, not as automatic signs of quality.
- Preserve semantic status colors and contrast in supported themes. Use text, icons, or structure as well as color to distinguish important states.
- Check narrow layouts, long titles, translated content, empty sections, and populated states. Fix the element causing overflow rather than concealing the defect with page-wide clipping.
- Let content size naturally. Use responsive constraints rather than fixed heights that clip text or create empty slabs. Keep table overflow local and preserve access to essential actions.
- Check sticky headers, overlays, safe areas, and the mobile keyboard when relevant. They should not cover focused controls, primary actions, or the content being edited.

## Typography and content

- Reuse the product's typefaces and scale. Without a defined typeface, start with a suitable system stack; introduce a custom font for a concrete design reason.
- Tune size, weight, line height, line length, and tracking as a set. Check the actual font and language: tight Latin display tracking is not a default for Chinese or body text.
- Use optical sizing when supported by the chosen font. Keep body copy comfortable, labels legible, and numeric columns aligned; tabular numerals can stabilize comparable values and counters.
- Support text enlargement and browser zoom without hiding content or disabling zoom. Allow wrapping where it is useful; make truncated essential information accessible another way.
- Keep copy concrete: describe what an action does, what happened, and how to recover. Preserve user content; polish is not permission to replace meaningful text with generic filler.
- Reserve space for changing button labels, asynchronous content, and media when useful. Loading and success states should not cause avoidable shifts or misrepresent actual completion.

## Controls, feedback, and accessibility

- Use native buttons, links, form controls, and suitable existing accessible primitives. Provide accessible names, labels, and the expected keyboard behavior. A visual imitation is not a complete component.
- Show press feedback at the start of a press; commit the action through the control's normal activation behavior. Do not move submission, navigation, or destructive side effects to `pointerdown` just to appear faster.
- Keep a visible focus indicator. Keyboard users need immediate state feedback too; distinguish feedback from decorative motion that delays their work.
- Provide hover, focus-visible, pressed, selected, disabled, and pending states where applicable. Optional hover effects can use `@media (hover: hover) and (pointer: fine)`; essential functionality must also work without hover.
- Give touch controls adequate hit areas and separation. Check contrast and target size against the project's accessibility target; use WCAG 2.2 AA as the baseline when none is specified.
- Model pending, success, failure, empty, and retry states honestly. Prevent duplicate submission where the operation requires it; distinguish an actual transaction lock from an animation lock.
- Keep validation associated with the relevant field and preserve input after errors. Announce important asynchronous status changes with appropriate semantics rather than relying on motion alone.
- For modal dialogs, provide a name, appropriate initial focus, contained keyboard focus, dismissal behavior, and focus restoration. Keep the background inert while modal. Prefer a tested primitive over rebuilding these mechanics.
- Treat visual presence and interactive state separately. Opacity alone does not hide content from keyboard or assistive technology. Exiting or hidden content must not remain accidentally actionable; move focus appropriately before hiding or making its subtree inert.
- Supply visible and keyboard-accessible alternatives to swipe, drag, or hover-only actions. Preserve existing confirmation, undo, and cancellation behavior for consequential actions.

## Decide whether motion earns its place

For each new effect, identify its purpose: acknowledge input, explain a state change, preserve a spatial relationship, or demonstrate something the user needs to understand. A request for expressive marketing or celebration can justify decoration within that scope.

Then check frequency, task cost, and accessibility. Frequently repeated interactions and data-reading surfaces usually benefit from less movement. Selection, typing, focus, and access to controls remain immediate. A static change or simple fade is a valid result.

Reduce or remove an unnecessary effect before introducing a more elaborate one. Do not add motion merely because a component currently has none, or stagger content the user is already trying to read and operate.

### Timing and easing

Reuse existing motion tokens first. With no established values, these are starting ranges to tune in context, not compliance thresholds:

| Situation | Starting point | Check |
| --- | --- | --- |
| Repeated navigation, typing, selection | Instant state; optional brief non-blocking feedback | No waiting for motion before the next action |
| Press feedback | Around 100–160 ms | Feedback begins immediately; release and cancellation stay responsive |
| Tooltip or small popover | Around 120–200 ms | Legible entry without slowing adjacent interactions |
| Menu or small state transition | Around 150–250 ms | Clear result, including rapid reversal |
| Larger dialog or drawer | Around 200–350 ms | Tune travel and settling; controls remain available |
| Explanatory or expressive sequence | Determined by the content and brief | Does not delay the user's main task; can be reduced or skipped |

- An ease-out curve is a useful starting point for a response that should begin promptly. Ease-in-out can suit an already visible element changing position. Linear motion fits constant-rate indicators. Use a different curve when the actual behavior warrants it.
- Native CSS easing is acceptable. Prefer the product's tested custom curves when present; a custom cubic-bezier is not intrinsically better.
- Keep related transitions coherent. Make dismissal shorter when it improves responsiveness; identical enter/exit timing is not automatically a defect. Deliberate holds retain their intentional timing and accessible alternative.
- Use explicit transition properties instead of `transition: all`. Tune distance and amplitude as well as duration; making a large movement faster does not necessarily make it comfortable.

### Spatial continuity and implementation choice

- Anchor a trigger-attached surface to its actual trigger and placement, including placement flips. A centered modal can remain centered. Use the component library's positioning/origin API when available.
- Keep entrance, dismissal, and gesture direction spatially understandable. A restrained fade is often enough; scaling every surface or starting at zero scale is not a default.
- Use CSS transitions for simple retargetable state changes. They can reverse during a transition; position continuity does not imply continuous velocity.
- Use WAAPI when programmatic playback control is useful, and a suitable existing spring implementation when gesture velocity and retargeting matter. Keyframes remain useful for deliberate sequences or loops with a valid purpose.
- Retarget from the current displayed state rather than a stale start or destination. Prevent old completion callbacks, timers, or promise handlers from closing a newly reopened surface or overwriting a newer state.
- For springs, start with restrained or no overshoot. Add bounce for an intentional physical interaction or product character. Check the library's parameter meanings and velocity units: a damping ratio is not the same as a raw damping coefficient.
- Keep semantic completion independent of animation completion. Handle cancellation, zero-duration/reduced-motion paths, and unmounting without depending solely on an animation-end event.

### Gesture continuity

Apply these details when the task includes dragging, swiping, or a gesture-driven sheet; do not introduce custom gestures merely to use them.

- Keep content attached to the active pointer with its original grab offset. Direct manipulation follows the pointer; a decorative spring lag should not make a functional slider or drag trail the user's input.
- Track the active pointer identity and use capture when appropriate. Handle `pointercancel`, lost capture during an active gesture, and unmounting; clean up state and listeners without a surprise commit.
- Distinguish gesture intent before claiming a drag. Scope `touch-action` to the relevant interaction, preserving page scrolling and pinch zoom where they are not in conflict.
- Estimate signed release velocity from recent timestamped samples, with consistent units and protection against zero time deltas. Use direction and position together; do not copy an unsigned whole-gesture average or a magic dismissal threshold.
- When momentum is intended, choose the endpoint from the projected direction of travel and hand velocity to the settling animation. Test the actual library's behavior instead of assuming every spring preserves velocity.
- Use bounded resistance and an understandable return at limits when useful. Re-grabbing or reversing a moving surface should start where it is now. Also test cancellation and the non-gesture alternative.

## Performance and preference fallbacks

- Prefer animating `transform` and `opacity` for movement and fading, but verify the actual rendering path. Neither a CSS property nor an animation library guarantees compositor-only execution in every situation.
- Animate layout properties when a real layout change requires them and the measured result is acceptable. Do not replace an expanding section with visual scaling that leaves incorrect layout or distorts its contents merely to satisfy a property rule.
- Avoid per-frame layout read/write interleaving, broad inherited custom-property updates, and component-tree rerenders for pointer tracking. Batch measurements and update the smallest relevant surface.
- Profile suspected jank under representative load before promising a performance improvement. Large blur, backdrop effects, and excessive layers deserve particular scrutiny. Use `will-change` only for an observed need, on a scoped surface, and release it when no longer needed.
- Reuse supported platform features. Check target-browser support before relying on `@starting-style`, view transitions, or other newer APIs; the final visible state and core interaction need a usable fallback.
- Honor `prefers-reduced-motion` in CSS and JavaScript-driven motion. Replace large movement, parallax, elastic overshoot, and decorative loops with a static state or gentle fade while retaining meaningful feedback.
- Preserve final geometry, visibility, focus, and lifecycle behavior in the reduced-motion path. Avoid blanket `transform: none` rules that move positioned surfaces or leave drawers in the wrong state. React to preference changes for long-lived interactions when supported.
- Make translucent surfaces readable over real content and provide a solid fallback. Reduced-transparency and increased-contrast queries can enhance supported browsers; baseline legibility should not depend on those queries being available.
- For persistent automatic motion, provide the applicable pause/stop behavior and honor reduced motion. Do not simulate progress or prolong loading solely to display an effect.

## Review and acceptance pass

For reviews, inspect the affected code and rendered behavior where available. A search hit such as `ease-in`, a layout animation, or a long duration is a candidate to investigate, not proof of a defect.

Report confirmed issues in impact order. Each actionable finding needs a location (`file:line`, or the visible region for an image-only review), observed behavior or code evidence, user impact, a scoped correction, and a way to check it. Distinguish measured defects from risks requiring a browser check. Respect intentional design tradeoffs unless they violate the current task or cause a demonstrated problem.

Use the user's requested output format; otherwise keep the review compact. Report no findings when appropriate. Separate optional opportunities from defects, without quotas, manufactured issues, or aesthetic scores.

Before completing an implementation, check the relevant items:

- **Layout:** primary task remains clear; representative desktop/narrow layouts, long content, supported themes, and text enlargement are usable.
- **States:** resting, focus, press, pending, success/error, empty/populated, and dismissal states remain correct where affected.
- **Input:** mouse, keyboard, and touch behavior work as applicable; focus and scrolling are not lost, trapped, or obscured unexpectedly.
- **Motion:** repeated open/close, interruption, cancellation, reduced motion, and final state work; related transitions remain consistent.
- **Engineering:** relevant lint/typecheck/tests/build pass; shared-component consumers are checked; no unnecessary dependency or unrelated rewrite was introduced.
- **Evidence:** inspect the after state at the same useful viewport/state as the baseline. Record actual checks and meaningful limitations, not a claim that every possible browser was tested.

Deliver the patch or artifact requested, then briefly describe the design decisions and validation. Mark unavailable checks `NOT RUN`; do not turn static review into a claim of tested UI quality, accessibility conformance, or measured speedup.

## Reference material

The Skill is self-contained; the following files are for targeted follow-up, not mandatory reading on every task:

- Read [sources and adaptation notes](references/sources.md) when checking provenance or revising a rule.
- Read [validation scenarios](references/validation.md) when testing routing or changing the Skill's behavior.
