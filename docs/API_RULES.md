# ThoughtSnap Labs API Rules

- Version public APIs under a stable prefix such as `/api/v1`.
- Use consistent resource naming and HTTP semantics.
- Validate request bodies, query parameters, headers, and uploaded metadata.
- Return a documented structured error envelope with a stable code, safe message, and correlation identifier.
- Never expose stack traces, credentials, internal connection details, or sensitive records.
- Authentication and ownership checks must run server-side for every protected operation.
- Mutating endpoints must define idempotency behaviour where duplicate delivery is possible.
- Payment and webhook state must be derived from verified server-side events.
- Pagination, filtering, sorting, rate limits, and maximum page sizes must be explicit.
- Use UTC internally and ISO 8601 timestamps at boundaries.
- Prefer integer minor units for money and explicit currency codes.
- Log request outcomes and correlation identifiers without logging secrets or unnecessary personal data.
- Keep provider-specific logic behind interfaces so tests can use deterministic adapters.
- Add contract and integration tests for critical API behaviour.