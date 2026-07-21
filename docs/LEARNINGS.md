# ThoughtSnap Labs Project Learnings

This is the durable memory of defects, failed approaches, operational incidents, and reusable engineering lessons discovered while building and maintaining this project.

Every Codex agent must read this file before planning or changing code.

## Purpose

Codex does not permanently retrain itself from one task. This file gives every future agent explicit repository memory so the project improves over time.

The objective is not merely to fix each defect. The objective is to prevent the same class of defect from returning.

## Mandatory learning loop

Whenever a bug, regression, CI failure, security weakness, incorrect assumption, or failed implementation is discovered:

1. Reproduce the issue reliably.
2. Identify the root cause rather than patching only the visible symptom.
3. Add a regression test that fails before the fix and passes after it.
4. Implement the smallest correct fix.
5. Search the repository for the same pattern elsewhere.
6. Record the learning below.
7. Promote reusable prevention rules into the appropriate permanent standard:
   - `PROJECT_RULES.md`
   - `docs/UI_RULES.md`
   - `docs/API_RULES.md`
   - `docs/TESTING_RULES.md`
   - `docs/SECURITY_RULES.md`
8. Reference the learning entry in the pull request.

A bug is not considered fully resolved until prevention has been considered.

## Entry template

### LRN-YYYY-NNN — Short title

- **Date:** YYYY-MM-DD
- **Project area:** frontend / backend / infrastructure / payments / authentication / files / QA / delivery / other
- **Severity:** low / medium / high / critical
- **Detected by:** test / CI / Codex review / owner / customer / monitoring
- **Symptom:** What visibly failed.
- **Root cause:** Why it happened.
- **Fix:** What changed.
- **Regression protection:** Test, check, invariant, lint rule, or monitoring added.
- **Repository-wide search:** Where else the same pattern was checked.
- **Prevention rule:** The reusable rule future agents must follow.
- **Promoted to standard:** File and section updated, or `not required` with reason.
- **Issue/PR:** References.
- **Status:** active / superseded

---

## Active learnings

### LRN-2026-001 — Autonomous tasks require durable repository state

- **Date:** 2026-07-21
- **Project area:** automation
- **Severity:** high
- **Detected by:** owner
- **Symptom:** A Codex task completed one work session and stopped instead of automatically carrying the entire product through every branch.
- **Root cause:** Individual Codex runs are finite tasks. A long product build cannot depend on chat context or an assumption that one task will run forever.
- **Fix:** Added `AGENTS.md`, `docs/AUTOMATION.md`, `docs/BUILD_LEDGER.md`, and `docs/BRANCH_PLAN.md` as durable state and continuation instructions.
- **Regression protection:** Every continuation task must read repository control documents and select work from the ledger.
- **Repository-wide search:** Applies to every ThoughtSnap Labs repository.
- **Prevention rule:** Product state must live in Git, never solely in an agent conversation.
- **Promoted to standard:** `PROJECT_RULES.md` and `docs/AUTOMATION.md`.
- **Issue/PR:** ThoughtSnap Labs Engineering Standard v1.
- **Status:** active

### LRN-2026-002 — Cloud task environments may lack package or Git access

- **Date:** 2026-07-21
- **Project area:** infrastructure
- **Severity:** high
- **Detected by:** Codex task
- **Symptom:** Dependency installation returned registry/proxy `403` errors and the task checkout had no configured `origin`, preventing complete validation and push.
- **Root cause:** The execution environment did not have the required outbound package access and repository remote configuration.
- **Fix:** Treat environment capability checks as part of task orientation. Use GitHub-connected/cloud environments with package access, or document the blocker while preserving generated work for a capable environment.
- **Regression protection:** Before significant implementation, verify package installation, repository remote, branch, push capability, and CI availability.
- **Repository-wide search:** Applies to every automated ThoughtSnap Labs project.
- **Prevention rule:** Agents must perform an environment preflight before spending a full run on implementation that cannot be validated or published.
- **Promoted to standard:** To be added to future ThoughtSnap Labs automation templates.
- **Issue/PR:** Cassiano.ai Branch 1 task.
- **Status:** active
