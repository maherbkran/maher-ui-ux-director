# Phosphor iconography standard

## Mandatory source policy

Use [Phosphor Icons](https://phosphoricons.com/) for new and redesigned interface icons. The UAE Design System also selects Phosphor as its icon library.

Do not create ordinary interface icons with:

- CSS borders, pseudo-elements, lines, circles, or triangles;
- Unicode arrows, text glyphs, dingbats, or emoji;
- improvised SVG paths drawn by the coding agent;
- a mixture of unrelated icon libraries;
- raster screenshots of icons.

Exceptions are approved brand marks, flags, product artwork, and genuinely missing domain-specific symbols. For an exception, first search Phosphor by concept and synonym, then document why no suitable symbol exists. Reuse an approved asset or request design approval before drawing a new vector.

## Integration order

1. Inspect the repository for an existing official Phosphor integration and reuse it.
2. If Phosphor is absent and dependency installation is authorized, use the official package for the detected stack.
3. If adding a dependency is not allowed, use official raw SVG assets from `@phosphor-icons/core` or already approved project assets.
4. Do not introduce a second active icon family. Plan a bounded migration if the current surface must move to Phosphor.

Common official sources include:

- React: `@phosphor-icons/react`, not the legacy `phosphor-react` package.
- Raw SVG and catalog data: `@phosphor-icons/core`.
- Official Phosphor packages for Vue, Flutter, SwiftUI, web components, and other supported stacks.

Follow the installed version's official documentation. Do not guess an import path.

## Semantic selection

- Choose the icon by action or object meaning, not visual novelty.
- Prefer familiar symbols for search, settings, account, calendar, download, upload, edit, delete, warning, success, and navigation.
- Use the same symbol for the same concept throughout the product.
- Do not reuse one icon for unrelated actions.
- Pair unfamiliar or high-risk icons with a visible text label.
- Keep destructive icons visually and semantically distinct without relying on color alone.
- Do not use icons as decorative bullets when typography or alignment communicates the structure better.

## Weight and state system

Define one icon weight strategy per surface:

- `regular` is the default for most interface icons;
- `bold` may support small, high-emphasis controls when it matches the type weight;
- `fill` may identify a selected or active state when the same icon remains recognizable;
- `duotone` is reserved for limited illustrative or expressive use, not dense tables and toolbars;
- `thin` and `light` require explicit legibility testing and should not carry critical meaning at small sizes.

Do not mix weights randomly within one navigation bar, toolbar, table, or control family.

## Size, alignment, and hit area

- Use an icon-size token scale rather than arbitrary values.
- For UAE government surfaces, follow the current UAE Design System icon sizing and accessibility requirements; standalone icons are normally at least 24px.
- For compact private-product interfaces, a smaller glyph may be used only when it remains legible and sits inside an accessible control target.
- Align icons optically with adjacent text; do not rely only on the SVG bounding box.
- Match stroke weight to typography and control prominence.
- Keep padding consistent across icon buttons.
- Never stretch an icon or alter its aspect ratio.

## Color and styling

- Use `currentColor` so icons inherit state and theme colors.
- Let hierarchy and state tokens determine color; avoid arbitrary per-icon colors.
- Do not use multiple colors inside ordinary icons unless the approved `duotone` treatment serves a clear role.
- Provide hover, active, focus-visible, disabled, loading, selected, and destructive states at the control level.
- Do not hide low-contrast icons on glass, imagery, or tinted surfaces.

## Accessibility

- Mark decorative icons `aria-hidden="true"` and keep them out of the focus order.
- Give an icon-only button an accessible name on the button. Do not expect the icon's filename or tooltip to provide the name.
- Keep visible labels for unfamiliar, primary, destructive, or navigation actions.
- Use native buttons and links. Do not attach actions directly to a bare SVG.
- Ensure keyboard focus, touch target, contrast, and disabled states remain clear.
- Do not communicate status with icon shape or color alone when a text label is needed.

## RTL and direction

- Mirror only icons whose meaning depends on physical direction, such as back, forward, carets, and directional arrows.
- Do not mirror universal objects, logos, media controls with established meaning, clocks, search, user, lock, or other non-directional symbols.
- Use Phosphor's `mirrored` option or the framework's direction-aware component when appropriate.
- Test breadcrumbs, pagination, steppers, upload/download, undo/redo, and table sorting in both RTL and LTR.

## Performance

- Import only used icons and preserve tree shaking.
- For React, prefer individual file imports when the bundler eagerly processes the full barrel; use the official Next.js package-import optimization when applicable.
- Use the official SSR entry for React Server Components or SSR environments that require it.
- Do not ship the entire icon catalog, multiple weights for every icon, or an untrimmed icon font when only a small set is used.
- Measure build and bundle impact when introducing or migrating the library.

## Acceptance gate

- [ ] Every ordinary interface icon comes from Phosphor.
- [ ] No CSS-drawn, text-glyph, emoji, or improvised SVG substitute remains.
- [ ] One semantic concept maps to one consistent icon.
- [ ] Weight, size, color, alignment, and state follow tokens.
- [ ] Icon-only controls have accessible names and visible focus.
- [ ] Directional icons behave correctly in RTL and LTR.
- [ ] Imports are optimized for the detected stack.
- [ ] Brand or domain-specific exceptions are documented and approved.
