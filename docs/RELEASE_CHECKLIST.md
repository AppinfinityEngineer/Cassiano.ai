# ThoughtSnap Labs Release Checklist

## Product

- [ ] Approved V1 scope and acceptance criteria are complete.
- [ ] No functional-looking placeholders or fake integrations remain.
- [ ] Onboarding, primary value flow, failure recovery, and support guidance are verified.
- [ ] Known limitations are documented honestly.

## Quality

- [ ] Formatting, linting, type checks, unit tests, integration tests, and production builds pass.
- [ ] Critical end-to-end journeys pass in a release-like environment.
- [ ] No unresolved critical or high-severity defects remain.
- [ ] Accessibility and responsive reviews are complete.
- [ ] Performance and dependency reviews are complete.

## Security and data

- [ ] Secret and dependency scans are clear or accepted explicitly.
- [ ] Authentication, authorisation, tenant isolation, webhook validation, and private file access are tested.
- [ ] Backup, recovery, export, deletion, retention, and audit expectations are documented.
- [ ] Production credentials are stored only in approved secret managers.

## Commercial and legal

- [ ] Pricing, entitlements, refunds, third-party costs, and payment states match the product.
- [ ] Privacy, terms, refund language, consent, and required disclosures have owner/legal approval.
- [ ] Live payment activation has explicit owner approval.

## Operations

- [ ] Production environment variables and deployment steps are documented.
- [ ] Health checks, logging, monitoring, alerting, rollback, and incident contacts are ready.
- [ ] DNS and repository visibility are appropriate.
- [ ] Release notes, version/tag, deployment evidence, and post-release checks are prepared.

Production release requires an explicit owner checkpoint even when all boxes are complete.