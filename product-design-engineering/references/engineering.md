# Cross-platform design engineering

Build a functioning state model using the target platform's conventions and capabilities. The controls section includes Web examples; verify their applicability against platform mechanisms before adapting them

## Before code

Inspect the real repository structure, component contract, state/data sources, existing tokens, dependencies, routing, tests, feature flags and caller assumptions. Map the shortest safe change. Confirm which performance and accessibility mechanisms exist on the actual platform

## Decisions to make when relevant

- Data semantics and state ownership: source of truth, derived vs stored state, server/client consistency, optimistic updates, reconciliation, idempotence where needed
- Components: reuse stable project abstractions; extract shared primitives for recurring responsibilities
- Inputs and flows: validation boundaries, focus management, keyboard/touch interaction, loading/disabled behavior, error messages, recovery and cancellation
- Async: concurrency, cancellation, stale responses, retries (with limits and idempotency), slow network, offline/reconnect when supported
- Visual: real dimensions, content-driven sizes, responsive layout, safe areas, font scaling, contrast, semantic roles and interaction targets
- Animation: cancel/retarget on state changes, prefer existing tokens, confirm compositing/layout implications on the platform, preserve truthful data and accessible content
- Security/privacy: input boundaries, authorization, personal-data exposure, destructive actions, secure defaults
- Performance: critical path, input responsiveness, rendering count, image/font loading, unnecessary computation, main-thread cost, memory leaks, reduced-motion
- Dependency policy: use platform/standard features or installed packages first; new dependencies require a clear cost-benefit reason

## Quality signals

Trace callbacks through state and data, check interruptions/reentrance, and observe target behavior. Follow project technology choices and record verification gaps

When platform-specific specialist skills are available, load them only for the relevant part (e.g. React performance for React projects, Apple HIG for Apple platforms, web interface guidance for Web)

## Controls, feedback, and accessibility

- Use native buttons, links, form controls, and existing accessible primitives with appropriate names, labels, and keyboard behavior
- Show press feedback at the start of a press; commit the action through the control's normal activation behavior. Do not move submission, navigation, or destructive side effects to `pointerdown` just to appear faster
- Keep a visible focus indicator. Keyboard users need immediate state feedback too; distinguish feedback from decorative motion that delays their work
- Provide hover, focus-visible, pressed, selected, disabled, and pending states where applicable. Optional hover effects can use `@media (hover: hover) and (pointer: fine)`; essential functionality must also work without hover
- Give touch controls adequate hit areas and separation. Check contrast and target size against the project's accessibility target; use WCAG 2.2 AA as the baseline when none is specified
- Model pending, success, failure, empty, and retry states honestly. Prevent duplicate submission where the operation requires it; distinguish an actual transaction lock from an animation lock
- Associate validation with its field and preserve input after errors. Announce important asynchronous status changes through accessible semantics
- For modal dialogs, provide a name, appropriate initial focus, contained keyboard focus, dismissal behavior, and focus restoration. Keep the background inert while modal. Prefer a tested primitive over rebuilding these mechanics
- Treat visual presence and interactive state separately. Opacity alone does not hide content from keyboard or assistive technology. Exiting or hidden content must not remain accidentally actionable; move focus appropriately before hiding or making its subtree inert
- Supply visible and keyboard-accessible alternatives to swipe, drag, or hover-only actions. Preserve existing confirmation, undo, and cancellation behavior for consequential actions

## Input coordination and responsive controls

- For submit-on-key inputs, let IME composition own candidate-selection keys before handling application shortcuts or suggestion menus. In Web implementations inspect composition lifecycle and the event's composition signal; legacy key-code fallbacks are compatibility measures to verify on target browsers, not a portable input API. Test the commit key and the next intentional submit separately, including mobile keyboard behavior
- When suggestions are active, route selection, dismissal and submission through the existing control contract so one key cannot both choose a suggestion and send. Preserve the product's newline and Tab behavior; handle empty results and retain the draft and references after failed submission. Add mentions or slash commands only when requested by the product
- Use roving focus only for composite widgets whose interaction pattern calls for it, with appropriate roles, arrow navigation and entry/exit behavior. Ordinary independent controls retain normal Tab navigation. Prefer the project's accessible primitive and check dynamic/disabled items and focus restoration
- Compress toolbars by available container space: reduce optional labels/spacing, group secondary actions into an accessible overflow menu, or wrap. Preserve primary actions, status meaning, accessible names, and touch targets. Derive breakpoints from actual overflow with long translations and enlarged text; use platform equivalents where container queries are unavailable

For conversation-specific scroll and execution states, load [Agent UI](agent-ui.md); these general input rules also apply outside chat

## Async state and performance evidence

- Follow the actual persistence contract. If feedback is optimistic, retain enough prior state to recover and reconcile the server response; a failed request must not leave a false success state
- Handle repeated intent deliberately through the existing transaction policy. A disabled button alone is not server idempotency, and an animation lock must not delay otherwise valid input
- Prevent stale responses from overwriting a newer object or intent. Scope cancellation and cleanup to the operation; account for navigation/unmount without silently losing recoverable input
- Trace the user-visible critical path before optimizing. In React or similar stacks, inspect independent request waterfalls, unnecessary data transfer, shared request state, and expensive rendering before adding caches or memoization. Preserve authorization and cache isolation
- Check library APIs against the installed version. Source-level suspicion is a performance risk to measure, not proof of a speedup; record the workload and actual measurement when making one
