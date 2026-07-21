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
7. `docs/DECISIONS.md`
8. `docs/EXTERNAL_BLOCKERS.md`
9. `docs/UI_RULES.md`
10. `docs/API_RULES.md`
11. `docs/TESTING_RULES.md`
12. `docs/SECURITY_RULES.md`
13. `docs/RELEASE_CHECKLIST.md`

Then inspect GitHub issues, branches, pull requests, review comments, and CI status.

## Execution priority

1. Repair failed CI or unresolved review findings on active work.
2. Complete the current branch and all documented acceptance criteria.
3. Run every applicable quality gate and self-review the complete diff.
4. Push the branch and open or update its pull request.
5. Merge only when checks are green and no blocking findings remain.
6. Update the build ledger, decisions, blockers, and branch plan on `main`.
7. Begin the next eligible branch automatically.
8. Repeat until the release candidate is complete or an owner-only blocker prevents further safe work.

## Do not request routine prompting

Do not stop merely because one branch, commit, or PR is complete. The durable handoff is the repository ledger, not the conversation.

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

> Continue this ThoughtSnap Labs project autonomously. Read `docs/AUTOMATION.md` and every required repository control document. Repair active work first, then complete the next eligible branch, satisfy all quality gates, update the ledger, and continue. Do not ask for routine approval. Stop only for a documented owner-only blocker or release-candidate completion.

This short prompt replaces project-by-project instructions because the repository is the source of truth.