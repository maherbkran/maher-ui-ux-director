# Strict Liquid Glass standard

Read this file completely before proposing or implementing glass. Liquid Glass is a functional material layer, not a decoration preset.

## 1. Placement and hierarchy

- Place glass in the top functional layer for navigation and controls that float above content.
- Suitable uses include compact tab or selection indicators, toggles, sliders, transient control clusters, toolbars over media, and navigation layers that need separation.
- Keep content surfaces solid or use restrained standard materials. Do not use Liquid Glass for tables, forms, product data, prices, medical or financial information, order rows, long text, or ordinary content cards.
- Do not place glass inside glass or stack overlapping glass surfaces.
- Do not enlarge a component, add empty space, or restructure a screen merely to showcase the effect.
- Use the effect only after layout, hierarchy, states, and accessibility work without it.

## 2. Material variants

Use one coherent variant strategy per surface.

### Regular

Use the regular treatment by default when:

- text, labels, icons, or several controls sit on the material;
- the underlying background can threaten legibility;
- the component is a toolbar, navigation bar, popover, alert, or larger control group.

Regular glass must blur or tone the background enough to preserve foreground clarity.

### Clear

Use clear glass only when all conditions are true:

1. the component floats over visually rich media such as a photo or video;
2. a dimming layer will not damage the underlying content experience;
3. foreground content is bold, bright, and simple enough to remain legible.

If the background is bright, test a dark scrim around 35% opacity behind the clear material. If the background is already dark and legibility passes, do not add unnecessary dimming.

Do not mix clear and regular variants within one control family or local surface unless a documented functional reason and visual test justify it.

## 3. Color and content

- Glass has no default decorative color; let the underlying content influence it.
- Tint sparingly for a primary action, selected item, or meaningful status.
- When emphasizing a primary action, tint the material background rather than only a thin icon or label.
- Do not tint every control. Multiple colored glass elements flatten priority and reduce legibility.
- Keep symbols and labels monochromatic by default and adapt their contrast to the background.
- Avoid lightweight colored text and tiny colored glyphs on glass.
- Maintain balanced brightness; avoid bright moving glass on very dark backgrounds.
- Never rely on glass color alone to communicate selection, status, or focus.

## 4. Shape and optical treatment

- Match shape to component anatomy. Use capsules for compact pill-like controls and rounded rectangles for larger controls where a capsule would look distorted.
- Keep curvature, radius, rim, and highlight consistent across the material family.
- Use a restrained edge highlight and shadow to separate the control from changing backgrounds.
- Keep refraction subtle enough that labels, values, and targets remain stable and readable.
- Use gentler refraction where precise values must remain readable, such as sliders.
- Avoid fake “glass” made only from low-opacity white, large blur, and a generic shadow when it has no optical hierarchy or interactive behavior.

## 5. Progressive web implementation

Start with a fully functional opaque or high-legibility fallback.

1. Build semantic HTML, real controls, focus states, and the complete journey without glass.
2. Define material tokens for fallback surface, opacity, blur, saturation, rim, highlight, shadow, tint, radius, motion, and contrast mode.
3. Enhance through `@supports` for `backdrop-filter`, SVG filter, or another required feature.
4. Keep the fallback visually intentional rather than a broken approximation.
5. Verify Chrome, Safari, Firefox, iOS, Android, and the project's actual browser matrix.

Do not ship a Chromium-only experiment as a universal production treatment. Feature detection and graceful degradation are mandatory.

## 6. Refraction implementation

Use the simplest implementation that achieves the approved role.

### CSS material

Prefer a bounded CSS material for navigation and controls when blur, tint, rim, and highlight are enough. Keep filter regions small and avoid full-screen animated backdrop blur.

### SVG displacement

Use `feDisplacementMap` only for a focused lens or control where real refraction materially improves the interaction.

- Encode horizontal displacement in the red channel and vertical displacement in the green channel; keep the neutral value centered.
- Keep displacement and chromatic fringe subtle.
- Reuse a displacement map while a lens only changes position.
- Regenerate the map only when shape or size changes.
- Exploit symmetry when generating rounded-rectangle maps instead of recalculating every quadrant independently.
- Bound the SVG filter region to the lens and required highlight area.
- Preserve live DOM interactivity, selection, and click targets.

### Safari and media constraints

- Safari can cache an SVG filter result by ID. When the displacement map changes, use a safe invalidation strategy such as a fresh filter ID and test for stale frames.
- Keep refracted DOM size and complexity conservative because Safari may break or drop oversized filter inputs.
- Scope specular work to the smallest region that renders correctly in the target browser.
- Live video and canvas may require a different rendering path such as WebGL. Do not introduce WebGL for a decorative flourish without a measured, approved need.
- If cross-browser parity is too costly, reduce the effect to a stable CSS material rather than shipping inconsistent behavior.

## 7. Interaction and motion

- Make the material respond only to meaningful pointer, touch, selection, drag, or focus changes.
- Prefer moving a stable lens with transform or position over recomputing blur or displacement every frame.
- Keep animations interruptible and preserve real control state.
- Do not animate every glass surface on page load or hover.
- Respect reduced motion. Replace morphing, spring, and refraction animation with a stable selected or active treatment.
- Never let motion move the hit target away from the pointer or delay the action.

## 8. Accessibility and adaptive fallback

- Test foreground contrast over the darkest, lightest, and busiest supported backgrounds.
- Provide a stronger scrim or opaque material when dynamic background contrast cannot be guaranteed.
- Support increased contrast, reduced transparency, reduced motion, forced-colors, light, and dark modes where the platform exposes them.
- Do not rely solely on a transparency preference that lacks support across the browser matrix; keep an explicit conservative fallback.
- Preserve labels, accessible names, keyboard navigation, focus-visible, touch targets, and screen-reader feedback independently of the visual effect.
- Keep content understandable when blur, transparency, tint, displacement, and animation are disabled.

## 9. Performance budget

- Limit simultaneous glass effects to the smallest set of important controls. Define the screen budget before implementation.
- Avoid large filter regions, full-screen blur, multiple overlapping backdrop filters, and rapidly changing backgrounds beneath glass.
- Do not regenerate displacement maps while only moving the lens.
- Avoid updating spatially distant glass elements through one oversized shared container.
- Animate compositor-friendly properties where possible and do not apply `will-change` globally.
- Measure scroll and drag smoothness, frame time, long tasks, paint and composite cost, GPU or memory pressure when available, and input response on representative mobile hardware.
- Test moving media, dense DOM, RTL, and low-power or thermally constrained devices.
- Remove, simplify, or disable the effect when it causes missed frames, delayed input, visual artifacts, excess memory, or unreadable content.

## 10. Required test matrix

- regular and clear variants used in the product;
- light, dark, bright, low-contrast, and visually busy backgrounds;
- default, hover, focus-visible, pressed, selected, disabled, loading, and error states;
- Arabic RTL, English LTR, numbers, and mixed-direction labels;
- keyboard, mouse, touch, and coarse pointer;
- reduced motion, reduced transparency or opaque fallback, increased contrast, and forced-colors where supported;
- Chrome, Safari, Firefox, iOS, Android, and target in-app browsers;
- normal and low-power mobile conditions;
- scroll, resize, orientation change, theme change, and dynamic content updates.

## 11. Acceptance gate

- [ ] Glass is confined to an appropriate functional layer.
- [ ] No glass-on-glass or uncontrolled variant mixing exists.
- [ ] Clear glass satisfies all three eligibility conditions.
- [ ] Opaque fallback and feature detection work.
- [ ] Text, icons, focus, and state pass contrast and legibility checks over every supported background.
- [ ] Reduced-effects and accessibility settings remain usable.
- [ ] Cross-browser and mobile behavior has been observed, not assumed.
- [ ] Filter regions and concurrent effects stay inside the measured performance budget.
- [ ] The underlying task remains complete when the effect is disabled.

If any gate fails, ship the stable fallback or reduce the effect rather than weakening readability, interaction, or performance.
