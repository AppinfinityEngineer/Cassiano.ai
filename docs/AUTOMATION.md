# ThoughtSnap Labs Autonomous Continuation Contract

This file is the default instruction for Codex or another approved coding agent when resuming this repository.

## Resume command

Read, in order:

1. `AGENTS.md`
2. `THOUGHTSNAP.md`
3. `PROJECT_RULES.md`
4. `docs/PRODUCT_SPEC.md`
5. `docs/BRANCH_PLAN.md`
6. `docs/BUILD_LEDGER.md`
7. `docs/LEARNINGS.md`
8. `docs/DECISIONS.md`
9. `docs/EXTERNAL_BLOCKERS.md`
10. `docs/UI_RULES.md`
11. `docs/API_RULES.md`
12. `docs/TESTING_RULES.md`
13. `docs/SECURITY_RULES.md`
14. `docs/RELEASE_CHECKLIST.md`

Then inspect GitHub issues, branches, pull requests, review comments, and CI status.

Before implementation, perform an environment preflight:

- confirm the expected repository and branch;
- confirm a configured Git remote and push capability;
- confirm package registry access;
- confirm required toolchains are available;
- confirm CI can run;
- record any unavailable capability without pretending validation succeeded.

## Execution priority

1. Repair failed CI or unresolved review findings on active work.
2. Repair credible bugs and regressions already recorded in issues, tests, monitoring, or reviews.
3. Complete the current branch and all documented acceptance criteria.
4. Run every applicable quality gate and self-review the complete diff.
5. Push the branch and open or update its pull request.
6. Merge only when checks are green and no blocking findings remain.
7. Update the build ledger, learnings, decisions, blockers, and branch plan on `main`.
8. Begin the next eligible branch automatically.
9. Repeat until the release candidate is complete or an owner-only blocker prevents further safe work.

## Mandatory self-improvement loop

When any defect, regression, failed approach, CI failure, security weakness, or incorrect assumption is found:

1. reproduce it;
2. identify the root cause;
3. add a regression test that proves the failure;
4. implement the smallest correct fix;
5. search for the same defect pattern elsewhere;
6. add or update an entry in `docs/LEARNINGS.md`;
7. promote reusable prevention rules into the permanent project standards;
8. reference the learning entry in the pull request.

Do not merely patch symptoms. A fix is incomplete until regression protection and future prevention have been considered.

Future agents must treat active entries in `docs/LEARNINGS.md` as binding project knowledge.

## Do not request routine prompting

Do not stop merely because one branch, commit, PR, or scheduled run is complete. The durable handoff is the repository ledger and learning record, not the conversation.

A scheduled run may end at a natural boundary, but the next scheduled run must resume from repository state without requiring a rewritten task prompt.

## Owner-only stop conditions

Stop and record an exact owner action only for:

- production deployment;
- live payment activation;
- DNS or repository visibility changes;
- secret or credential provision;
- destructive or irreversible production operations;
- legal approval;
- unresolved material product ambiguity;
- a critical security decision;
- release-candidate completion requiring final owner review.

Continue all unrelated safe work while a blocker exists.

## Standard task prompt

Use this short prompt for future runs:

> Continue this ThoughtSnap Labs project autonomously. Read `docs/AUTOMATION.md` and every required repository control document, including `docs/LEARNINGS.md`. Repair active work first, apply the mandatory self-improvement loop to every bug or failed approach, then complete the next eligible branch, satisfy all quality gates, update the ledger and learning record, and continue. Do not ask for routine approval. Stop only for a documented owner-only blocker or release-candidate completion.

This short prompt replaces project-by-project instructions because the repository is the source of truth.
