# Interface standard

## Product posture

Default to **compact, clear, refined, task-focused** interfaces with selective visual effects. A screen should answer immediately:

1. Where am I?
2. What matters now?
3. What needs attention?
4. What is the primary available action?
5. What will happen after I use it?

Large elements and empty space must earn their footprint. Density means showing more useful information with strong hierarchy, not shrinking text or crowding controls.

## Respect the product

- Derive decisions from the product domain, its users, real tasks, content, data, permissions, and brand.
- Preserve approved logos, imagery, colors, and product language. Improve how they are applied.
- Use the existing typeface when it is approved and fit for purpose. For applicable UAE government products, use the current UAE Design System typefaces. For other products with no Arabic type system, IBM Plex Sans Arabic is a preferred candidate, not an automatic replacement.
- Keep public marketing pages, transactional product screens, and admin workspaces distinct. A spacious campaign layout is not a dashboard layout.
- Never import features from a reference product merely because its visual treatment is useful.

## Layout and first viewport

- Put page identity, essential context, and the primary action in a compact header.
- Show useful task content within the first desktop viewport, especially at 1366×768.
- Remove fixed heights and `min-height` rules that create unexplained voids.
- Group by meaning and interaction. Do not wrap every group in a bordered rounded rectangle.
- Choose rows, lists, tables, sections, split views, drawers, and cards based on the task.
- Use columns when they improve comparison or use available width. Do not create columns merely to fill space.
- Put search, filters, sorting, view settings, and bulk actions in a coherent toolbar.
- Keep decision-critical information visible; reveal secondary details progressively.
- Avoid nested scrolling. Use natural page scrolling unless an established workspace pattern requires a bounded region.
- Keep sticky controls minimal and ensure they never obscure focused or selected content.
- Preserve list context, filters, selection, pagination, and scroll position across detail navigation when the workflow benefits.

## Density and sizing

Use the project's existing tokens when coherent. If no usable scale exists, establish one before broad implementation.

- Use a small, consistent spacing scale; reserve the largest gaps for genuine section boundaries.
- Keep heading size proportional to product work, not to marketing spectacle.
- Use compact desktop controls while maintaining legibility, focus treatment, and an adequate hit area.
- On touch devices, preserve a comfortable interactive envelope even when the visible control is compact.
- Keep badges visually subordinate to the values and actions they qualify.
- Avoid full-width buttons unless the layout or mobile task genuinely benefits.
- Avoid one radius, shadow, or elevation on every component. Surface treatment should encode hierarchy.
- Never “fix” density by reducing body text, line height, or contrast below comfortable reading.

## Typography

- Define explicit roles for page title, section title, body, label, helper, metadata, table value, and numeric data.
- Use one family or a deliberate two-family pairing. Do not switch typefaces for novelty.
- Use sentence case unless the language or brand requires otherwise.
- Avoid decorative eyebrow labels, tracked all-caps text, monospace metadata, or a highlighted single word unless they serve this specific product.
- Keep measure readable. Avoid long centered paragraphs and forced line breaks.
- Use tabular numerals for aligned quantities, prices, dates, and comparison columns where supported.
- Align Arabic, English, numbers, currency, codes, and units intentionally; test mixed-direction strings with real examples.

## Iconography

- Use Phosphor for new and redesigned interface icons; follow [iconography.md](iconography.md) completely.
- Never approximate common icons with CSS strokes, pseudo-elements, triangles, Unicode arrows, emoji, or improvised SVG paths.
- Keep one icon family, one semantic mapping, and a deliberate weight and size strategy per surface.
- Use a visible text label for unfamiliar, primary, destructive, or navigation actions.
- Give icon-only controls an accessible name and adequate target; keep decorative icons hidden from assistive technology.
- Mirror only direction-dependent icons in RTL.
- Reuse official Phosphor components or raw assets and optimize imports for the detected stack.

## Components

### Buttons and controls

- Distinguish primary, secondary, tertiary, and destructive actions.
- Label actions by their result: “Save changes,” “Approve return,” or “Download invoice,” not “Continue” or “Submit” when a specific outcome is known.
- Match icon size, label size, padding, and control height.
- Design hover, active, focus-visible, disabled, loading, and success or error feedback.
- Keep one clear primary action per local decision area unless the task genuinely has equal branches.

### Forms

- Keep labels visible. Use placeholders for examples, not as the only label.
- Group fields according to the user's decision model, not the database schema.
- Put validation near the field and preserve valid input after a recoverable error.
- Focus the first invalid field after failed submission and explain the correction.
- Warn about unsaved changes when navigation would discard meaningful work.

### Tables, lists, and data

- Align text, numbers, prices, dates, and status consistently.
- Make rows easy to scan and compare. Preserve necessary density without hiding decision-critical data.
- Use clear column headers, predictable row actions, and stable column widths where appropriate.
- Keep statuses small, readable, and consistent. Do not rely on color alone.
- Use pagination, progressive loading, or virtualization based on actual data size and interaction needs.
- Keep bulk selection and bulk actions close to the selected set and visibly scoped.

### System states

- Standardize loading, empty, partial, error, offline, success, permission, and expired-session states.
- Pair each state with the next useful action when one exists.
- Use skeletons only when their shape approximates stable content and the delay cannot be removed.
- Reserve layout space to avoid shifts. Never use animation to disguise a blocked or slow operation.

## Selective Liquid Glass

Read [liquid-glass.md](liquid-glass.md) completely before using glass. Use it only after hierarchy and layout are correct. Suitable targets include an active tab indicator, toggle, slider, compact control cluster, or navigation layer that needs separation.

- Keep medical, financial, order, inventory, price, and table data on stable high-legibility surfaces.
- Avoid stacked transparent layers, glass on every card, or large blurred regions.
- Keep glass in the functional control and navigation layer, not the content layer. Never stack glass on glass.
- Do not enlarge a component merely to display the effect.
- Maintain sufficient contrast in light and dark themes and over every supported background.
- Measure scroll and interaction cost from blur, filters, backdrop rendering, and refraction.
- Respect reduced motion, reduced transparency, and increased contrast; provide a visually coherent opaque fallback when unsupported or too expensive.
- Use regular material for text-heavy or variable backgrounds. Use clear material only over rich media when a dimming layer is acceptable and foreground content remains bold and legible.
- Use feature detection and verify Chrome, Safari, Firefox, iOS, and Android behavior before claiming support.
- Prefer a simple CSS treatment over a large dependency for a limited effect.

## Responsive behavior

- Design adaptations, not scaled-down desktop screenshots.
- Prioritize content and actions per viewport; collapse or relocate secondary controls deliberately.
- Test long Arabic, English, mixed-direction content, realistic product names, dense tables, sparse data, and error messages.
- Avoid hidden essential actions, horizontal page overflow, clipped content, unreachable focus, and sticky elements that consume the mobile viewport.
- Preserve native zoom and platform navigation gestures.
