# UX flows, states, and prioritization

## Model tasks, not isolated pages

Select one coherent user goal and follow it from the actual entry point to a confirmed outcome. Do not judge pages as unrelated screenshots.

For each journey, document:

1. Role and goal.
2. Preconditions and permissions.
3. Actual entry point.
4. Information visible at each step.
5. User action.
6. System response and waiting state.
7. Decisions and validation.
8. Successful end state and confirmation.
9. Useful next action.

Keep valid alternate outcomes distinct from errors. A return request, approval queue, or pending review may be its own successful journey.

## Happy Path and wireflow

Define the shortest understandable successful route under the product's real rules. Do not bypass authentication, validation, approval, payment confirmation, or permissions to reduce clicks.

For every transition, record:

- initiating control;
- destination screen or in-place state change;
- immediate feedback;
- data or context preserved;
- back, edit, retry, and cancel behavior;
- authoritative confirmation;
- analytics or audit requirements when already part of the product.

Use a wireflow when spatial context matters. Use a table when exact mappings are clearer. Avoid a diagram that merely repeats a short linear list.

## State matrix

Evaluate only states relevant to the feature, including:

| State family | Questions |
|---|---|
| Loading | Is progress truthful? Is layout stable? Can independent content appear earlier? |
| Empty | Why is it empty? Is it expected? What useful action is available? |
| Partial | Which data loaded or failed? Can the user continue safely? |
| Success | What completed? What changed? What is the next useful action? |
| Validation error | Which value is invalid? How can it be corrected without losing valid input? |
| System error | What failed? What remains saved? Can the user retry or recover? |
| Offline or timeout | Is the state detectable? Is retry safe? Could duplicate work occur? |
| Unauthorized | Is the role restricted, the session expired, or approval pending? |
| Unavailable | Is an item sold out, archived, disabled, or temporarily unavailable? |
| Repeated action | Is double submission prevented? Is the operation idempotent where needed? |
| Destructive | Is scope and consequence clear? Is confirmation or undo appropriate? |
| Long and dense content | Does the layout survive realistic names, descriptions, prices, and tables? |
| RTL and mixed language | Do direction, order, punctuation, numbers, and controls remain correct? |

For each state, define message, next action, preserved input, retry behavior, and duplicate-operation protection.

## Information architecture

- Group navigation around user goals and frequency, not internal department or database structure.
- Separate global navigation, local navigation, filters, and item-level actions.
- Make current location and available scope visible.
- Keep terminology stable across navigation, page titles, buttons, breadcrumbs, and confirmation messages.
- Avoid dead ends. Every terminal state should explain completion or offer the next relevant destination.
- Put advanced or rare options behind progressive disclosure without hiding essentials.

## PURE-inspired difficulty review

Unless qualified reviewers independently complete the formal method, describe this as a “PURE-inspired review.” Evaluate each step for:

- clarity of the next action;
- reading and comprehension;
- memory and comparison burden;
- data entry and duplication;
- unnecessary navigation or scrolling;
- waiting and uncertainty;
- error likelihood;
- recovery cost.

Use the review to compare alternatives, not to manufacture a precision score.

## Prioritization

Consider these dimensions independently:

- **Impact:** users and journeys affected; task, trust, access, or conversion consequence.
- **Evidence:** strength and reproducibility of the observation.
- **Risk:** data, permission, regression, architecture, and operational risk.
- **Implementation effort:** breadth, complexity, dependencies, and verification burden.
- **Cost:** services, infrastructure, licensing, maintenance, and support.

Do not multiply raw values when a high risk would incorrectly increase priority. Prefer high-impact, strong-evidence, reversible work. Gate high-risk changes behind explicit plans and approvals.

For each proposed improvement, include:

- problem and evidence;
- affected roles and journeys;
- proposed correction;
- expected effect and measurement;
- affected owners, files, services, or components;
- risks, dependencies, and cost;
- acceptance criteria;
- rollback method.

## Continuity checklist

During navigation and updates, preserve when relevant:

- search query and filter values;
- sort, view mode, and pagination;
- selected rows or items;
- scroll position;
- draft input and uploaded files;
- expanded details or active tabs;
- chosen language and direction;
- permission and organization context.

Do not preserve stale or sensitive data after logout, role change, tenant switch, or session expiry.
