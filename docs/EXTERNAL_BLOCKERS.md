# Cassiano.ai External Owner Blockers

Development must continue around these items. They block only the named production actions.

## BLOCKER-001 — Repository visibility review

**Status:** Owner action required before sensitive implementation or production use  
**Current state:** The GitHub repository is public.  
**Why it matters:** Source code can remain public if intentionally open source, but product strategy, security configuration, future operational details, and accidental sensitive content receive greater exposure. Customer data and secrets must never enter the repository regardless of visibility.  
**Owner action:** Decide whether `AppinfinityEngineer/Cassiano.ai` should remain public or be changed to private before production.  
**Unblocked work:** All V1 development using synthetic data and environment-variable placeholders.

## BLOCKER-002 — Production service credentials

**Status:** Not yet required  
**Required later:** MongoDB Atlas, Stripe, private object storage, transactional email, hosting, and monitoring credentials.  
**Owner action:** Supply through each platform's managed secret configuration when production/staging integration is ready. Never paste credentials into issues, pull requests, code, or documentation.  
**Unblocked work:** Implement provider interfaces, development adapters, mocks, contract tests, and `.env.example` files.

## BLOCKER-003 — Live commercial configuration

**Status:** Owner approval required before launch  
**Items:** Final package price, live Stripe product/price, refund approach, delivery promise, business contact details, and approved legal wording.  
**Owner action:** Approve these during the production-readiness branch.  
**Unblocked work:** Use configurable test-mode values and clearly marked legal placeholders.

## BLOCKER-004 — Domain and production deployment

**Status:** Owner approval required  
**Items:** Cassiano.ai DNS, hosting creation/configuration, production deployment, and live payments.  
**Owner action:** Explicitly approve irreversible or chargeable production actions.  
**Unblocked work:** Build and validate deployment manifests and staging-ready documentation.
