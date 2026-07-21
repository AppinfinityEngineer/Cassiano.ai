# ThoughtSnap Labs Testing Rules

## Principles

- Test behaviour and risk, not implementation trivia or coverage numbers alone.
- Every defect fix requires regression coverage where technically possible.
- Critical flows require integration or end-to-end evidence, not only unit tests.
- Tests must be deterministic, isolated, readable, and safe to run repeatedly.

## Required layers

- Unit tests for business rules, validation, transformations, and state machines.
- Integration tests for databases, providers, APIs, authentication, payments, and storage boundaries.
- End-to-end tests for the smallest set of commercially critical customer and admin journeys.
- Negative-path tests for permissions, tenant isolation, duplicate events, invalid transitions, and dependency failure.

## Quality gates

Every branch must run the applicable formatter, linter, type checker, unit tests, integration tests, production build, and end-to-end tests.

Never delete, skip, weaken, or rewrite a valid test merely to make CI pass. Fix the product or document why the requirement itself must change.