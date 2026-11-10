# UAE Design System review matrix

Use the current [UAE Design System guidelines](https://designsystem.gov.ae/guidelines) as a mandatory quality review matrix for UI work.

## Applicability

Apply two levels correctly:

- **Every product:** apply the universal rules for legibility, hierarchy, responsive layout, content clarity, action semantics, icon consistency, accessibility, progressive enhancement, RTL, performance, and maintainable implementation.
- **UAE government or explicitly aligned product:** also apply the current government identity tokens, approved typefaces, colour palette, components, mobile navigation and authentication rules, browser support, and any entity-specific exceptions.

Do not make a private product look governmental by automatically copying federal fonts, gold, red, green, black, navigation, or UAE PASS rules. Preserve the product's approved identity while meeting the same quality floor.

Before claiming conformance, open the live guideline pages relevant to the surface because the system can change. Record every applicable tab as passed, not applicable, or deviated with a reason.

## 1. Typography

Live guideline: https://designsystem.gov.ae/guidelines/typography

Check:

- explicit roles for headings, body, labels, metadata, actions, and data;
- legible size, weight, line height, paragraph spacing, and measure;
- consistent fallback stacks and font-loading behavior;
- correct alignment and direction for English LTR and Arabic RTL;
- responsive type that does not create oversized operational screens;
- real Arabic glyph quality and mixed-script testing;
- no arbitrary type sizes or decorative changes that weaken hierarchy.

For aligned federal projects, use the current approved typefaces and scale. The published system identifies Roboto and Inter for English, and Noto Kufi Arabic and Alexandria for Arabic. Verify the live guideline before implementation. For other projects, retain the approved brand font.

## 2. Colour system

Live guideline: https://designsystem.gov.ae/guidelines/colour-system

Check:

- product, neutral, semantic, status, focus, and data-visualization tokens;
- WCAG AA contrast for normal and large text, controls, graphics, focus, and states;
- light, dark, hover, active, selected, disabled, error, warning, and success combinations;
- information is not communicated by color alone;
- neutral surfaces preserve readability and hierarchy;
- brand combinations are intentional and do not pair competing accents;
- dynamic imagery and glass do not invalidate tested contrast.

Use exact UAE palette values only for applicable government products. Test combinations rather than assuming an approved brand swatch is accessible in every foreground/background role.

## 3. Imagery

Live guideline: https://designsystem.gov.ae/guidelines/imagery

Check:

- imagery is contextual, realistic, culturally appropriate, and consistent with the brand;
- photography, illustration, and video have a coherent style, mood, framing, and level of detail;
- the subject and user context are represented accurately;
- backgrounds are simple enough to protect hierarchy and copy legibility;
- illustrations are purposeful, simple, recognizable, high-contrast, and stylistically consistent;
- imagery is not generic filler or fabricated evidence;
- crops, responsive sources, dimensions, alt text, loading, licensing, and file size are correct;
- icons replace illustrations when the communication is small and symbolic;
- photography and illustration are not mixed randomly.

Do not generate faces, people, institutions, testimonials, or evidence that could be mistaken for real when the product requires authentic imagery.

## 4. Iconography

Live guideline: https://designsystem.gov.ae/guidelines/iconography

Read [iconography.md](iconography.md) and apply it completely.

Check:

- Phosphor is used as the standard icon family;
- symbols are familiar, contextual, and used sparingly;
- semantics, weights, sizes, alignment, states, and color are consistent;
- ordinary icons are not hand-drawn with CSS or improvised vectors;
- standalone government icons meet the current minimum size guidance, normally at least 24px;
- icon-only controls have accessible names and adequate targets;
- directional symbols mirror correctly in RTL while universal symbols remain unchanged.

## 5. Layout and spacing

Live guideline: https://designsystem.gov.ae/guidelines/layout

Check:

- the layout responds intentionally across the system's breakpoints and the project's target sizes;
- containers have deliberate maximum widths and margins; full-fluid layout is reserved for justified sections;
- grid choices reflect content relationships, using practical six-, four-, three-, or twelve-column structures where appropriate;
- column gaps and section spacing come from tokens, not arbitrary values;
- spacing adjusts by viewport while retaining optical balance;
- the first operational viewport contains useful task content;
- no accidental horizontal overflow, nested scrolling, content clipping, or oversized blank areas exist;
- orientation and large-screen behavior are tested when relevant.

The published system uses breakpoints at 640, 768, 1024, 1280, and 1536px, a typical 24px large-screen grid gap, and a structured spacing scale. Use the current project tokens when they already provide an equivalent coherent system.

## 6. Content

Live guideline: https://designsystem.gov.ae/guidelines/content

Check:

- voice is consistent and tone adapts to context;
- copy is professional, accessible, user-centered, clear, confident, and concrete;
- navigation terms remain formal or appropriately semi-formal and consistent;
- errors explain the issue and recovery without blame or raw technical codes;
- messages are short, meaningful, human, and provide direction;
- jargon, wit, idioms, hype, filler, and ambiguous CTA labels are removed;
- acronyms, numbers, dates, and terminology follow the chosen language standard;
- authenticated content can adapt to the user's actual context without exposing private data;
- Arabic is written naturally rather than translated mechanically.

Read [ux-writing.md](ux-writing.md) for the complete microcopy gate. For federal English content, follow the current UAE system's language convention, including British English where required.

## 7. Actions and input

Live guideline: https://designsystem.gov.ae/guidelines/actions

Check:

- primary, outline, soft, link, and destructive actions have clear hierarchy;
- repeated cards or rows do not contain competing solid primary buttons;
- button labels use familiar action verbs, describe the result, and normally stay under four words;
- icons appear in buttons only when they improve understanding;
- full-width buttons are limited to layouts that need a strong focal action, such as login or registration;
- links navigate and buttons change state or trigger actions;
- fields ask only for necessary information and use the correct control;
- labels, help, validation, keyboard completion, paste, autocomplete, and error recovery work;
- floating action buttons are necessary, limited, keyboard accessible, and never obscure content;
- feedback is immediate and truthful, and repeated submissions are safe.

## 8. Mobile applications

Live guideline: https://designsystem.gov.ae/guidelines/mobile-applications

Check:

- decisions are user-centered, simple, accessible, secure, consistent, and performant;
- web and native experiences use a coherent component and terminology system;
- touch targets, safe areas, keyboard, orientation, and small-screen hierarchy work;
- first-time onboarding appears only when needed and stays brief;
- transactional bottom navigation exposes three to five core destinations with recognizable icons and text labels when this pattern fits;
- the top bar preserves context and essential actions without consuming the screen;
- secondary navigation is clear and does not hide essential destinations behind excessive expansion;
- splash screens disappear as soon as the app is ready and do not mask slow startup;
- authentication protects security and explains every handoff and failure.

For UAE federal mobile apps, apply current UAE PASS, biometric, passcode, onboarding, and navigation requirements exactly. Do not impose these identity and authentication rules on unrelated private products.

## 9. Accessibility

Live guideline: https://designsystem.gov.ae/guidelines/accessibility

Check:

- WCAG 2.2 Level AA is the working target unless a stricter approved requirement applies;
- semantic HTML, headings, landmarks, labels, accessible names, live regions, and ARIA states are correct;
- all tasks work by keyboard with visible focus and logical order;
- screen-reader output and focus return work for dialogs, menus, drawers, validation, and async updates;
- contrast, zoom, reflow, text spacing, target size, reduced motion, reduced transparency, and increased contrast are supported;
- images, icons, charts, audio, and video have equivalent information;
- accessibility is inherent in the product, not delegated to an overlay plugin;
- people of determination and elderly users can complete the complete task, not only reach the page.

## 10. Technical guidance

Live guidelines:

- Advanced CSS: https://designsystem.gov.ae/guidelines/advanced-css
- Frontend development: https://designsystem.gov.ae/guidelines/frontend-development
- Technical coding: https://designsystem.gov.ae/guidelines/technical-coding
- API-first applications: https://designsystem.gov.ae/guidelines/api-first-applications

Check:

- build a semantic functional baseline, then progressively enhance;
- use `@supports` and graceful degradation for advanced CSS and Liquid Glass;
- account for orientation, print, contrast, motion, input modality, and other environmental media features;
- use logical CSS properties for RTL and avoid left/right duplication;
- keep components single-purpose, isolated, reusable, typed where appropriate, and documented through the repository's existing system;
- extend current design-system components before rewriting them;
- avoid hard-coded colors and layout values when tokens exist;
- optimize bundles, media, fonts, third parties, caching, and Core Web Vitals based on evidence;
- preserve API contracts, security, validation, error semantics, and separation of UI from business logic;
- test the actual browser and device matrix and provide fallbacks instead of blocking users by browser detection.

## Required conformance record

For a broad audit or redesign, include:

| Guideline | Status | Evidence | Decision or deviation |
|---|---|---|---|
| Typography | Pass / Fail / N/A | Screen, token, or file | Applied rule or justified exception |
| Colour system | Pass / Fail / N/A | Contrast and token evidence | Applied rule or justified exception |
| Imagery | Pass / Fail / N/A | Asset and rendered evidence | Applied rule or justified exception |
| Iconography | Pass / Fail / N/A | Library and component evidence | Applied rule or justified exception |
| Layout and spacing | Pass / Fail / N/A | Viewport and token evidence | Applied rule or justified exception |
| Content | Pass / Fail / N/A | Exact strings and states | Applied rule or justified exception |
| Actions and input | Pass / Fail / N/A | Controls and flow evidence | Applied rule or justified exception |
| Mobile applications | Pass / Fail / N/A | Device and state evidence | Applied rule or justified exception |
| Accessibility | Pass / Fail / N/A | Tool and manual evidence | Applied rule or justified exception |
| Technical guidance | Pass / Fail / N/A | Source and runtime evidence | Applied rule or justified exception |

Do not mark “Pass” from code inspection alone when the rule requires rendered, interaction, device, accessibility, or performance evidence.
