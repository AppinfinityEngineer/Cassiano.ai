# ThoughtSnap Labs Security Rules

- Never commit secrets, tokens, credentials, private keys, production data, or customer documents.
- Use environment-based secret injection and document every required variable in `.env.example`.
- Enforce least privilege for users, roles, services, storage, and provider credentials.
- Perform authentication, authorisation, ownership, and tenant isolation checks on the backend.
- Hash passwords using a current password-hashing algorithm; never encrypt or log plaintext passwords.
- Verify webhook signatures and implement replay-safe idempotency.
- Keep object storage private and issue short-lived signed access only after ownership checks.
- Validate file type, size, filename, and metadata; never trust extensions alone.
- Apply secure headers, CORS allow-lists, rate limits, input validation, and safe error handling.
- Avoid logging secrets, payment data, full tokens, sensitive personal data, or uploaded content.
- Maintain dependency and secret scanning in CI where supported.
- Record security-relevant changes in PR descriptions and audit critical state changes.
- Critical or high-severity security findings block merge and release.
- Production deployment, live payments, DNS changes, repository visibility changes, destructive data actions, and secret rotation require explicit owner approval.