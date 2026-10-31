# Production Readiness Checklist Catalog

Use this catalog as a coverage map. Select concrete checks based on the product, data, audience, deployment model, and release stage. Do not mark a category complete merely because it appears here.

## 1. Product scope and release management

- Supported users, regions, plans, and use cases are clear.
- Release scope, known limitations, migration impact, and rollout strategy are documented.
- Feature flags or staged rollout are considered for risky changes.
- A named owner can make release, rollback, and incident decisions.
- User-facing pricing, limits, eligibility, and terms match the implemented product.

## 2. Core functionality and user journeys

- Primary user journeys work end to end, including first run and returning use.
- Validation, permissions, authorization, persistence, and data integrity behave as intended.
- Loading, empty, success, error, offline, timeout, retry, and not-found states are handled.
- Account recovery, deletion, cancellation, export, and destructive actions are clear where relevant.
- Payments, subscriptions, notifications, email delivery, and third-party integrations are checked when present.
- User-visible error messages provide a recovery path without exposing internals.

## 3. UX, content, accessibility, and localization

- Layouts work at representative mobile, tablet, and desktop sizes.
- Keyboard navigation, visible focus, labels, semantics, contrast, and screen-reader names are reviewed.
- Forms communicate validation and errors; controls have clear labels and touch targets.
- Copy is understandable and consistent; dates, times, numbers, currency, and units are correct for the target locale.
- Language, right-to-left layout, time zones, and translated content are tested where applicable.
- Images have appropriate alternatives; motion and media have accessible alternatives where relevant.
- Verify against the current accessibility target selected by the project; do not claim conformance from a quick scan.

## 4. Platform and compatibility

### Web applications

- Supported browsers, viewport sizes, navigation, refresh/deep links, and browser history work.
- 404 and route fallback behavior is useful; canonical host, HTTPS, and redirects are correct.
- Cookie/storage behavior and permission prompts match the product's needs.

### Mobile applications

- Supported OS versions and device sizes are stated and tested.
- Install, upgrade, permissions, deep links, push notifications, offline behavior, and crash recovery work.
- Store listing, privacy disclosures, signing, release channel, and rollback/previous-version considerations are addressed.

### APIs and services

- Authentication, authorization, request validation, error schemas, versioning, quotas, and idempotency are handled.
- API documentation and machine-readable schemas match behavior; CORS is checked only where browser clients require it.
- Webhooks have authentication, replay handling, and delivery/retry visibility where relevant.

### Desktop, CLI, libraries, and packages

- Clean installation, upgrade, uninstall, OS/runtime compatibility, and failure recovery are checked.
- CLI input, destructive commands, shell escaping, and exit codes are predictable.
- Package names, versions, dependencies, exports, license metadata, and installation documentation are correct.
- Signing, provenance, checksums, or update channels are considered for distributable binaries.

## 5. Security, privacy, and data lifecycle

- Authentication, session handling, authorization boundaries, and least privilege are checked.
- Inputs, uploads, output encoding, injection risks, CSRF/CORS, security headers, and rate limits are reviewed as relevant.
- Secrets are absent from source, logs, build output, screenshots, and committed environment files.
- Environment variable names and required configuration are documented; real secret values are stored through the deployment provider.
- Dependencies, build actions, permissions, and software supply chain are reviewed proportionally to exposure.
- Sensitive data has a defined purpose, access policy, retention, deletion, export, backup, and restore path.
- Transport and storage protections are reviewed where sensitive data is involved.
- Privacy notices, cookie/consent behavior, analytics, and third-party data sharing are disclosed appropriately.
- Incident handling and disclosure contacts/process are known when the risk warrants them.

## 6. Testing and quality gates

- Unit, integration, end-to-end, and regression checks cover critical paths in proportion to the product.
- A production build and clean install are checked; tests do not rely on local-only state.
- Smoke tests cover the release artifact and highest-risk integrations.
- Test data is non-sensitive; test and production environments are separated.
- Accessibility, browser/device, security, and performance checks are selected where relevant.
- Flaky or skipped checks are visible; coverage percentage alone is not treated as proof of quality.

## 7. Build, CI/CD, configuration, and deployment

- Build is reproducible enough for the project; dependency lockfiles and runtime versions are intentional.
- CI gates, artifact identity, deployment permissions, and branch/release policy are understood.
- Development, staging, and production configuration are separated.
- Required environment variables are documented and validated at startup; no secret values are committed.
- Database/schema migrations are ordered, reversible or recoverable, and tested on representative data.
- DNS, TLS, canonical domains, redirects, CDN/cache invalidation, and service bindings are correct where applicable.
- Rollback, feature-flag disablement, and recovery steps are documented for risky changes.
- Release includes versioning, changelog, deprecation, and compatibility behavior where needed.

## 8. Performance, capacity, availability, and resilience

- Page/app startup and critical operations are measured against a user-relevant target.
- Heavy assets, caching, database queries, API latency, and client-side work are reviewed.
- Timeouts, retries, backoff, idempotency, concurrency, queue behavior, and dependency failure are handled where relevant.
- Capacity, rate limits, quotas, storage growth, and third-party service limits are understood.
- Graceful degradation and recovery from unavailable dependencies are considered.
- Cost and spend alerts are considered for usage-based services.
- Load or resilience testing is used when expected exposure and consequence justify it.

## 9. Observability, operations, incident response, and support

- Logs, metrics, traces, health checks, and alerts cover critical user journeys and dependencies.
- Logs avoid unnecessary secrets and personal data; alert thresholds are actionable.
- Operational owner, escalation route, incident notes, and runbooks exist for material risks.
- Backups are configured where required and restore has been exercised or explicitly marked untested.
- Status/support channels and user feedback routes are visible and staffed appropriately.
- Error reporting and analytics are checked for sensitive data leakage.

## 10. Search discoverability, SEO, previews, and GEO

### Conventional search and link sharing

- Page titles, descriptions, headings, canonical URLs, robots directives, sitemap, and internal links match intended indexability.
- Important content is available to crawlers in the rendered page; no accidental staging/noindex behavior remains.
- Structured data is valid and only describes visible, accurate content.
- Open Graph/social preview metadata and images render on major sharing clients.
- Locale/canonical/hreflang behavior is correct when multilingual pages exist.
- Search and performance recommendations use current official documentation when technical requirements have changed.

### Generative engine optimization

- Make the product, organization, terminology, and key facts easy to understand from accurate, well-structured public pages.
- Check that public documentation has stable URLs, clear headings, and dates/versions where useful.
- Treat crawler policies and emerging GEO tactics as optional, changeable experiments. Do not claim guaranteed rankings, inclusion, or citations; do not make `llms.txt` or a particular AI crawler rule a universal launch requirement.

## 11. Analytics, business flows, and feedback

- Product goals and critical events are defined; event names and parameters are consistent.
- Consent, retention, access, and privacy controls match the analytics being used.
- Signup, activation, conversion, billing, cancellation, refunds, and transactional messages are verified where applicable.
- Attribution assumptions and dashboards are understood; analytics are not mistaken for ground truth.
- Feedback, bug reporting, and user support pathways are clear.

## 12. Legal, licensing, trust, and specialist review

- Terms, privacy disclosures, cookie consent, consumer disclosures, and data rights are reviewed for the operating jurisdictions.
- Third-party assets, fonts, dependencies, datasets, and models have compatible licenses and attribution.
- Regulated data, age limits, financial/health claims, and industry-specific requirements are routed for qualified review.
- Accessibility or compliance claims are not made without the scope and evidence to support them.

This catalog is not legal advice or a compliance checklist for a specific jurisdiction. Mark specialist review as not assessed until completed by an appropriate reviewer.

## 13. Documentation, onboarding, distribution, and communication

- A new user can understand prerequisites and complete onboarding without hidden setup knowledge.
- Help, troubleshooting, account/contact, and support information are findable.
- Install/update instructions, environment setup, API references, or app-store metadata match the release.
- Release notes explain meaningful changes, limitations, migrations, and breaking changes.
- Emails, notifications, invitations, and user-facing release messages have been checked in realistic clients.

## 14. Post-launch monitoring and learning

- First-run activation, errors, performance, support signals, and key business outcomes have an owner and review window.
- Rollout expansion/stop criteria are set for staged releases where appropriate.
- Feedback, incidents, and regressions have a path to be triaged and fixed.
- Checklist findings are revisited after release; improvements deferred from launch have an owner or explicit acceptance.
