---
name: production-readiness
description: Build and maintain an evidence-backed, product-specific production checklist for a software project, from planning through release and post-launch operations. Use before or during a release, and re-check affected items after implementation changes; do not claim certification or perform deployment actions.
metadata:
  short-description: Review every relevant production-readiness area
---

# Production Readiness

Create a comprehensive checklist across the areas that can affect a product's release, then tailor it to the product instead of dumping an irrelevant master list. This skill is a practical review aid, not a guarantee that every risk has been found.

## Scope and workflow

1. Read [references/checklist-catalog.md](references/checklist-catalog.md) before the review. Use it to consider all major categories, not just code, SEO, or deployment.
2. Inspect the project, available preview, documentation, stack, deployment configuration, and recent changes. Identify the product type, primary user journeys, data handled, release stage, and known constraints. A successful build alone does not establish readiness.
3. Map the catalog to the product. Include each applicable category and explain exclusions that might otherwise be expected. For a web product, consider web UX, accessibility, security, operations, discoverability, and privacy. For mobile, APIs, desktop/CLI, libraries, or other software, include their specific distribution and compatibility checks too.
4. Verify checks against observable evidence. Use repository evidence for code/configuration claims, and a browser or runtime for user-facing behavior when available. For volatile technology requirements or standards, consult current primary/official documentation where browsing is available. Do not infer deployment-provider configuration from source files.
5. For a real project review, create or update `PRODUCTION-CHECKLIST.md` in the project root so the result can be carried forward. If no writable project is available, return the checklist in the conversation. Preserve prior decisions and status history when updating an existing checklist. If the user asks only for an illustrative example or a skill-behavior test, keep the checklist inline and do not alter the sample project.
6. When applied alongside implementation work, re-check the affected checklist items after the changes and update their status only after verifying them again. Do not imply background monitoring or automatic checks between skill invocations.

## Categories to consider

Use the full catalog to consider these categories. Include relevant subchecks and mark out-of-scope areas with a reason rather than silently omitting them:

1. Product scope, release plan, users, and support ownership
2. Core functionality, data correctness, edge cases, and recovery
3. UX, content, responsive behavior, accessibility, and localization
4. Platform, browser, device, API, and package compatibility
5. Security, privacy, data lifecycle, permissions, and secret handling
6. Testing, quality gates, and release regression checks
7. Build, CI/CD, configuration, deployment, migrations, and rollback
8. Performance, capacity, availability, and resilience
9. Observability, alerts, incident response, backups, and support
10. Search discoverability, SEO, link previews, and carefully scoped GEO
11. Analytics, business flows, billing, and user feedback
12. Legal, licensing, trust, and jurisdiction-specific review
13. Documentation, onboarding, distribution, and release communication
14. Post-launch monitoring, feedback, and follow-up

## Status and priority

Every checklist item must have one status:

- **Verified** — inspected or exercised; include concise evidence and date.
- **Needs attention** — a concrete issue or missing required work was found.
- **Not assessed** — relevant, but could not be checked with available access.
- **Not applicable** — explain why it does not apply to this product.

Prioritize relevant items as **P0** (release blocker), **P1** (address before broad release or document an explicit owner/decision), or **P2** (post-launch improvement). Use priorities to make tradeoffs visible, not to hide unchecked areas.

## Evidence and safety boundaries

- Separate repository-verifiable checks from tasks requiring live credentials, production access, a human decision, or specialist review.
- Never expose, request, or commit secret values. Verify that expected variable names are documented and that secret values belong in the deployment provider's secret manager. `.env.example` may contain safe placeholders; `.env` containing real secrets must remain out of version control.
- Do not push changes, deploy, alter production configuration, create accounts, submit app-store releases, or contact users as part of a readiness review.
- For SEO and GEO, report observable technical/content readiness, not rankings or guaranteed LLM citations. Treat emerging GEO tactics as optional experiments, not release blockers or settled standards.
- Do not call this a security audit, legal opinion, accessibility certification, compliance certification, or complete assurance review.

## Deliverable

Provide a concise readiness summary, then a categorized checklist with status, priority, evidence, and next action. Call out P0 blockers separately. Include all considered categories, even when some are marked not applicable or not assessed. State the project areas and environments that were unavailable, and the date/scope of the review.
