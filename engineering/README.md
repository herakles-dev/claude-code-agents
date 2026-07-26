# engineering

General-purpose software engineering agents — backend, frontend, database, TypeScript, testing, and code quality. Stack-aware but not project-specific; drop these into any codebase.

| Agent | What it does / when to reach for it |
|---|---|
| `backend-architect.md` | Designs backend APIs, auth, and middleware, and proactively flags bugs while it does. Reach for it when standing up a new service or endpoint. |
| `code-quality-engineer.md` | Reviews code for quality and security (OWASP Top 10, SOLID principles), then refactors and pays down technical debt. The merged successor to what were previously separate code-review and refactoring agents. Reach for it after a feature is working and before it merges. |
| `database-engineer.md` | Designs schemas, writes migrations, and optimizes queries across PostgreSQL, MongoDB, and Redis. Reach for it for anything touching data modeling or query performance. |
| `frontend-specialist.md` | Builds and optimizes React/Next.js/Vue UIs — state management, responsive layout, performance. Reach for it for UI work of any real size. |
| `testing-engineer.md` | Writes unit, integration, and E2E tests and drives TDD workflows with a coverage strategy. Reach for it when a feature needs a real test plan, not just a couple of assertions. |
| `typescript-specialist.md` | TypeScript type-system design, JS→TS migrations, strict mode, and advanced generic patterns. Reach for it for type-level problems that go beyond routine annotation. |

## Considered and skipped

`refactoring-consultant.md` was requested for this package but was left out on purpose: `code-quality-engineer.md`'s own description states it directly replaces the older code-reviewer and refactoring-consultant agents, and its body covers the same code-smell/SOLID/technical-debt ground. Carrying the older one forward alongside its explicit successor would just be duplication.
