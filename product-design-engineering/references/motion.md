# Motion and continuity

The implementation examples below target Web UI. For other platforms, use their animation, input, lifecycle, and accessibility APIs while preserving the same interaction goals

## Decide whether motion earns its place

For each new effect, identify its purpose: acknowledge input, explain a state change, preserve a spatial relationship, or demonstrate something the user needs to understand. A request for expressive marketing or celebration can justify decoration within that scope

Then check frequency, task cost, and accessibility. Frequently repeated interactions and data-reading surfaces usually benefit from less movement. Selection, typing, focus, and access to controls remain immediate. A static change or simple fade is a valid result

Remove effects whose task value is absent; keep content available for immediate reading and interaction

### Define the trigger and replay contract before animation

For recurring motion, define its event/state contract:

| Event | Default intent | Continuity check |
| --- | --- | --- |
| First meaningful appearance | Optional entrance that improves recognition | Immediately needed content stays available |
| Returning to an existing page/tab | Preserve stable content and scroll state | Counters and success feedback retain their current state on `onShow`/remount |
| User-requested refresh | Acknowledge refresh; optionally replay relevant *data-display* motion after meaningful completion | Distinguish requested refresh, passive update, confirmed success, and failure |
| Passive data update | Update the current display in place | Counters retain value continuity |
| Confirmed business/state change | Animate the actual transition if helpful | Shared backgrounds remain visually continuous |
| Cancellation, reversal, interrupted transition | Continue from displayed state or show a valid stable state | Keep the previous visual present until the replacement is ready |

Keep persistent visual surfaces mounted or visually continuous when their identity persists. Separate data refresh from the signal to **replay** an animation; explicit user intent is safer than attaching replay to fetches or generic page lifecycle events. Honor reduced-motion preferences and verify real device/platform behavior where it affects overscroll, gesture physics or native chrome

### Timing and easing

Reuse existing motion tokens. Otherwise tune these starting ranges in context:

| Situation | Starting point | Check |
| --- | --- | --- |
| Repeated navigation, typing, selection | Instant state; optional brief non-blocking feedback | No waiting for motion before the next action |
| Press feedback | Around 100–160 ms | Feedback begins immediately; release and cancellation stay responsive |
| Tooltip or small popover | Around 120–200 ms | Legible entry without slowing adjacent interactions |
| Menu or small state transition | Around 150–250 ms | Clear result, including rapid reversal |
| Larger dialog or drawer | Around 200–350 ms | Tune travel and settling; controls remain available |
| Explanatory or expressive sequence | Determined by the content and brief | Does not delay the user's main task; can be reduced or skipped |

- An ease-out curve is a useful starting point for a response that should begin promptly. Ease-in-out can suit an already visible element changing position. Linear motion fits constant-rate indicators. Use a different curve when the actual behavior warrants it
- Use the product's tested curves or suitable native CSS easing
- Keep related transitions coherent; choose dismissal timing for responsiveness. Preserve deliberate holds and their accessible alternative
- Specify transition properties explicitly and tune distance, amplitude, and duration together

### Spatial continuity and implementation choice

- Anchor a trigger-attached surface to its actual trigger and placement, including placement flips. A centered modal can remain centered. Use the component library's positioning/origin API when available
- Keep entrance, dismissal, and gesture direction spatially understandable; use a restrained fade when sufficient
- Use CSS transitions for simple retargetable state changes. They can reverse during a transition; position continuity does not imply continuous velocity
- Use WAAPI when programmatic playback control is useful, and a suitable existing spring implementation when gesture velocity and retargeting matter. Keyframes remain useful for deliberate sequences or loops with a valid purpose
- Retarget from the current displayed state rather than a stale start or destination. Prevent old completion callbacks, timers, or promise handlers from closing a newly reopened surface or overwriting a newer state
- For springs, start with restrained or no overshoot. Add bounce for an intentional physical interaction or product character. Check the library's parameter meanings and velocity units: a damping ratio is not the same as a raw damping coefficient
- Keep semantic completion independent of animation completion. Handle cancellation, zero-duration/reduced-motion paths, and unmounting without depending solely on an animation-end event

### Gesture continuity

Apply these details to requested dragging, swiping, or gesture-driven sheets

- Keep content attached to the active pointer with its original grab offset. Direct manipulation follows the pointer; a decorative spring lag should not make a functional slider or drag trail the user's input
- Track the active pointer identity and use capture when appropriate. Handle `pointercancel`, lost capture during an active gesture, and unmounting; clean up state and listeners without a surprise commit
- Distinguish gesture intent before claiming a drag. Scope `touch-action` to the relevant interaction, preserving page scrolling and pinch zoom where they are not in conflict
- Estimate signed release velocity from recent timestamped samples, with consistent units and protection against zero time deltas. Choose dismissal thresholds using direction, position, and target interaction
- When momentum is intended, choose the endpoint from projected travel and hand velocity to the settling animation; verify the installed library's handoff behavior
- Use bounded resistance and an understandable return at limits when useful. Re-grabbing or reversing a moving surface should start where it is now. Also test cancellation and the non-gesture alternative

## Optional spring reference and scroll edges

Choose intent first: immediate state acknowledgement may need no movement; a timed reveal can use easing; a released drag or interruptible positional transition may benefit from a spring. Reuse existing motion tokens before considering these examples from the inspected Framer Motion source

| Upstream identifier | Stiffness | Damping | Mass | Candidate use to evaluate |
| --- | --- | --- | --- | --- |
| `SPRING_BOUNCY` | 600 | 30 | 1.0 | Small expressive feedback where overshoot is welcome |
| `SPRING_SNAPPY` | 320 | 28 | 1.0 | Compact positional reveals where settling remains unobtrusive |
| `SPRING_GENTLE` | 380 | 18 | 1.0 | Deliberately elastic feedback |
| `SPRING_HEAVY_SNAP` | 1200 | 80 | 0.1 | Damped settling after direct manipulation, subject to gesture testing |

These definitions come from the inspected Framer Motion source; version differences are recorded in the [pinned source record](source-map.md#open-claude-ui-selective-integration--2026-10-16). Keep the project's animation engine and adapt values to its units, initial velocity, and rest thresholds. Evaluate travel, duration, overshoot, reversal, repeated activation, and reduced motion in that engine

Use a scroll-edge fade when hidden overflow needs a cue. Show it at edges with more content and update after content/container resize, preserving readable text, focus indicators, and controls. Choose a simple supported treatment with a readable fallback; handle [conversation scroll ownership](agent-ui.md) separately

## Performance and preference fallbacks

- Prefer `transform` and `opacity` for movement and fading; verify the actual rendering path and compositing behavior
- Animate layout properties when the layout change requires them and measurement supports the result; preserve correct geometry and content proportions
- Batch layout measurements before writes, localize custom-property updates, and keep pointer tracking scoped to the smallest relevant surface
- Profile suspected jank under representative load before promising a performance improvement. Large blur, backdrop effects, and excessive layers deserve particular scrutiny. Use `will-change` only for an observed need, on a scoped surface, and release it when no longer needed
- Reuse supported platform features. Check target-browser support before relying on `@starting-style`, view transitions, or other newer APIs; the final visible state and core interaction need a usable fallback
- Honor `prefers-reduced-motion` in CSS and JavaScript-driven motion. Replace large movement, parallax, elastic overshoot, and decorative loops with a static state or gentle fade while retaining meaningful feedback
- Preserve final geometry, visibility, focus, lifecycle behavior, and any transforms needed for positioning in the reduced-motion path. React to preference changes for long-lived interactions when supported
- Make translucent surfaces readable over real content and provide a solid fallback. Reduced-transparency and increased-contrast queries can enhance supported browsers; baseline legibility should not depend on those queries being available
- For persistent automatic motion, provide the applicable pause/stop behavior and honor reduced motion. Do not simulate progress or prolong loading solely to display an effect

## Data transitions

- Distinguish entrance from update; preserve item identity and continue updates from the current displayed state
- For a positive-bar entrance with a fixed zero baseline, shared normalized progress is one option: `height_i(t) = final_height_i * easing(progress(t))`. It preserves relative proportions during that entrance
- When values, ordering, or scales change, keep the interpretation truthful throughout the transition or choose an immediate update. Handle negative, zero, missing, and invalid data distinctly; don't animate missing data into a fabricated zero
- Retarget interrupted updates coherently. Keep values readable, with labels aligned to the display or stable final values clearly separated from transitional decoration
- A stagger or line reveal can imply order or elapsed time. Use it only when that meaning fits the data and does not delay comparison or interaction. Reduced motion must retain the same information and usable final state
