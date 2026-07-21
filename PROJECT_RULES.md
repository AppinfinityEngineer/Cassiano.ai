# ThoughtSnap Labs Project Rules

These rules apply unless a project-specific document explicitly overrides them.

## Delivery

- Work only from documented product requirements and acceptance criteria.
- Build one reviewable branch at a time.
- Prefer complete vertical slices over disconnected scaffolding.
- Never create functional-looking placeholder controls.
- Never silently reduce scope or mark unfinished work complete.
- Record assumptions and material decisions.
- Update `docs/BUILD_LEDGER.md` before and after every branch.

## Engineering

- Keep architecture modular, typed, testable, and proportionate to the product.
- Validate all external input.
- Enforce authentication, authorisation, and ownership on the backend.
- Handle loading, empty, success, partial failure, and error states.
- Do not hardcode credentials, environment-specific URLs, prices, entitlements, or secrets.
- Avoid unnecessary dependencies and speculative abstractions.
- Preserve existing behaviour unless the branch intentionally changes it.

## Git and pull requests

- Never develop directly on `main`.
- Use `feature/`, `fix/`, `chore/`, or `release/` branch prefixes.
- Keep commits intentional and comprehensible.
- Every PR must include scope, exclusions, acceptance criteria, tests run, environment changes, risks, and screenshots for meaningful UI changes.
- Never merge with failing required checks.
- Never weaken tests, assertions, permissions, or security controls to make CI pass.
- Use squash merge unless the repository documents a different convention.

## Agent behaviour

- Read every repository control document before making changes.
- Inspect current branches, issues, PRs, CI, and the build ledger before starting new work.
- Repair active CI or review failures before opening unrelated branches.
- Continue automatically to the next eligible branch after a clean merge.
- Stop only for an owner-only blocker, irreversible production action, legal approval, live payment activation, secret provision, or unresolved material product ambiguity.
- Document blockers precisely and continue all unrelated safe work.

## Definition of done

Work is done only when implementation, tests, documentation, security checks, acceptance criteria, and repository state all agree that it is done.