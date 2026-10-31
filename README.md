# Production Readiness

An open-source agent skill for building and maintaining a product-specific release checklist across the full software lifecycle. It covers functional behavior, UX, accessibility, platform compatibility, security, privacy, testing, deployment, performance, operations, SEO/GEO, business flows, legal review, documentation, and post-launch monitoring.

The skill selects relevant checks from a broad catalog, marks each with evidence-backed status, and saves or updates `PRODUCTION-CHECKLIST.md` in the project. It distinguishes what was verified from what could not be checked. It is a review aid, not a certification or a substitute for specialist security, legal, accessibility, or compliance work.

## Use it

Share this folder with your agent or install the folder in the skill directory your agent uses. Example:

```text
Use production-readiness to prepare this application for its first public release.
Inspect the repository, create a project-specific checklist, and verify what you can.
Keep unchecked operational items visible. Do not deploy or change production settings.
```

When used alongside implementation work, the skill re-checks affected items after changes and updates the checklist with fresh evidence. It does not monitor the project in the background.

## Statuses

- **Verified** — checked directly with evidence.
- **Needs attention** — a concrete gap or defect was found.
- **Not assessed** — relevant but unavailable to verify.
- **Not applicable** — excluded with a reason.

Items also get a P0/P1/P2 priority. The reference catalog describes 14 categories; the review should consider every category and explain non-applicable areas instead of silently leaving them out.

## Native Agent Skills

Copy this folder into the skills directory supported by your agent:

| Agent | Example path |
| --- | --- |
| OpenAI Codex | `.codex/skills/production-readiness/` |
| Claude Code | `.claude/skills/production-readiness/` |
| Google Antigravity | `.agents/skills/production-readiness/` |

The folder must include `SKILL.md` and `references/checklist-catalog.md`.

## Example and test report

See [TEST-REPORT.md](TEST-REPORT.md) for a checklist example based on a read-only review of Galvora Library.

## Files

```text
production-readiness/
├── SKILL.md
├── README.md
├── LICENSE
├── TEST-REPORT.md
└── references/
    └── checklist-catalog.md
```

Built by **Galvora Labs**. Licensed under [MIT](LICENSE).
