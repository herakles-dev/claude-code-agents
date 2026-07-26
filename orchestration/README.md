# orchestration

Agents for building, routing, and running other agents — the meta layer of a Claude Code agent fleet — plus a general-purpose, nine-agent pipeline for spec-driven development (plan → architect → implement → integrate → test → review → security → optimize → recover). Nothing here is tied to a specific stack or domain.

| Agent | What it does / when to reach for it |
|---|---|
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

The nine `spec-*` agents form one coherent pipeline end to end; use as many or as few stages as a given project needs. The four non-`spec` agents (`agent-architect`, `agent-assignment`, `agent-optimizer`, `meta-agent`) are the tools you use to build and maintain the agent fleet itself, independent of any one project.
