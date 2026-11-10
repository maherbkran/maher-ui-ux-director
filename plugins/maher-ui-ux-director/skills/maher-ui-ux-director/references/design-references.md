# Design and implementation reference map

Use references to calibrate a decision, not to copy a product's identity. Open the actual page, inspect relevant images or examples, and state when access fails. For version-sensitive implementation details, prefer the official documentation for the detected stack.

## Distinctive design and anti-pattern review

- Anthropic Frontend Design skill: https://github.com/anthropics/skills/tree/main/skills/frontend-design
- Frontend Craft: https://github.com/nattergabriel/frontend-craft
- UX/UI Skills: https://github.com/taylorwinfield/ux-ui-skills
- Audit AI Design Slop: https://www.ui-skills.com/skills/mengto/audit-ai-design-slop
- Vercel Web Interface Guidelines: https://github.com/vercel-labs/web-interface-guidelines
- OpenAI Frontend App Builder: https://github.com/openai/plugins/tree/main/plugins/build-web-apps/skills/frontend-app-builder

Use these for deliberate visual direction, removal-first anti-pattern review, design-system grounding, interaction states, accessibility, and browser verification. Resolve conflicts in favor of the user's brief, current product truth, and verified runtime evidence.

## UX writing

- Cursor Unslop: https://www.ui-skills.com/skills/cursor/unslop

Use it only for prose and microcopy. It does not evaluate layout, hierarchy, accessibility, interaction, responsiveness, or frontend code.

## UAE Design System and iconography

- Complete guideline index: https://designsystem.gov.ae/guidelines
- Typography: https://designsystem.gov.ae/guidelines/typography
- Colour system: https://designsystem.gov.ae/guidelines/colour-system
- Imagery: https://designsystem.gov.ae/guidelines/imagery
- Iconography: https://designsystem.gov.ae/guidelines/iconography
- Layout and spacing: https://designsystem.gov.ae/guidelines/layout
- Content: https://designsystem.gov.ae/guidelines/content
- Actions and input: https://designsystem.gov.ae/guidelines/actions
- Mobile applications: https://designsystem.gov.ae/guidelines/mobile-applications
- Accessibility: https://designsystem.gov.ae/guidelines/accessibility
- Advanced CSS: https://designsystem.gov.ae/guidelines/advanced-css
- Frontend development: https://designsystem.gov.ae/guidelines/frontend-development
- Technical coding: https://designsystem.gov.ae/guidelines/technical-coding
- API-first applications: https://designsystem.gov.ae/guidelines/api-first-applications
- Phosphor Icons: https://phosphoricons.com/
- Official Phosphor repositories: https://github.com/phosphor-icons

Use `uae-design-system.md` as the mandatory review matrix and `iconography.md` as the implementation standard. Apply exact federal identity rules only to applicable UAE government work; apply the universal quality rules to every product.

## Product-interface calibration

- Linear design refresh: https://linear.app/now/behind-the-latest-design-refresh
- Shopify Admin redesign: https://www.shopify.com/blog/admin-new-look
- Horizon eCommerce case study: https://www.fourmeta.com/projects/horizon
- Intercom information architecture: https://www.intercom.com/blog/designing-for-clarity-restructuring-intercoms-information-architecture
- Atlassian typography at scale: https://www.atlassian.com/blog/how-we-build/implementing-typography-at-scale-the-journey-behind-the-screens

Study density, hierarchy, navigation, workspace structure, filters, tables, typography, and responsive continuity. Do not import features or reproduce a brand.

## Journeys and validation

- Userpilot Happy Path: https://userpilot.com/blog/happy-path/
- Nielsen Norman Group Wireflows: https://www.nngroup.com/articles/wireflows/
- Nielsen Norman Group PURE: https://www.nngroup.com/articles/pure-method/
- Zeplin Happy Path: https://blog.zeplin.io/collaboration/what-is-the-happy-path/
- Figma UX validation: https://www.figma.com/resource-library/ux-validation/

Use these to model end-to-end tasks, transitions, alternatives, states, effort, and early validation. Do not describe a heuristic review as user research or a formal PURE evaluation.

## Glass and materials

- Aave Labs, Building Glass for the Web: https://aave.com/design/building-glass-for-the-web
- Liquid Glass with CSS and SVG: https://kube.io/blog/liquid-glass-css-svg/
- Apple Human Interface Guidelines, Materials: https://developer.apple.com/design/human-interface-guidelines/materials
- Apple Liquid Glass overview: https://developer.apple.com/documentation/technologyoverviews/liquid-glass
- Apple Adopting Liquid Glass: https://developer.apple.com/documentation/technologyoverviews/adopting-liquid-glass
- Apple Applying Liquid Glass to custom views: https://developer.apple.com/documentation/swiftui/applying-liquid-glass-to-custom-views

Read `liquid-glass.md` completely. Use glass as a bounded functional material for suitable navigation and controls. Validate variant choice, contrast, opaque fallback, reduced effects, browser support, filter bounds, repaint cost, and representative mobile performance.

## Source-use rules

- Prefer primary or official sources for technical facts.
- Verify current guidance when libraries, browsers, accessibility expectations, or APIs may have changed.
- Cite the exact source near any external claim in a user-facing research report.
- Paraphrase; do not reproduce large portions of third-party material.
- Preserve source licenses and attribution when reusing code or assets.
