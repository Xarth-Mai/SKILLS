# Tokens, input and agent UI probes

Status: **NOT RUN** — specifications for future evaluation, not runnable fixtures or observed model results

## Worker inputs

Supply only the task and raw fixture from the selected row. Keep evaluator criteria and this file outside the evaluated runtime package; prepare independent identical fixtures for baseline and candidate

| ID | User task | Raw fixture to prepare |
| --- | --- | --- |
| G1 | 调整设置页的层级和拥挤感，保留现有品牌与功能 | Non-chat settings page with a blue brand, established radius/motion tokens, light/dark themes, nested borders, required field boundaries and visible focus styles |
| G2 | 中文选词有时会把消息发出去，选命令时也会误发送，修复输入行为 | Existing composer with IME events, Enter submit, Shift+Enter newline, suggestion menu, empty results, attached references and a failing mock submit endpoint |
| G3 | 我往上翻聊天记录时，新回复总把我拉回底部，帮我修复 | Streaming chat with caller-wired input handlers, prepend history, delayed images, expanded tool output, resize controls and two conversations; local client changes only |
| G4 | 工具栏在窄栏里挤坏了，保留所有功能 | Resizable panel inside a wide viewport, long translated labels, primary/secondary actions, keyboard focus and text enlargement controls |
| G5 | 整理工具执行卡片，让我知道发生了什么以及能做什么 | Mock events with stable call IDs: queued, approval needed, decline, running, failure, cancellation request/confirmation, late success and retry; existing authorization and duplicate-prevention contracts |
| G6 | 让聊天面板展开更连贯，并适配减少动态效果 | Installed animation engine and existing motion tokens, interruptible panel, rapid reversal, reduced-motion control and changing content; no new library needed |
| G7 | 只把发送按钮改成“发送消息” | Existing composer with correct input/focus behavior and unrelated files; exact label edit only |
| G8 | 小程序聊天滚动会跳，修好，保持原来的样式 | Mini-app source and platform scroll/input mechanisms, streaming fixture and documented emulator/device availability; no React runtime |
| G9 | 多个助手同时处理任务时，帮我看清谁还没完成 | Mock parallel task events, one success, one blocked task and one failure; narrow layout and an existing task list; no overall completion event |

## Evaluator-only acceptance

Judge actual changes and observed behavior, not whether the answer names the pattern

| ID | Required outcome | Failure signal |
| --- | --- | --- |
| G1 | Reuse brand/tokens, clarify semantic roles, retain required boundaries and focus, check supported themes | Imports Claude colors/radii or removes every nested border; adds chat features or mandatory springs |
| G2 | Composition commit does not send/select app suggestions; menu selection does not also submit; next deliberate send works; newline, empty results and failed-send draft/reference recovery remain valid | One key causes two actions, IME candidates are prevented, draft lost, or Web legacy key codes treated as universally sufficient |
| G3 | History remains stable beyond any cooldown; explicit resume follows new content; reflow/prepend and conversation changes respect reading ownership | Timer alone re-enables follow, every token restarts smooth scrolling, or late media steals reading position |
| G4 | Compression follows actual container constraints; all actions remain reachable with accessible names, usable targets and keyboard order | Viewport-only logic misses the narrow panel, icon-only actions lose names, or focus moves into hidden controls |
| G5 | Distinct truthful states, per-call approval/result association, decline prevents execution, cancellation reconciles actual outcome and retry follows existing contract | Cosmetic approval gate, fabricated success/progress, automatic consequential replay or late events applied to the wrong call |
| G6 | Existing motion reused, interruption continuous, controls usable and reduced motion preserves geometry/state | Installs a library for example presets, maps Gentle to universally calm motion or uses animation completion as business state |
| G7 | Only the requested label changes with a proportionate check | Loads a full design workflow or changes input behavior, tokens or layout |
| G8 | Uses platform mechanisms, preserves identity and reports available versus unperformed runtime checks | Pastes DOM/React Hooks or claims browser checks prove mini-app input/scroll behavior |
| G9 | Shows individual ownership/outcomes and unresolved overall work; uses the existing task list when sufficient | One agent's success marks everything complete, a graph is mandatory or unsupported reasoning is invented |

## Execution boundary

These development probes shaped the guidance and are not held-out evidence. Future comparisons should use the same model/settings, tools, raw fixtures and budgets, include unchanged passing cases and independent holdouts, and separate first-attempt from repaired results. Check implicit routing separately from forced invocation; use real target input/scroll evidence for implementation claims. Record PASS / FAIL / BLOCKED / NOT RUN with artifacts and traces rather than treating static Markdown checks as behavioral success
