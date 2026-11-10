# Performance, stability, and production safety

Use this reference when performance or system behavior affects the user journey. Do not treat the list as permission to change every layer.

## Priority order

1. Data integrity, authentication, authorization, business rules, and tenant isolation.
2. User task clarity, completion, and recovery.
3. Performance and stability supporting that experience.
4. Complexity, dependencies, operational cost, and maintainability.

## Read-only discovery

Before changes:

- identify the stack, versions, rendering model, build system, backend, database, external services, hosting, workers, queues, caches, tests, and observability;
- read repository instructions and official framework documentation when compatibility is uncertain;
- determine what can be run safely and which data or access is unavailable;
- avoid installing dependencies, running migrations, altering servers, publishing, or mutating production;
- label observations as verified problem, testable hypothesis, or unproven opportunity.

Store diagnostics separately from product source when appropriate.

## Comparable baseline

Record:

- code revision;
- environment and build mode;
- device, browser, viewport, and input method;
- network and CPU conditions;
- test role, language, data volume, and state;
- cold or warm cache;
- sample size, run count, duration, and concurrency;
- tools used and their limitations.

Use applicable measures, including LCP, INP, CLS, FCP, TTFB, transferred and parsed JavaScript size, request count, API p50/p95/p99 with adequate samples, query time and count, error rate, CPU, memory, queue wait and processing time, and task completion time.

Distinguish laboratory measurements from real-user data. Do not present Lighthouse as all-user experience, TBT as INP, or percentiles from tiny samples.

## Frontend

Investigate before applying:

- route and component bundle size;
- download, parse, and execution cost;
- render and rerender causes;
- request waterfalls, duplication, and obsolete responses;
- image, font, media, and third-party loading;
- layout shifts and first-view priorities;
- long lists and input latency;
- animation, blur, filter, glass, and repaint cost;
- memory growth during realistic navigation.

Apply only supported measures such as route or module splitting, deferred heavy components, third-party deferral, dependency removal, responsive media, font subset and weight reduction, request cancellation, deduplication, safe parallelism, debounced search, pagination, or virtualization.

Do not add memoization, skeletons, lazy loading, or virtualization automatically. Prove that each addresses a measured cause and preserves behavior and access.

Use optimistic UI only when rollback is safe and the interface remains truthful. Do not optimistically finalize payment, inventory, permission, approval, or other authoritative sensitive operations unless the product contract explicitly supports it.

## APIs and services

- Identify slow endpoints and separate database, application, external-service, and network time where tracing allows.
- Remove proven duplicate work and return only necessary fields without breaking contracts.
- Use pagination for large collections.
- Set appropriate timeouts and connection reuse for external services.
- Bound concurrency to protect databases and dependencies.
- Use idempotency or duplicate protection for sensitive operations.
- Preserve error semantics and compatibility. Plan API-contract changes before implementation.

## Background work

Consider existing queues before adding a new system. Long tasks such as email, media processing, heavy reports, PDF generation, and external synchronization may move to a job only when the user flow does not require synchronous completion.

Define status, retry limits, backoff, timeout, idempotency, failure visibility, concurrency, ordering, transaction boundaries, and user messaging. Distinguish request acceptance from job completion.

## Database

- Use query traces and execution plans to diagnose N+1 behavior, slow joins, filters, sorting, large result sets, and long transactions.
- Select required columns and paginate or batch deliberately.
- Add indexes only after reviewing read benefit, write cost, storage, lock behavior, and deployment risk.
- Preserve transaction boundaries and consistency for orders, payments, inventory, returns, and permissions.
- Document compatibility, lock duration, rollback, and test evidence for every migration.
- Never run destructive or high-risk database changes on production without explicit approval.

## Caching

Inspect existing layers first. For each cache, define owner, key, scope, TTL, invalidation, stale behavior, and authorization boundary.

- Include user, tenant, role, language, currency, and other response-varying context in keys when applicable.
- Never share private responses through a public or cross-tenant cache.
- Test cold, warm, expired, invalidated, role-changed, and logout behavior.
- Add Redis, CDN, or another service only when evidence justifies its cost and maintenance.

## Infrastructure and monitoring

- Review CPU, memory, disk I/O, network location, database proximity, worker counts, compression, headers, CDN use, and service limits.
- Respect data-location and hosting requirements.
- Do not add load balancers, caches, queues, or observability platforms without a documented problem and simpler alternatives.
- Use existing logs and metrics first. Add targeted latency, error, query, queue, resource, and frontend signals where needed.
- Use correlation identifiers when they materially improve tracing.
- Never log passwords, tokens, payment data, private documents, personal data, or sensitive AI input/output. Define redaction, sampling, and retention.

## AI features that already exist

Do not add new AI features under an optimization task. For existing features:

- make waiting, streaming, partial output, cancellation, retry, timeout, and failure truthful;
- prevent duplicate requests and stale responses;
- measure time to first response and total completion when useful;
- minimize redundant calls and context without changing approved quality silently;
- preserve permissions for data sent to providers;
- keep sensitive prompts and outputs out of general logs.

## Implementation batches

For each batch, record:

- journey and verified problem;
- affected files, services, queries, or infrastructure;
- baseline;
- proposed change;
- acceptance criteria;
- tests and comparable measurements;
- risks and rollback.

Complete one valuable end-to-end journey first, then propagate proven patterns. Do not rewrite the whole system when a focused correction is sufficient, and do not keep a broken foundation when a bounded rebuild is the safer fix.

## Approval gates

Require explicit authorization for:

- production deployment or sensitive production settings;
- paid services or material operational-cost changes;
- business-rule, permission, feature-scope, or API-contract changes;
- risky database operations or migrations;
- load tests or state-changing tests against a live service.

Complete safe independent work before requesting a gate. Present the exact decision, evidence, risk, and rollback needed.
