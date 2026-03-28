# chorbit-client

Frontend for **Chorbit** — chore tracking for groups, inspired by Tricount.

## Stack

| Package | Purpose |
|---------|---------|
| React | UI framework |
| Vite | Build tool + dev server |
| TypeScript | Strict mode |

**Planned**: Apollo Client (GraphQL), Zustand (local state), TailwindCSS (styling), Vitest (testing)

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
npm install
npm run dev              # start Vite dev server
```

## Test
```bash
npm test                 # Vitest (when configured)
npm run typecheck        # tsc --noEmit
npm run lint             # ESLint
```

## Conventions
- TypeScript strict, no `any`
- Named exports only (no default exports)
- Functional components only (no class components)
- Zustand for UI-only state (modals, sidebar) — server state lives in Apollo cache
- TailwindCSS for all styling (no CSS modules or styled-components)
- Secrets via env vars only

## Key Patterns
- Apollo Client connects to `http://localhost:4000/graphql` in dev
- Pages map 1:1 to routes
