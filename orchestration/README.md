# orchestration

Agents for building, routing, and running other agents — the meta layer of a Claude Code agent fleet — plus a general-purpose, nine-agent pipeline for spec-driven development (plan → architect → implement → integrate → test → review → security → optimize → recover), plus a wave-level adversarial review/fix lane that runs alongside it. Nothing here is tied to a specific stack or domain.

| Agent | What it does / when to reach for it |
|---|---|
| `adversarial-reviewer.md` | Reviews a batch ("wave") of already-completed work across five lenses — code quality, completeness, integration, security, and architectural rationale — and defaults to assuming issues exist until proven otherwise. Read-only; reports findings, doesn't fix them. Reach for it after a chunk of work lands and before the next chunk builds on top of it, as a complement to `spec-reviewer-v11`'s per-task review. |
| `adversarial-lite-reviewer.md` | The fast, scoped counterpart to `adversarial-reviewer.md` — reviews a single completed task's own changed files only (not the wider repo) across four lenses, including a causal-claim audit that checks whether "this fixes X" commit language is actually backed by a measurement rather than asserted. Read-only, ~2-3k token budget. Reach for it as a cheap per-task gate rather than `adversarial-reviewer.md`'s heavier wave-level pass. |
| `adversarial-lite-fixer.md` | Applies the smallest possible fix for each LOW/MEDIUM/HIGH finding from a prior review pass, refuses to touch anything CRITICAL, and re-verifies only the files it touched. Reach for it right after `adversarial-lite-reviewer.md` (or any reviewer emitting the same structured error list) to burn down findings without expanding scope. |
| `agent-architect.md` | Builds new specialized Claude Code agents — wires in schema, task-list protocol, and handoff conventions — so you don't hand-write agent boilerplate from scratch. Reach for it when adding a new agent to your own fleet. |
| `agent-assignment.md` | Reviews a task plan and recommends which agent should own each task, plus any specialist overrides. Read-only advisory — it produces a routing plan, it never spawns or edits anything itself. Reach for it when a plan has many tasks and it's not obvious who should do what. |
| `agent-optimizer.md` | Audits an existing agent ecosystem, flags duplicate or overlapping agents, tightens prompts, and surfaces coverage gaps. Reach for it periodically as a fleet grows, to keep it from sprawling. |
| `meta-agent.md` | The agent-lifecycle manager — create, upgrade, merge, or retire agents from a single entry point. Reach for it as the day-to-day tool for maintaining the fleet itself. |
| `spec-architect-v11.md` | Designs system architecture for a complex or novel problem before implementation starts. |
| `spec-implementer-v11.md` | Writes the actual code and business logic for a planned task. |
| `spec-integrator-v11.md` | Coordinates multi-service integration and API contracts across a project with more than one moving service. |
| `spec-optimizer-v11.md` | Profiles and optimizes performance bottlenecks once something is working but slow. |
| `spec-planner-v11.md` | Kicks off a session — breaks a goal into a concrete task plan and sets up tracking. Usually the first agent in the pipeline. |
| `spec-recovery-v11.md` | Handles rollback and failure recovery when a task or deployment goes wrong mid-flight. |
| `spec-reviewer-v11.md` | Runs code review, PR review, and design critique before work is considered done. |
| `spec-security-v11.md` | Designs and validates security architecture — threat modeling, OWASP checks — for the current session's scope. |
| `spec-tester-v11.md` | Runs a tiered (syntax → functional → integration → regression) test/validation pass. |

The nine `spec-*` agents form one coherent pipeline end to end; use as many or as few stages as a given project needs. The four non-`spec` agents (`agent-architect`, `agent-assignment`, `agent-optimizer`, `meta-agent`) are the tools you use to build and maintain the agent fleet itself, independent of any one project. `adversarial-reviewer`, `adversarial-lite-reviewer`, and `adversarial-lite-fixer` are a review/fix trio that can run alongside the pipeline rather than as one of its numbered stages — the lite reviewer feeds the fixer directly, and the heavier wave-level reviewer is there for batches of work too large for the lite pass's ~2-3k token budget.
