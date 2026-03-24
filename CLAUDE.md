# chorbit-client

React 18 + Vite + TypeScript + Zustand + Apollo Client + TailwindCSS.

For project-wide context, see `../chorebit-vault/README.md`.

## Stack
| Package | Purpose |
|---------|---------|
| React 18 | UI framework |
| Vite | Build tool + dev server |
| Apollo Client | GraphQL client, connects to chorbit-server `/graphql` |
| Zustand | Local state management (non-server state) |
| TailwindCSS | Utility-first CSS |
| Vitest | Testing (Vite-native) |

## Structure
```
src/
  components/   ← React components
  pages/        ← route-level components
  graphql/      ← queries, mutations, fragments
  stores/       ← Zustand stores
  lib/          ← Apollo Client setup, utilities
```

## Run
```bash
npm run dev              # start Vite dev server
```

## Test
```bash
npm test                 # run Vitest
npm run typecheck        # tsc --noEmit
npm run lint             # ESLint
```

## Key Patterns
- Apollo Client connects to `http://localhost:4000/graphql` in dev
- Zustand for UI-only state (modals, sidebar, etc.) — server state lives in Apollo cache
- TailwindCSS for all styling, no CSS modules or styled-components
- Pages map 1:1 to routes

## Vault Workflow
1. **Before implementing**: Read the relevant feature spec in `../chorebit-vault/features/` and any referenced architecture or decision docs
2. **After implementing**: Update the feature spec to reflect what was actually built (if anything diverged from the plan)
3. **If you make an architectural decision**: Write an ADR to `../chorebit-vault/decisions/` using the template

## Conventions
- TypeScript strict, no `any`
- Functional components only (no class components)
- No default exports (named exports only)
- Commit format: `type: description (#issue)`
