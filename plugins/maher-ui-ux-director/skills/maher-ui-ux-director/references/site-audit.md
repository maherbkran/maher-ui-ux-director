# Full-site audit and route coverage

Use this workflow whenever the user requests work on a website, web application, portal, dashboard, or repository without explicitly restricting the scope to one page, route, component, or journey.

## Default scope

Treat the complete accessible product as the target. Do not reduce an unqualified website request to the home page, dashboard, or a few visually interesting screens.

If the current Codex workspace contains a web project, use it as the target automatically. Do not ask for a URL or screenshot before inspecting the repository, route definitions, scripts, environment guidance, and runnable application.

Ask for a missing target only when there is no usable project, live URL, local run path, or attached artifact.

## Discover the complete inventory

Reconcile evidence from every available source:

1. Framework route directories and router configuration.
2. `sitemap.xml`, sitemap indexes, and `robots.txt` declarations.
3. Global navigation, sidebars, footers, breadcrumbs, tabs, command menus, and in-product links.
4. Authentication, role, tenant, feature-flag, and locale gates.
5. CMS collections, API-backed slugs, dynamic parameters, and generated routes.
6. Redirects, error routes, legal pages, onboarding, account, settings, and utility surfaces.
7. Existing tests, stories, design files, analytics names, and product documentation when available.

Deduplicate aliases and redirects while retaining their behavior. Record routes that exist in code but are unreachable from navigation, and links that point to missing routes.

## Build the route matrix first

Create or maintain a working inventory with at least:

| Route or family | Page/template | Entry point | Role/access | Dynamic parameters | Languages/themes | Key states | Source evidence | Render status |
|---|---|---|---|---|---|---|---|---|

Classify each entry as inspected, representative-family inspection, blocked, redirected, duplicate, obsolete, or out of scope by explicit user instruction.

Do not publish a full-site conclusion until the inventory is reconciled against the available route sources.

## Inspect breadth and depth

For every distinct page or route family, inspect:

- shared header, navigation, footer, sidebars, overlays, and responsive shell;
- information hierarchy, content density, primary and secondary actions;
- loading, empty, partial, success, validation, error, unauthorized, and long-content states when relevant;
- desktop and representative mobile behavior;
- Arabic RTL, English LTR, and mixed-direction content when supported;
- light, dark, and other product themes when supported;
- keyboard, focus, semantics, contrast, motion, and touch behavior;
- shared component and token owners in source code;
- performance signals that materially affect the journey.

Follow primary journeys across routes. A route inventory without journey testing is not a product audit, and a journey review that ignores the remaining sitemap is not a full-site audit.

## Handle large and dynamic products

Enumerate all route families. For unbounded dynamic records, inspect representative instances that cover materially different layouts and states, such as short and long content, empty and populated data, different permissions, and error conditions.

Do not crawl infinite calendars, pagination, search combinations, filter permutations, or every database record. State the sampling rule and preserve the full route-family inventory.

When the site is too large for one safe implementation batch, complete the inventory and audit first, then divide implementation by shared shell, route family, or user journey. Do not present the first batch as completion of the whole site.

## Coverage gate

Before final delivery, report:

- total routes and route families discovered;
- inspected, representative, blocked, redirected, duplicate, and excluded counts;
- roles, languages, themes, states, and viewports actually exercised;
- missing credentials, data, services, or environments;
- remaining routes or journeys and the reason they remain.

Use “full-site audit” only when every accessible route or distinct route family has an evidence-backed disposition in the coverage matrix.
