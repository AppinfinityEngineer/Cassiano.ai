# Cassiano.ai Autonomous Engineering Contract

Every Codex task must read this file before changing the repository.

## Mission

Build Cassiano.ai V1 through the ordered branches in `docs/BRANCH_PLAN.md`. Continue automatically from the state recorded in `docs/BUILD_LEDGER.md`. Do not wait for routine owner approval between branches.

## Product boundary

Cassiano.ai sells a productised custom AI employee service. In V1, the final Custom GPT is created manually by Cassiano staff. Do not fabricate an API for automatic Custom GPT creation or ownership transfer.

## Locked stack

### Frontend
- React
- TypeScript
- Vite
- Tailwind CSS
- React Router
- TanStack Query
- React Hook Form
- Zod

### Backend
- Python
- FastAPI
- Pydantic
- current supported async PyMongo API
- MongoDB Atlas
- service and repository architecture

### Integrations
- Stripe Checkout with verified, idempotent webhooks
- S3-compatible private object storage
- transactional email provider abstraction
- Render-ready backend
- Vercel- or Render-ready frontend

### Testing
- Pytest
- frontend unit/component tests
- Playwright for critical end-to-end flows
- linting, formatting, type checking, and production builds

Do not change the locked stack without a documented ADR in `docs/DECISIONS.md`.

## Repository rules

- Never develop directly on `main` after bootstrap.
- Use the exact branch names and order in `docs/BRANCH_PLAN.md`.
- Open one pull request per branch.
- Use squash merge unless repository policy requires otherwise.
- Update `docs/BUILD_LEDGER.md` before and after every branch.
- Update `docs/DECISIONS.md` for meaningful architecture choices.
- Record genuine owner dependencies in `docs/EXTERNAL_BLOCKERS.md`.
- Continue all unrelated work when a blocker exists.
- Do not rewrite unrelated working areas.
- Do not leave controls that appear functional but do nothing.
- Do not silently swallow errors or fabricate successful integrations.
- Never commit secrets, credentials, private customer files, or production data.

## Branch loop

For each branch:

1. Pull current `main` and read all control documents.
2. Confirm the next eligible branch from the ledger.
3. Create or update a GitHub issue with scope, exclusions, acceptance criteria, tests, and security considerations.
4. Create the feature branch.
5. Implement the smallest complete vertical slice.
6. Add and run appropriate tests continuously.
7. Review the full diff as a senior engineer.
8. Fix defects before opening the pull request.
9. Open a pull request with an acceptance checklist and test results.
10. Repair CI and review findings until all gates pass.
11. Merge only when every applicable gate passes.
12. Update the ledger and begin the next eligible branch automatically.

## Mandatory quality gates

A branch may merge only when all applicable checks pass:

- formatting
- linting
- TypeScript/static checks
- unit tests
- integration tests
- production build
- relevant Playwright tests
- acceptance criteria
- security review
- accessibility review for UI work
- no unresolved critical or high-severity findings
- documentation current
- no committed secrets

Never remove, disable, weaken, or mark a valid test optional merely to make CI green.

## Security invariants

- Backend authorization is authoritative; frontend route guards are not security controls.
- Customers may access only their own records and files.
- Stripe payment state comes only from verified server-side webhook events.
- Stripe webhook processing must be idempotent.
- Monetary values use integer minor units.
- Files remain private and use short-lived signed access.
- MIME type, extension, size, filename, and ownership must be validated server-side.
- Invalid project-state transitions must be rejected server-side and audited.
- Critical QA failures must block delivery.
- Secrets must come from environment variables or managed secret stores.

## Owner approval required before

- production deployment
- live Stripe activation or real charges
- DNS changes
- infrastructure purchases
- repository visibility changes
- production data deletion
- production secret rotation
- publishing unreviewed legal terms
- irreversible repository operations
- knowingly shipping a critical security defect

## External credentials

Missing credentials must not stop unrelated development. Implement the real provider interface, a safe development adapter, contract tests, `.env.example` entries, and exact setup documentation. Record the remaining owner action in `docs/EXTERNAL_BLOCKERS.md`.

## Definition of V1 complete

V1 is complete only when the full test-mode journey works:

Visitor → registration → verified Stripe payment → one customer project → resumable onboarding → secure document upload → submission → admin build workspace → structured QA → controlled delivery → one revision → completion.

Tenant isolation, invalid-state prevention, payment integrity, file access controls, and critical QA delivery blocking must be proven by tests.
