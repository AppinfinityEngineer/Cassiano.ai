# Cassiano.ai Architecture Decisions

## ADR-001 — Productised service before autonomous agent platform

**Status:** Accepted  
**Context:** V1 must be commercially usable without depending on unsupported automation for creating or transferring Custom GPTs.  
**Decision:** Build the sales, intake, fulfilment, QA, delivery, and revision operating system. Cassiano staff manually create the final Custom GPT in V1.  
**Consequences:** Faster and safer launch; human QA remains central; automatic GPT creation is excluded until a supported, reliable API exists.

## ADR-002 — Full payment upfront in V1

**Status:** Accepted  
**Context:** Deposits and balance collection add order states, webhooks, delivery locks, support complexity, and invoice chasing.  
**Decision:** V1 uses one configurable package with full Stripe payment upfront.  
**Consequences:** Simpler checkout and operations. Deposit/balance flows may be reconsidered after real conversion evidence.

## ADR-003 — Sequential autonomous branches

**Status:** Accepted  
**Context:** Early branches establish architecture used by every later feature. Parallel implementation would increase merge conflicts and inconsistency.  
**Decision:** Execute the ordered branch plan sequentially through the release candidate.  
**Consequences:** Lower drift and simpler recovery. Parallel work may be introduced later only for genuinely independent tasks.

## ADR-004 — Provider abstractions with safe development adapters

**Status:** Accepted  
**Context:** Production credentials may not be available during autonomous development.  
**Decision:** External services use interfaces plus real production adapters and safe local/test adapters. Missing credentials must not be represented as successful production validation.  
**Consequences:** Development continues without secrets while preserving production-ready integration boundaries.

## ADR-005 — Private file storage outside MongoDB

**Status:** Accepted  
**Context:** Customer documents are confidential business assets and may be large.  
**Decision:** Store binaries in private S3-compatible object storage; store metadata and ownership in MongoDB; use short-lived signed access.  
**Consequences:** Stronger security and scalability, with storage provider configuration required before production.
