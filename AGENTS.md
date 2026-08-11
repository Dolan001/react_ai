# React behavior pack

This repository contains AI behavior only and must never contain a runnable React
application or generated framework source. Agents use it while creating or adopting
`apps/frontend/` in a separate target monorepo.

Use strict TypeScript, runtime-validated API data, accessible semantic components,
explicit loading/empty/error/success states, and independent browser verification.
All writes require a task contract and target path lease.

Load agent and skill Markdown only after React is selected. JSON catalogs route the
workflow but do not replace behavioral instructions. Prefer cached discovery, bounded
context, and focused checks.
