# Platform-aware design and acceptance evidence

Use when adapting guidance across runtimes or reviewing a UI with limited target access. Preserve the product goal while verifying the target's APIs, input, styling, and rendering behavior

## Three questions before choosing an implementation

1. **What actually renders and owns the chrome?** Browser DOM, mini-app WebView, native controls, operating-system shell, terminal or game engine may differ in layout, typography, access and rendering behavior.
2. **Which platform mechanisms are guaranteed?** Confirm the installed SDK, component framework, supported style properties, input events, navigation, keyboard and accessibility APIs from source or version-matched documentation.
3. **What evidence is available?** Distinguish code inspection, unit/component tests, simulated/browser rendering, official IDE emulator/preview, physical devices, instrumented traces and user comprehension tests.

A substitute preview can reveal obvious layout defects. It is *not* proof of system chrome, real hit targets, hardware back navigation, keyboard behavior, actual motion smoothness or accessibility.

## Web

Inspect actual semantic HTML, focus order, reduced-motion behavior, responsive container widths, long content, browser zoom and keyboard input. DOM assertions prove states and event paths within that browser, not cross-browser visual fidelity or real touch. Verify newer CSS/WAAPI features against target browsers before relying on them.

## Mobile native and desktop

Start with the runtime's own navigation patterns, typography/scaling, safe areas, system accessibility preferences, gesture and pointer models, keyboard/focus rules and target devices. Spring APIs and parameter semantics differ between frameworks. Native motion and touch should be assessed on actual devices when quality claims depend on them.

## WeChat mini programs and similar hosted mini-apps

Apply this section when the target is WeChat or a similar hosted mini-app

- Confirm project root and effective source paths; distinguish source compilation from a mapped HTML approximation. Respect WXML/WXSS component/event capabilities rather than assuming direct DOM access.
- Check what the WeChat **native navigation bar/tab bar** owns, and what color, border and layout controls are actually configurable. Avoid replacing native bars with custom ones solely for decorative styling.
- Verify `rpx`/px assumptions, content container width, `safe-area` behavior, device text settings, keyboard lifting/scroll, input/textarea value reconciliation, scroll containers, picker and switch appearance, and navigation/back behavior. The `button` text box is not automatically its effective touch area.
- For `rich-text`/Markdown, test supported node/tag/style subset against the actual SDK. Preserve literal user data and safe link/HTML handling; avoid claiming browser-standard CSS support inside rich text. Test headings, lists, code, links, long lines, whitespace and nesting. Do not sacrifice original editable content to rendering convenience.
- Inspect asynchronous `setData`, lifecycle `onShow/onHide/onUnload`, request cancellation or generation checks, and stale responses. In a mini-app, a visually stable page may still overwrite a newer action due to event sequencing.
- For motion, determine whether WXSS transitions, animation APIs or Canvas suit the component. Test rapid reentry, page switches, static/reduced-motion alternatives and CPU-constrained devices; JS/CSS syntax parity with Web does not imply equivalent behavior.
- Test readable native UI at representative device widths and themes, with scaled text and a realistic keyboard. Verify tap comfort by actually activating controls. Official developer-tool compilation plus emulator/preview is stronger than WXML parser success; physical iOS and Android checks are stronger still.

## CLI and non-graphical tools

Design CLI experiences around clear state, recoverable errors, discoverable commands, consistent terminology, input safety, useful progress, completion status, and accessible output

## Evidence ladder (state what you achieved)

| Evidence | What it can support | It cannot alone establish |
| --- | --- | --- |
| Source/spec/code audit | Contract consistency, probable defects, unsupported calls | Final rendering or user comprehension |
| Unit/integration checks | Tested state transitions, format, error and data behavior | Physical accessibility and subjective quality |
| Browser/mock/mapped layout | Layout hypotheses and captured viewport under that renderer | Native widgets, platform keyboard, actual device motion |
| Target IDE emulator or preview | SDK compilation and simulated native layout/interaction | All physical touch, OS differences, screen-reader behavior |
| Physical device / instrumentation | Observed behavior on named devices, real input, smoothness | All users, devices or human understanding |
| User task observation | Task success, confusion and comprehension for observed participants | Causal claims outside the sample |

Record platform, version, viewport/device, theme, data fixture, action, result and limitations for each material claim. If the required platform is unavailable, still finish the useful safe work and mark that level `BLOCKED` or `NOT RUN`. Propose a short reproducible manual checklist rather than declaring success by analogy.
