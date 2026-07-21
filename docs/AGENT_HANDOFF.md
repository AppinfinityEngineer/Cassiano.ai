# ThoughtSnap Labs Agent Handoff Protocol

This repository uses separate autonomous roles so implementation and review do not rely on the same agent perspective.

## Roles

### Builder Agent

The Builder Agent owns implementation.

It must:

1. read all repository control documents;
2. confirm Git remotes, branch, push access, package access, and CI availability before substantial work;
3. work only on the current approved feature branch;
4. implement the documented acceptance criteria;
5. add tests and regression protection;
6. run all applicable quality gates;
7. commit and push the branch to GitHub;
8. open or update a pull request;
9. write a structured handoff for the Reviewer Agent;
10. never approve or merge its own pull request.

The Builder Agent must not declare work complete when changes exist only in an ephemeral workspace. Completion requires a pushed Git branch and a hosted pull request.

### Reviewer Agent

The Reviewer Agent owns independent verification.

It must review against the repository, not against the Builder Agent's confidence.

It must read:

- `AGENTS.md`
- `THOUGHTSNAP.md`
- `PROJECT_RULES.md`
- `docs/PRODUCT_SPEC.md`
- `docs/BRANCH_PLAN.md`
- `docs/UI_RULES.md`
- `docs/API_RULES.md`
- `docs/TESTING_RULES.md`
- `docs/SECURITY_RULES.md`
- `docs/LEARNINGS.md`
- the linked issue and acceptance criteria
- the complete pull-request diff
- CI results and relevant logs

The Reviewer Agent must check:

- requirement coverage;
- correctness and edge cases;
- architecture consistency;
- authentication and authorisation;
- tenant isolation;
- payment integrity;
- file access controls;
- state-machine enforcement;
- error handling;
- accessibility and responsive behaviour;
- test quality and missing regression coverage;
- duplication, dead code, placeholders, and accidental secrets;
- whether previous lessons in `docs/LEARNINGS.md` were respected.

The Reviewer Agent must classify findings:

- `critical`: security, data loss, payment corruption, tenant breach, or unusable core flow;
- `high`: major requirement failure or likely production defect;
- `medium`: important maintainability, resilience, accessibility, or test weakness;
- `low`: polish or non-blocking improvement.

Critical and high findings always block approval. Valid medium findings should be fixed unless explicitly recorded as accepted debt with a concrete reason.

## Handoff Format

The Builder Agent must add this information to the pull request:

```markdown
## Builder Handoff

### Issue and branch
- Issue: #<number>
- Branch: `<branch>`

### Acceptance criteria
- [x] ...

### Files and architecture changed
- ...

### Tests and checks run
- command — result

### Security and data considerations
- ...

### Known limitations
- ...

### Learning updates
- regression tests added
- `docs/LEARNINGS.md` entries added or updated
```

## Review and Repair Loop

1. Builder pushes code and opens the PR.
2. Reviewer inspects the full PR and posts findings.
3. Builder resumes the same branch and fixes every blocking finding.
4. Builder adds regression tests where a defect was found.
5. Builder updates `docs/LEARNINGS.md` when the lesson is reusable.
6. Reviewer re-reviews the new head commit.
7. Repeat until approved and CI is green.
8. Reviewer may merge using squash merge only when every merge gate passes.
9. After merge, the continuation agent updates `docs/BUILD_LEDGER.md` and starts the next eligible branch.

## Merge Authority

The Reviewer Agent may merge without routine human approval only when:

- the repository permits automated merge;
- every required CI check is green;
- all branch acceptance criteria are verified;
- no critical or high findings remain;
- no unresolved valid medium finding remains without documented acceptance;
- no owner-only stop condition applies;
- the PR head SHA has not changed since the final review;
- the branch contains no secrets or production activation.

The Reviewer Agent must not merge production deployment, live payment activation, DNS changes, legal publication, destructive operations, or unresolved critical security work.

## Continuation

A merged branch is not the end of the project. The continuation agent must update repository state and begin the next eligible branch automatically.