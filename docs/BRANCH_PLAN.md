# Cassiano.ai Ordered Branch Plan

Branches run sequentially unless this file records a justified dependency change. Each branch requires an issue, tests, self-review, pull request, green CI, and updated documentation before merge.

## 1. `feature/project-foundation`

Create the monorepo, frontend, backend, MongoDB lifecycle, environment configuration, typed health integration, Docker development setup, test/lint/type-check configuration, CI, and setup documentation.

Acceptance: frontend and backend start; health accurately reports API/database state; tests, linting, type checks, and builds pass; no secrets committed.

## 2. `feature/design-system-shell`

Create the Cassiano visual system, accessible reusable components, public shell, customer shell, admin shell, navigation, responsive behaviour, and loading/empty/error states.

Acceptance: shared components are used consistently; keyboard and responsive review pass; no duplicated page-level design system.

## 3. `feature/authentication-rbac`

Create customer registration, login/logout, password reset architecture, secure token/session handling, customer/admin roles, seed-admin mechanism, backend authorisation, and protected frontend routes.

Acceptance: passwords are securely hashed; role and tenant boundaries are tested; invalid/expired authentication is handled safely.

## 4. `feature/marketing-site-seo`

Build Home, How It Works, Pricing, Capabilities, FAQ, Contact, and editable legal placeholders. Add metadata, canonicals, sitemap, robots, structured data, accessibility, and performance foundations.

Acceptance: offer is clear; CTA enters registration/purchase flow; no fake testimonials or unsupported claims; SEO and accessibility checks pass.

## 5. `feature/stripe-full-payment`

Create one configurable package, Stripe Checkout, verified/idempotent webhooks, order model, customer order view, admin order list, success/cancel flows, and test-mode coverage.

Acceptance: only verified webhooks mark payment; duplicates are safe; money uses integer minor units; failures are tested.

## 6. `feature/customer-projects`

Create exactly one project from each paid order, backend state machine, status history, customer progress view, admin queue, search/filtering, and ownership rules.

Acceptance: duplicate projects are prevented; invalid transitions fail; customers see only their projects.

## 7. `feature/onboarding-wizard`

Create the multi-step guided onboarding, repeatable fields, autosave, resume, validation, progress, review, final submission, locking, and admin-readable submission.

Acceptance: refresh does not lose progress; required fields work; submission updates project state; cross-customer access is impossible.

## 8. `feature/knowledge-file-uploads`

Create private S3-compatible storage abstraction, local adapter, signed access, file validation, categories, customer ownership, admin access, deletion/replacement, and security tests.

Acceptance: files are private; unsupported or oversized files fail; tenant isolation and deletion behaviour are tested.

## 9. `feature/admin-build-workspace`

Create the consolidated admin project workspace, onboarding/file review, deterministic editable/versioned build brief, GPT configuration record, internal notes, information requests, and build workflow actions.

Acceptance: admins have one operational workspace; customer-hidden data stays hidden; versions and requests are audited.

## 10. `feature/gpt-qa-harness`

Create standard and project-specific tests, expected/actual behaviour, result/severity/reviewer fields, required-test configuration, summaries, and backend delivery blocking.

Acceptance: incomplete mandatory tests and critical failures prevent ready-for-delivery transitions.

## 11. `feature/delivery-revision`

Create controlled delivery, access/setup guidance, recommended prompts, limitations and third-party cost explanation, plus one-revision entitlement and history.

Acceptance: delivery requires approved state; revision limits are enforced; out-of-scope and completion flows work.

## 12. `feature/email-audit-production-hardening`

Create transactional email abstraction, lifecycle emails, audit events, secure headers, rate limiting, structured logging, operational health, data export/deletion foundations, deployment configuration, and production documentation.

Acceptance: sensitive actions are audited; unavailable providers fail visibly; security and deployment documentation are complete.

## 13. `feature/end-to-end-release-candidate`

Build and pass Playwright happy and negative paths for registration, payment, project creation, onboarding, uploads, admin build, QA, delivery, revision, completion, and tenant isolation. Perform desktop/mobile UI review and repair release blockers.

Acceptance: complete test-mode journey passes; no critical/high defects remain.

## 14. `release/v1-production-readiness`

Perform architecture, security, accessibility, performance, dependency, index/data, backup/recovery, deployment, legal-placeholder, and release-checklist reviews.

Acceptance: release-readiness report exists; all owner actions are explicit; no production deployment or live payment activation occurs without owner approval.
