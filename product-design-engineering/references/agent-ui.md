# Conversation and agent interfaces

Use for conversation and agent-product tasks. Reuse the project's brand, components, input model, and event contract; provenance is recorded in the [source record](source-map.md#open-claude-ui-selective-integration--2026-10-16)

## Reading and scroll ownership

- Distinguish following the latest content from browsing history. While following, keep new content reachable without repeatedly restarting smooth scrolling for every token; when the user intentionally browses away, preserve their reading position until they return to the bottom or explicitly resume following
- Offer a discoverable, keyboard-accessible way to reach the latest content when following is suspended. A cooldown alone is not persistent reading intent; time passing must not force the viewport back to the bottom
- Inspect real wheel, touch, keyboard and scrollbar behavior, and distinguish programmatic scrolling from user intent. Track content and viewport size changes, including late media, expanded tool results and the on-screen keyboard. Preserve the visible reading anchor when older history is prepended
- Scope follow state to the conversation and its navigation contract. Cancelling a response, returning to a conversation or changing sessions should not accidentally inherit another view's scroll state
- Tune bottom tolerance and any cooldown to the platform. Verify event wiring, resize handling, accessibility, history browsing during sustained streaming, explicit resume, and content reflow

## Composer and message hierarchy

Use [Engineering](engineering.md#input-coordination-and-responsive-controls) for IME, suggestion menus and responsive actions. Preserve draft text and attachments until the submission contract allows clearing them; failures need a recoverable retry without silently losing or duplicating content

Distinguish user messages, assistant output and tool activity through readable role labels, grouping and emphasis. Bubble shapes and alignment are product choices. Keep partial output distinguishable from completed output; retain selectable text, code, links and accessible actions during updates. Announce meaningful state changes without reading every streamed token or stealing focus

## Truthful execution and permission states

Map the actual event/data contract to the relevant states

| State | User-facing meaning and action |
| --- | --- |
| Queued or waiting | Work is accepted or waiting on a known prerequisite; show the cause only if known |
| Working or generating | Execution is active; show meaningful activity and cancellation when supported |
| Needs approval | Show the proposed operation, relevant target/scope and consequences, with distinct approve and decline actions; execution remains gated by the real authorization mechanism |
| Succeeded | Show the confirmed outcome and usable result; finished animation or a closed stream alone is insufficient |
| Failed | Preserve useful output/draft and explain supported recovery; retry follows the operation's duplicate-prevention contract |
| Declined, cancelled or interrupted | Distinguish refusal, requested cancellation and confirmed termination; do not present them as success or imply that completed side effects were undone |

Keep a tool call's identity associated with its approval, execution and result, including late events and retries. A UI badge does not enforce authorization. On reconnect, reconcile with the authoritative state rather than replaying consequential actions

Describe thinking or working only as supported by supplied status events or user-visible summaries. Do not fabricate private reasoning, percentage completion or a staged sequence to make waiting look active. Decorative motion is optional and must retain meaningful static feedback under reduced motion

## Optional multi-agent presentation

Use a task list or grouped activity by default when it explains ownership, progress and blockers. Add lanes or a graph only when actual parallel work and dependencies help the user decide what to do. Keep per-task outcomes distinct from overall completion; one completed agent does not imply the entire request succeeded. Make details progressively available and retain a usable narrow-screen reading order

## Focused acceptance

Check only the affected flows: IME commit versus submit, failed-send recovery, history browsing while tokens arrive, resume-following, late layout changes, approval/decline, cancellation races, retries, keyboard access and reduced motion. Use the target runtime for input and scroll claims; a screenshot or static inspection establishes neither
