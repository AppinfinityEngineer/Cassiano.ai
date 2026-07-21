# Cassiano.ai

Cassiano.ai is a self-service platform where businesses purchase a custom AI employee trained on their company knowledge, brand voice, products, services, policies, and workflows.

## V1 workflow

Visitor → account → Stripe full payment → guided onboarding → secure knowledge upload → admin build workspace → manual Custom GPT creation → structured QA → delivery → one revision → completion.

The Custom GPT itself is created manually in V1. The platform automates the commercial, intake, operations, QA, delivery, and revision workflow around the service.

## Locked stack

- Frontend: React, TypeScript, Vite, Tailwind CSS, React Router, TanStack Query, React Hook Form, Zod
- Backend: Python, FastAPI, Pydantic, async PyMongo, MongoDB Atlas
- Integrations: Stripe Checkout/webhooks, S3-compatible private storage, transactional email provider abstraction
- Testing: Pytest, frontend unit/component tests, Playwright

## Autonomous delivery

Codex must read `AGENTS.md` and the files under `docs/` before beginning or continuing work. Progress is controlled by `docs/BUILD_LEDGER.md` and the ordered branches in `docs/BRANCH_PLAN.md`.

## Current status

Repository bootstrap complete. Branch 1 is `feature/project-foundation`.

## Security

Never commit credentials or customer data. This repository is currently public; production activation requires an explicit owner privacy and security review.
