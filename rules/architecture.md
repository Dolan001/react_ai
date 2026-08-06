# Architecture rules

- Generate frontend source only in target `apps/frontend/`.
- Keep route, feature, shared UI, state, and service boundaries explicit.
- Keep backend business logic out of the browser.
- Consume a generated typed API client and runtime-validate untrusted data.
- Provide explicit loading, empty, error, retry, and success states.
