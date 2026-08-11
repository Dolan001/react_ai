# React production delivery reference

Load this reference only for React creation, feature implementation, or verification.

## Structure and rendering

- Pin Node, package manager, React, TypeScript, router, build, lint, and test versions;
  commit one lockfile. Enable strict types and validate environment variables.
- Routes compose feature boundaries. Features own product behavior; UI primitives own
  reusable presentation; network code stays behind typed adapters.
- Keep state at the nearest stable owner. Use URL state for shareable navigation,
  server/cache state for remote data, form state for editing, and global state only for
  genuinely application-wide concerns.
- Preserve semantic approved HTML and visual hierarchy. Do not copy untrusted scripts,
  inline handlers, tracking code, or unsafe markup from supplied HTML.

## Interaction, data, and security

- Every route covers loading, empty, success, validation, recoverable error,
  authorization failure, offline/timeout, and unexpected error states as applicable.
- Generate types from the stable API contract and validate untrusted responses at
  runtime. Centralize base URL, credentials, cancellation, retry policy, and error
  normalization. Never retry non-idempotent writes blindly.
- Do not place secrets in client bundles. Avoid unsafe HTML; if product requirements
  demand rich HTML, sanitize with a reviewed policy and test malicious inputs.
- Authentication UI does not authorize. Handle token/session expiry, logout, CSRF if
  cookies are used, redaction, and sensitive data persistence explicitly.

## Accessibility, responsiveness, and performance

- Use native elements, programmatic labels, logical heading order, visible focus,
  keyboard-complete interactions, meaningful status announcements, and reduced motion.
- Verify target viewport widths from the design contract plus narrow/mobile, tablet,
  desktop, zoom, long text, and empty/overflow conditions.
- Reserve dimensions for media, lazy-load below-fold work, split at route boundaries,
  and measure bundle/render behavior before introducing memoization.

## Verification

- Focused lane: format, lint, strict types, changed unit/component tests, accessibility
  assertions, and the affected route journey.
- Full lane: all tests, production build, browser journeys against a live backend,
  contract failures, responsive screenshots, visual comparison, accessibility scan,
  and bundle/performance budgets.
- Compare screenshots at deterministic viewport, font, data, animation, and clock
  settings. Review differences; never update baselines merely to make CI green.
- Evidence records exact argv, cwd, exit code, browser/viewport, artifact paths, and
  requirement IDs. A mock-only journey cannot verify backend integration.
