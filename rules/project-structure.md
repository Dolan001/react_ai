# Generated React structure

The agent generates this structure under target `apps/frontend/`. Router and build
tool choices are recorded from project constraints; route/feature names come from the
requirements.

```text
apps/frontend/
├── package.json
├── package-lock.json
├── tsconfig.json
├── vite.config.ts
├── eslint.config.js
├── playwright.config.ts
├── vitest.config.ts
├── index.html
├── .env.example
├── .gitignore
├── .dockerignore
├── Dockerfile
├── README.md
├── public/
├── src/
│   ├── main.tsx
│   ├── app/
│   │   ├── App.tsx
│   │   ├── router.tsx
│   │   ├── providers.tsx
│   │   └── styles.css
│   ├── routes/
│   │   ├── RootRoute.tsx
│   │   ├── NotFoundRoute.tsx
│   │   └── <FeatureRoute>.tsx
│   ├── features/
│   │   └── <feature>/
│   │       ├── components/
│   │       ├── hooks/
│   │       ├── schemas.ts
│   │       ├── types.ts
│   │       └── tests/
│   ├── components/
│   │   ├── ui/
│   │   └── shared/
│   ├── services/
│   │   ├── api-client.ts
│   │   └── errors.ts
│   └── lib/
│       ├── env.ts
│       └── utilities.ts
├── tests/
│   ├── setup.ts
│   └── e2e/
└── scripts/
    └── validate_project.mjs
```

Ownership:

- `src/app`: application assembly, providers, router, and global styles.
- `src/routes`: route-level composition only.
- `src/features`: cohesive product behavior with colocated validation and tests.
- `src/components/ui`: reusable presentation primitives without business behavior.
- `src/services`: typed network boundaries and standard client errors.
- `src/lib`: validated environment access and framework-neutral utilities.
- shared API types/client are generated under target `packages/` when required.

Generation order:

1. Resolve supported Node, React, TypeScript, router, and build-tool versions.
2. Create strict configuration, environment validation, app assembly, routing,
   dependency lock, and test foundations.
3. Convert approved design evidence into semantic route/feature boundaries.
4. Generate only requirement-backed features.
5. Connect the generated typed API client and runtime-validate responses.
6. Add unit, integration, accessibility, responsive, and visual tests.
7. Add target-owned Docker and CI after the production build passes.
