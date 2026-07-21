# ThoughtSnap Labs Product Philosophy

This document defines the default product and engineering DNA for every ThoughtSnap Labs project.

## Principles

- Simple beats clever.
- Every product must have one obvious primary job.
- Local-first and offline-capable are preferred where practical.
- Use the smallest backend that genuinely serves the product.
- Do not add AI where deterministic software is better.
- Premium onboarding is part of the product, not decoration.
- Fast startup, responsive interaction, clear feedback, and graceful failure are mandatory.
- Every feature must earn its place.
- Build commercially useful vertical slices before broad feature sets.
- Quality, trust, privacy, and maintainability outrank raw shipping speed.
- Ship small, test thoroughly, learn quickly, and automate repeatable work.
- Never claim an integration, result, test, or deployment succeeded when it was not verified.

## Product standard

A ThoughtSnap Labs product should be:

- understandable within seconds;
- useful without unnecessary setup;
- visually coherent and premium;
- resilient when networks or dependencies fail;
- honest about limitations and third-party costs;
- measurable through meaningful product and operational metrics;
- maintainable by another engineer or coding agent using repository documentation alone.

## Automation standard

Repositories are the durable source of truth. Agents must not rely on prior chat context.

Every project must maintain:

- `AGENTS.md`
- `THOUGHTSNAP.md`
- `PROJECT_RULES.md`
- `docs/PRODUCT_SPEC.md`
- `docs/BRANCH_PLAN.md`
- `docs/BUILD_LEDGER.md`
- `docs/DECISIONS.md`
- `docs/EXTERNAL_BLOCKERS.md`
- `docs/UI_RULES.md`
- `docs/API_RULES.md`
- `docs/TESTING_RULES.md`
- `docs/SECURITY_RULES.md`
- `docs/RELEASE_CHECKLIST.md`
- `docs/AUTOMATION.md`

The default continuation instruction is: read the repository control documents, repair the current work, complete the next eligible branch, update the ledger, and continue without routine owner prompting.