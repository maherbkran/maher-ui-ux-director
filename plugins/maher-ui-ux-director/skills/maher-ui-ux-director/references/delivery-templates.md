# Delivery templates

Adapt the output to the user's scope. Do not generate every document for a small targeted fix.

## Compact audit

```markdown
# UI/UX audit

## Outcome
<Dominant problem and highest-leverage correction.>

## Checked scope
- Product surface:
- Roles and states:
- Viewports and languages:
- Rendered evidence:
- Source paths:

## Baseline
- Primary task:
- Current path:
- First-viewport content:
- Performance evidence:

## Findings
| Priority | Class | Location | Evidence | Harm | Remove or fix | Acceptance |
|---|---|---|---|---|---|---|

## Flow and state gaps
| Step or state | Current behavior | Required behavior | Evidence |
|---|---|---|---|

## Improve first
<One supported correction with the strongest evidence and leverage.>

## Unknowns
- <Anything not inspected or verified.>
```

## Implementation batch

```markdown
# Implementation batch: <journey or surface>

## Problem and evidence
- Problem:
- Evidence:
- Affected roles and journey:

## Scope
- Included:
- Excluded:
- Product rules and contracts preserved:

## Design decision
- Information hierarchy:
- Components and tokens:
- States and copy:
- Responsive and RTL behavior:

## Technical change
- Files and owners:
- APIs, data, or queries:
- Dependencies:
- Rollback:

## Acceptance criteria
- [ ] <Observable result>

## Verification
- Commands and tests:
- Viewports and states:
- Before/after evidence:
- Performance comparison:
- Not tested and why:

## Remaining risks
- <Risk or none known>
```

## Full program deliverables

Use these only for a broad audit and implementation program:

1. **Unified UX and performance audit**
   - stack and architecture discovered;
   - UI, journey, and performance baseline;
   - evidence-backed causes;
   - facts separated from hypotheses and unknowns.

2. **Prioritized improvement roadmap**
   - impact, evidence, risk, effort, cost;
   - scope, dependencies, approval gates, acceptance, and rollback.

3. **UX flows and design system**
   - Happy Paths, wireflows, alternatives, and state matrix;
   - design tokens, component rules, content rules, Phosphor icon mapping, and Liquid Glass limits;
   - UAE Design System tab-by-tab conformance record with evidence or justified deviations.

4. **Implementation batches**
   - each batch's changes, owners, tests, results, rollback, and open issues.

5. **Performance benchmark**
   - comparable conditions, samples, tools, raw values, and limitations.

6. **Final QA and regression report**
   - functional, visual, accessibility, performance, permission, data-isolation, and stability results.

7. **Before and after evidence**
   - equivalent data, role, state, language, theme, and viewport;
   - useful first-viewport content, recovered space, action clarity, journey improvements, state feedback, and measured performance.

8. **Final optimization summary**
   - completed outcomes, evidence, omitted work, remaining risks, and prioritized future recommendations.

## Final response after implementation

Lead with the shipped outcome, then state:

- what materially changed;
- how it was verified;
- measured before/after results when comparable;
- files or surfaces affected;
- remaining limitations or approval gates.

Avoid narrating every internal step. Do not describe a recommendation as implemented or a compile check as visual approval.

## Evidence rules

- Use screenshot pairs only when they show the same role, data, state, language, theme, and viewport.
- Name the browser, viewport, device or emulation, build mode, and cache condition for performance comparisons.
- Link findings to actual files and lines when the source is available.
- Record typography, colour, imagery, iconography, layout, content, actions and input, mobile, accessibility, and technical-guidance status for broad UI work.
- For glass, record functional layer, variant, fallback, contrast, accessibility settings, browser matrix, and measured performance.
- For icons, record the official Phosphor source, weight and size tokens, accessible names, RTL behavior, and optimized import path.
- Treat missing access as a limitation, not as proof that a problem does or does not exist.
- Report tests exactly as run. Do not infer browser, role, data-volume, or production coverage.
