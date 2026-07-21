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
10. `docs/AGENT_HANDOFF.md`
11. `docs/UI_RULES.md`
12. `docs/API_RULES.md`
13. `docs/TESTING_RULES.md`
14. `docs/SECURITY_RULES.md`
15. `docs/RELEASE_CHECKLIST.md`

Then inspect GitHub issues, branches, pull requests, review comments, and CI status.

Before implementation, perform an environment preflight:

- confirm the expected repository and branch;
- confirm a configured Git remote and push capability;
- confirm package registry access;
- confirm required toolchains are available;
- confirm CI can run;
- record any unavailable capability without pretending validation succeeded.

A coding run must not spend substantial effort in a workspace that cannot push its branch. If no Git remote or push capability exists, stop implementation immediately, record the blocker, and continue only in a correctly connected environment.

## Agent separation

Use two independent roles:

- **Builder Agent:** implements, tests, commits, pushes, and opens or updates the pull request.
- **Reviewer Agent:** independently reviews the hosted pull request against the codebase, standards, issue, tests, CI, and `docs/LEARNINGS.md`.

The Builder Agent must never approve or merge its own pull request.

The Reviewer Agent may merge only after all conditions in `docs/AGENT_HANDOFF.md` are satisfied.

## Execution priority

1. Repair failed CI or unresolved review findings on active work.
2. Repair credible bugs and regressions already recorded in issues, tests, monitoring, or reviews.
3. Complete the current branch and all documented acceptance criteria.
4. Run every applicable quality gate and self-review the complete diff.
5. Push the branch and open or update its hosted pull request.
6. Produce the Builder Handoff defined in `docs/AGENT_HANDOFF.md`.
7. Hand the pull request to the independent Reviewer Agent.
8. Repeat the builder-reviewer repair loop until approved and green.
9. Reviewer Agent merges when safe.
10. Update the build ledger, learnings, decisions, blockers, and branch plan on `main`.
11. Begin the next eligible branch automatically.
12. Repeat until the release candidate is complete or an owner-only blocker prevents further safe work.

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

Do not stop merely because one branch, commit, PR, review cycle, or scheduled run is complete. The durable handoff is the hosted GitHub state, repository ledger, and learning record—not the conversation or an ephemeral workspace.

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

## Standard Builder task prompt

> Act as the Builder Agent for this ThoughtSnap Labs project. Read `docs/AUTOMATION.md`, `docs/AGENT_HANDOFF.md`, and every required repository control document. Perform the environment preflight before implementation. Repair active review or CI failures first, then implement the next eligible work, run all quality gates, commit, push, and create or update the hosted pull request. Add the required Builder Handoff. Do not approve or merge your own PR. Stop only after the PR is ready for the independent Reviewer Agent or a documented owner-only blocker exists.

## Standard Reviewer task prompt

> Act as the independent Reviewer Agent for this ThoughtSnap Labs project. Read `docs/AUTOMATION.md`, `docs/AGENT_HANDOFF.md`, all engineering standards, `docs/LEARNINGS.md`, the linked issue, the complete hosted pull-request diff, and CI results. Review independently and post severity-classified findings. Do not implement broad product work. Request fixes for blocking findings. When the current PR head satisfies all acceptance criteria, quality gates, security requirements, and handoff conditions, approve and squash-merge it. Then update or trigger the repository continuation state so the next eligible Builder task can begin. Stop only for an owner-only blocker or release-candidate completion.

These short prompts replace project-by-project instructions because the repository is the source of truth.