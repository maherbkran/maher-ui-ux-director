# Web implementation quality gate

Apply this gate to the affected surface and its shared owners. Follow the project's framework and official documentation when a version-specific behavior is uncertain.

## Semantics and accessibility

- Use native semantic elements before ARIA.
- Use `<button>` for actions and `<a>` or the framework's link component for navigation.
- Give every form control a visible label or an accurate accessible name.
- Give icon-only controls an accessible name; hide decorative icons from assistive technology.
- Provide meaningful image alternatives; use empty alt text for decorative images.
- Keep headings hierarchical and provide a route to main content when the application shell warrants it.
- Make all functionality available by keyboard unless the interaction is inherently path-based; provide an equivalent whenever possible.
- Keep a visible `:focus-visible` treatment. Never remove outlines without an equivalent replacement.
- Ensure sticky headers, footers, drawers, and overlays do not cover the focused element.
- Announce important async validation, success, and error changes with an appropriate live region.
- Do not disable browser zoom.
- Test contrast for text, controls, focus, states, charts, and content over translucent surfaces.
- Do not rely on color, hover, position, or motion alone to communicate meaning.

## Forms

- Use meaningful `name`, `type`, `inputmode`, and `autocomplete` values.
- Keep labels and controls in one usable hit area for checkboxes and radios.
- Do not block paste.
- Keep submit available until the request actually starts, then prevent duplicate submission and show truthful progress.
- Place errors next to fields, summarize when necessary, and focus the first invalid field after submission.
- Preserve valid input after recoverable failures.
- Warn before discarding meaningful unsaved changes.
- Avoid autofocus on mobile and use it sparingly on desktop.

## Navigation and state

- Keep navigable states such as tabs, filters, sort, search, and pagination in the URL when deep linking and browser navigation should preserve them.
- Use links for destinations so open-in-new-tab, copy-link, and browser navigation continue to work.
- Require confirmation or a safe undo window for destructive actions based on consequence and reversibility.
- Restore context after returning from detail views when the journey requires it.
- Prevent stale async results from replacing newer search or filter results.

## Layout and content resilience

- Prefer CSS grid and flexbox to JavaScript layout measurement.
- Handle long, short, empty, localized, user-generated, and mixed-direction content.
- Let flex and grid children shrink correctly; prevent accidental page-level horizontal overflow.
- Avoid clipping focus rings, menus, tooltips, validation, and sticky content.
- Account for safe areas in full-bleed mobile layouts.
- Reserve space for images and async content to prevent layout shifts.
- Do not use fixed heights when content may grow.

## Motion and interaction

- Respect `prefers-reduced-motion` with a reduced or disabled variant.
- Animate compositor-friendly properties when possible, normally transform and opacity.
- Never use `transition: all`; name the properties.
- Keep interaction motion interruptible and responsive to new input.
- Stop or provide controls for persistent nonessential motion as required by accessibility expectations.
- Preserve tap, click, and keyboard alternatives for drag, swipe, pinch, and gesture interactions.
- Keep motion tied to state, causality, spatial change, progress, or confirmation.

## Images, media, and fonts

- Set explicit image dimensions or aspect ratio.
- Lazy-load below-fold media; prioritize only assets that materially affect the first view.
- Use responsive sources and an appropriate modern format while preserving required quality.
- Prefer compressed video with a still fallback over large animated GIFs when motion is necessary.
- Load only required font families, scripts, and weights.
- Use a suitable font-display strategy and avoid excessive preload.
- Preserve licensed use and required Arabic glyph coverage.

## Icons and materials

- Use official Phosphor components or official SVG assets for ordinary interface icons.
- Reject CSS-drawn icons, text glyph substitutes, emoji controls, and improvised SVG paths when Phosphor provides the concept.
- Keep Phosphor weight, size, color, alignment, active state, accessibility, and RTL mirroring consistent.
- Import only used icons and follow the official SSR or framework entry point for the detected stack.
- Keep Liquid Glass in a bounded control or navigation layer and provide a functional opaque fallback through progressive enhancement.
- Do not stack glass, place it beneath data or long-form content, or animate expensive blur and displacement without measurement.
- Test glass under reduced motion, reduced transparency or conservative fallback, increased contrast, dynamic backgrounds, and the target browser matrix.

## Localization and direction

- Format dates, times, numbers, currency, units, and pluralization with locale-aware APIs.
- Do not infer language from IP address alone.
- Mark brand names, codes, and identifiers that should not be translated.
- Set `dir` at the correct container level for mixed content rather than forcing one direction on every string.
- Test directional icons, breadcrumbs, steppers, tables, form adornments, and chart labels in RTL.

## Rendering and performance

- Avoid layout reads during render and repeated interleaved DOM reads and writes.
- Keep controlled input work cheap for every keystroke.
- Split routes or heavy modules when supported by measured bundle or interaction cost.
- Load expensive editors, visualizations, and media only when needed.
- Virtualize only lists large enough to justify it and preserve accessibility, selection, and keyboard behavior.
- Deduplicate requests, cancel obsolete requests, and parallelize independent work within safe service limits.
- Avoid hydration mismatches and use suppression only for genuinely unavoidable differences.

## Component and design-system integrity

- Reuse an existing owner when it expresses the decision correctly.
- Resolve tokens and aliases to their actual runtime values before declaring inconsistency.
- Do not create a new shared primitive from visual similarity alone; prove shared behavior and ownership.
- Add variants for meaningful states rather than scattered one-off overrides.
- Keep component APIs explicit enough to prevent invalid visual and behavioral combinations.

## Verification checklist

- Build, type, lint, and test commands pass for the affected scope.
- The task works with mouse, touch where relevant, and keyboard.
- Focus order and focus return are correct for dialogs, menus, and drawers.
- Loading, empty, error, offline, success, permission, and repeated-action states behave correctly.
- Desktop, 1366×768 when relevant, and representative mobile views have been visually inspected.
- Arabic RTL, English LTR, and mixed content have been exercised when supported.
- Slow network and reduced-motion behavior have been checked when the change affects them.
- Fresh screenshots show no clipping, overlap, accidental overflow, weak contrast, or hierarchy regression.
- No ordinary icon is hand-drawn or sourced from a second unapproved icon family.
- Every applicable UAE Design System guideline tab has evidence, an N/A decision, or a justified deviation.
- Liquid Glass, when present, passes the complete gate in `liquid-glass.md`.
