# Motion and continuity

The implementation examples below target Web UI. For other platforms, use their animation, input, lifecycle, and accessibility APIs while preserving the same interaction goals

## Decide whether motion earns its place

For each new effect, identify its purpose: acknowledge input, explain a state change, preserve a spatial relationship, or demonstrate something the user needs to understand. A request for expressive marketing or celebration can justify decoration within that scope

Then check frequency, task cost, and accessibility. Frequently repeated interactions and data-reading surfaces usually benefit from less movement. Selection, typing, focus, and access to controls remain immediate. A static change or simple fade is a valid result

Reduce or remove an unnecessary effect before introducing a more elaborate one. Do not add motion merely because a component currently has none, or stagger content the user is already trying to read and operate

### Define the trigger and replay contract before animation

Use a small event/state map for motion that is likely to recur; do not design an effect solely from its ideal success screenshot:

| Event | Default intent | Common failure to avoid |
| --- | --- | --- |
| First meaningful appearance | Optional entrance effect that improves recognition | Staggering content that users need immediately |
| Returning to an existing page/tab | Preserve stable content and scroll state | Replaying counters or success effects on `onShow`/remount |
| User-requested refresh | Clearly acknowledge refresh; optionally replay relevant *data-display* motion after meaningful completion | Treating passive refresh or failed request as a new success |
| Passive data update | Update truthfully, generally without re-running entrance effects | Resetting a counter to zero on every value change |
| Confirmed business/state change | Animate the actual transition if helpful | Destroying the shared background or flashing an empty intermediate frame |
| Cancellation, reversal, interrupted transition | Continue from displayed state or show a valid stable state | Unmounting the previous visual before the replacement is ready |

Keep persistent visual surfaces mounted or visually continuous when their identity persists. Separate data refresh from the signal to **replay** an animation; explicit user intent is safer than attaching replay to fetches or generic page lifecycle events. Honor reduced-motion preferences and verify real device/platform behavior where it affects overscroll, gesture physics or native chrome

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

- An ease-out curve is a useful starting point for a response that should begin promptly. Ease-in-out can suit an already visible element changing position. Linear motion fits constant-rate indicators. Use a different curve when the actual behavior warrants it
- Native CSS easing is acceptable. Prefer the product's tested custom curves when present; a custom cubic-bezier is not intrinsically better
- Keep related transitions coherent. Make dismissal shorter when it improves responsiveness; identical enter/exit timing is not automatically a defect. Deliberate holds retain their intentional timing and accessible alternative
- Use explicit transition properties instead of `transition: all`. Tune distance and amplitude as well as duration; making a large movement faster does not necessarily make it comfortable

### Spatial continuity and implementation choice

- Anchor a trigger-attached surface to its actual trigger and placement, including placement flips. A centered modal can remain centered. Use the component library's positioning/origin API when available
- Keep entrance, dismissal, and gesture direction spatially understandable. A restrained fade is often enough; scaling every surface or starting at zero scale is not a default
- Use CSS transitions for simple retargetable state changes. They can reverse during a transition; position continuity does not imply continuous velocity
- Use WAAPI when programmatic playback control is useful, and a suitable existing spring implementation when gesture velocity and retargeting matter. Keyframes remain useful for deliberate sequences or loops with a valid purpose
- Retarget from the current displayed state rather than a stale start or destination. Prevent old completion callbacks, timers, or promise handlers from closing a newly reopened surface or overwriting a newer state
- For springs, start with restrained or no overshoot. Add bounce for an intentional physical interaction or product character. Check the library's parameter meanings and velocity units: a damping ratio is not the same as a raw damping coefficient
- Keep semantic completion independent of animation completion. Handle cancellation, zero-duration/reduced-motion paths, and unmounting without depending solely on an animation-end event

### Gesture continuity

Apply these details when the task includes dragging, swiping, or a gesture-driven sheet; do not introduce custom gestures merely to use them

- Keep content attached to the active pointer with its original grab offset. Direct manipulation follows the pointer; a decorative spring lag should not make a functional slider or drag trail the user's input
- Track the active pointer identity and use capture when appropriate. Handle `pointercancel`, lost capture during an active gesture, and unmounting; clean up state and listeners without a surprise commit
- Distinguish gesture intent before claiming a drag. Scope `touch-action` to the relevant interaction, preserving page scrolling and pinch zoom where they are not in conflict
- Estimate signed release velocity from recent timestamped samples, with consistent units and protection against zero time deltas. Use direction and position together; do not copy an unsigned whole-gesture average or a magic dismissal threshold
- When momentum is intended, choose the endpoint from the projected direction of travel and hand velocity to the settling animation. Test the actual library's behavior instead of assuming every spring preserves velocity
- Use bounded resistance and an understandable return at limits when useful. Re-grabbing or reversing a moving surface should start where it is now. Also test cancellation and the non-gesture alternative

## Optional spring reference and scroll edges

Choose intent first: immediate state acknowledgement may need no movement; a timed reveal can use easing; a released drag or interruptible positional transition may benefit from a spring. Reuse existing motion tokens before considering these examples from the inspected Framer Motion source

| Upstream identifier | Stiffness | Damping | Mass | Candidate use to evaluate, not a required mapping |
| --- | --- | --- | --- | --- |
| `SPRING_BOUNCY` | 600 | 30 | 1.0 | Small expressive feedback where overshoot is welcome |
| `SPRING_SNAPPY` | 320 | 28 | 1.0 | Compact positional reveals where settling remains unobtrusive |
| `SPRING_GENTLE` | 380 | 18 | 1.0 | Deliberately elastic feedback; the name does not mean low bounce |
| `SPRING_HEAVY_SNAP` | 1200 | 80 | 0.1 | Damped settling after direct manipulation, subject to gesture testing |

These numbers are source definitions, not measured guarantees of duration, overshoot or perceived quality. The source's AGENTS table disagrees with several definitions; use the [pinned source record](source-map.md#open-claude-ui-selective-integration--2026-10-16). Confirm the installed engine's units, initial velocity and rest thresholds, then observe actual travel, reversal, repeated activation and reduced motion. Do not translate these values mechanically to another engine or add Framer Motion just to use them

A scroll-edge fade can indicate hidden overflow when the surface benefits from that cue. Show it only at edges with more content, update it after content/container resize, and avoid obscuring text, focus indicators or controls. A simple gradient or no mask can be sufficient; a seven-stop mask is an optional treatment, not a quality gate. Use the platform's supported rendering mechanism with a readable fallback; fading does not solve [conversation scroll ownership](agent-ui.md)

## Performance and preference fallbacks

- Prefer animating `transform` and `opacity` for movement and fading, but verify the actual rendering path. Neither a CSS property nor an animation library guarantees compositor-only execution in every situation
- Animate layout properties when a real layout change requires them and the measured result is acceptable. Do not replace an expanding section with visual scaling that leaves incorrect layout or distorts its contents merely to satisfy a property rule
- Avoid per-frame layout read/write interleaving, broad inherited custom-property updates, and component-tree rerenders for pointer tracking. Batch measurements and update the smallest relevant surface
- Profile suspected jank under representative load before promising a performance improvement. Large blur, backdrop effects, and excessive layers deserve particular scrutiny. Use `will-change` only for an observed need, on a scoped surface, and release it when no longer needed
- Reuse supported platform features. Check target-browser support before relying on `@starting-style`, view transitions, or other newer APIs; the final visible state and core interaction need a usable fallback
- Honor `prefers-reduced-motion` in CSS and JavaScript-driven motion. Replace large movement, parallax, elastic overshoot, and decorative loops with a static state or gentle fade while retaining meaningful feedback
- Preserve final geometry, visibility, focus, and lifecycle behavior in the reduced-motion path. Avoid blanket `transform: none` rules that move positioned surfaces or leave drawers in the wrong state. React to preference changes for long-lived interactions when supported
- Make translucent surfaces readable over real content and provide a solid fallback. Reduced-transparency and increased-contrast queries can enhance supported browsers; baseline legibility should not depend on those queries being available
- For persistent automatic motion, provide the applicable pause/stop behavior and honor reduced motion. Do not simulate progress or prolong loading solely to display an effect

## Data transitions

- Distinguish an entrance from an update. On updates, preserve item identity and move from the current displayed state; avoid resetting existing data to zero solely for decoration
- Shared normalized progress is one option for a positive-bar entrance with a fixed zero baseline: `height_i(t) = final_height_i * easing(progress(t))`. It preserves relative proportions during that entrance; it is not a universal requirement or an equal-pixels-per-second rule
- When values, ordering, or scales change, keep the interpretation truthful throughout the transition or choose an immediate update. Handle negative, zero, missing, and invalid data distinctly; don't animate missing data into a fabricated zero
- Retarget interrupted updates coherently. Keep labels aligned with the displayed state or clearly separate stable final values from transitional decoration; avoid animated counters that impede reading
- A stagger or line reveal can imply order or elapsed time. Use it only when that meaning fits the data and does not delay comparison or interaction. Reduced motion must retain the same information and usable final state
