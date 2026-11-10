# Anti-AI UI audit

## Principle

Do not try to prove whether AI created a design. Diagnose visible and implemented consequences. A familiar technique is not a defect by itself; a pile of defaults with no product-specific reason is.

Classify a candidate as:

- **Quality defect:** established usability, accessibility, responsive, content, interaction, or runtime problem.
- **Generic-pattern defect:** repeated or decorative default that provides no useful information, action, state, hierarchy, or brand meaning.

Require concrete evidence from a rendered state, interaction, component, token, source path, or line of copy.

## Removal test

For each candidate:

1. Name the role it performs.
2. Remove it mentally or in a reversible prototype.
3. If clarity improves and no role is lost, remove or consolidate it.
4. If a role is lost, keep the role and make the smallest correction.
5. Introduce a replacement only when deletion creates a real gap.

Prefer subtraction, hierarchy, alignment, and better content before decorative restyling.

## Common patterns to inspect

### Cardification and container nesting

- Nearly every block is a rounded card, regardless of meaning.
- Cards contain cards, bordered shells, tinted panels, and pills without adding hierarchy.
- Identical icon-title-description tiles are used for unrelated content.
- One radius, shadow, border, and padding recipe is applied everywhere.
- A table or list is fragmented into many cards and becomes harder to compare.

### Oversized dashboard chrome

- A greeting, page title, statistic, or banner consumes the first viewport before task content appears.
- Large headings, illustrations, and empty padding mimic a landing page inside an operational app.
- The primary action is separated from the data it affects.
- Multiple summary cards repeat information already visible in the table or list.

### Template typography

- An all-caps eyebrow appears above every heading.
- One word in each headline receives a gradient, italic, or accent color without semantic reason.
- Small monospace labels, dotted metadata strings, arrows appended to every link, or numbered `01 / 02 / 03` sections appear regardless of content.
- Long centered paragraphs, ornamental type, or forced line breaks weaken scanning.
- Type roles, weights, and sizes are inconsistent or fail to reflect task importance.

### Decorative stacking

- Glow, gradient, glass, grid, noise, particles, floating orbs, beams, borders, and shadows perform the same decorative job simultaneously.
- Glass appears inside content cards, underneath long text or data, on top of other glass, or without an opaque accessibility fallback.
- Warm editorial cream and serif, near-black with neon accent, purple gradient, or glass-on-dark appears without a link to the product.
- Browser chrome, device mockups, charts, or dashboards are decorative fiction rather than meaningful product evidence.
- The background competes with controls or data.

### Repetitive motion

- Every section fades and slides into view.
- Every card lifts, scales, glows, or rotates on hover.
- Motion delays access, moves targets, blocks input, or restarts mechanically.
- Animation communicates no state, spatial relationship, causality, progress, or confirmation.
- Reduced-motion preferences are ignored.

### Pill and badge inflation

- Most labels, tabs, metadata, and actions are pills.
- Large colored badges overpower the value they describe.
- Status is communicated by color alone.
- A badge restates a nearby heading or obvious state.

### Improvised iconography

- Common interface icons are assembled from CSS lines, borders, pseudo-elements, circles, or triangles.
- Unicode arrows, emoji, text glyphs, or hand-drawn SVG paths imitate icons already available in Phosphor.
- Several icon families, weights, stroke widths, bounding boxes, or metaphors appear in one surface.
- Icons are decorative, unlabeled, misaligned, inaccessible, or mirrored incorrectly in RTL.
- Icon buttons use tiny visible glyphs without an adequate target or accessible name.

Replace ordinary icons with the official Phosphor component or SVG asset. Preserve custom vectors only for approved brand marks or a documented domain-specific gap.

### Generic content structure

- A page follows hero, logos, three benefits, testimonial, pricing, FAQ, and final CTA without regard to the actual journey.
- Repeated section labels and CTA blocks restate nearby text.
- Fake customer logos, metrics, activity, testimonials, charts, avatars, awards, or ratings appear as proof.
- Placeholder content has uniform length and hides real layout stress.

### Weak interaction and hierarchy

- Several actions compete as primary.
- Important actions are icon-only, hidden on hover, or visually weaker than decoration.
- Labels describe implementation terms rather than user goals.
- Loading, empty, error, permission, and success states are missing or contradictory.
- Spacing, color, radius, icon style, and alignment vary accidentally.
- Responsive behavior clips, overlaps, overflows, or hides essential content.

## Product-specificity test

Ask of every strong visual choice:

- What in the product's domain, audience, content, task, or brand caused this decision?
- Would the same choice appear unchanged in an unrelated finance, education, wedding, healthcare, or productivity app?
- Does the choice improve comprehension or interaction, or only make the screenshot look “designed”?

Revise choices that have no product-specific answer.

## Prioritization

- **P0:** blocks task completion, breaks access, misrepresents proof, or creates serious data or permission risk.
- **P1:** materially harms comprehension, trust, navigation, interaction, or recovery.
- **P2:** repeated generic pattern or inconsistency that weakens hierarchy, density, or identity.
- **P3:** isolated polish issue with limited impact.

Group symptoms by root cause. Report the five to eight highest-impact findings by default rather than an exhaustive list of tiny offenses.

## Evidence format

For every finding, record:

| Field | Required content |
|---|---|
| Priority | P0–P3 |
| Class | Quality defect or generic-pattern defect |
| Location | Screen, state, viewport, component, or source path |
| Evidence | What was actually observed |
| Harm | Effect on task, comprehension, trust, access, or performance |
| Correction | Remove, consolidate, or smallest supported fix |
| Acceptance | Observable condition that proves the correction |

Mark unavailable states and unverified behavior as unknown.
