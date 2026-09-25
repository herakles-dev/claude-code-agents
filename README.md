# claude-code-agents

A curated, transferable set of Claude Code agents, organized into small installable packages by theme. This isn't an export of everything — it's a hand-picked slice of a larger working agent fleet, kept small on purpose. Quality and coherence over volume: every agent here earned its place because it's general-purpose, stands on its own, and isn't tied to one specific deployment.

Pull the package folder you need and drop its `.md` files into your own project. Done.

## Package index

| Package | Agents | Purpose |
|---|---|---|
| [`orchestration/`](orchestration/) | 16 | Building, routing, and running other agents, plus a general-purpose nine-stage spec-driven development pipeline (plan → architect → implement → integrate → test → review → security → optimize → recover), plus a wave-level + per-task adversarial review/fix trio. |
| [`engineering/`](engineering/) | 7 | General-purpose software engineering: backend, frontend, database, TypeScript, testing, code quality, documentation. |
| [`security/`](security/) | 6 | Application security, privacy compliance, and bug-bounty report writing. |
| [`devops/`](devops/) | 5 | CI/CD, containers, nginx, log analysis, site reliability. |
| [`claude-code/`](claude-code/) | 2 | Configuration helpers for Claude Code itself — status line/output styles/preferences, and Skills lifecycle management. |

**36 agent files across 5 packages** (`code-quality-engineer` is intentionally shipped in both `engineering/` and `security/` since it's directly relevant to both workflows — 35 agents, one deliberate duplicate).

Each package has its own `README.md`: a short "what this is for," a table of every agent with a one-sentence description of what it does and when to reach for it, and notes on anything that was considered for inclusion and left out (with the reason).

## How to use

1. Pick a package folder — or a single agent `.md` file — that matches what you're working on.
2. Copy the file(s) into your project's `.claude/agents/` directory.
3. That's it. Claude Code picks up any `.md` file dropped into `.claude/agents/` as an available agent; no build step or registration required.

Agents are independent — you don't need the whole package to use one agent out of it. Read the agent's frontmatter and opening section before relying on it; a few reference conventions (like a task-tracking protocol) that make the most sense if your project has something similar in place, but the core capability works standalone.

## Featured, published separately

Two tools that started life in this fleet outgrew "agent definition" and became their own standalone projects — linked here, not copied into this tree:

- **[opensource-pipeline](https://github.com/herakles-dev/opensource-pipeline)** — a fork/sanitize/package pipeline for open-sourcing a project; also merged into a 233k-star community Claude Code repository.
- **[ansi-stream-guard](https://github.com/herakles-dev/ansi-stream-guard)** — a 130-line ANSI-escape-boundary reassembler, with 12 tests.

## What was deliberately left out

This is a curated release, not a full export. Some agents and entire agent families were excluded on purpose:

- Claude Code's own internal-architecture agents — agent coordination internals, MCP implementation, tool execution pipeline, prompt-assembly, and safety-architecture detail — not meant for external release, plus anything sourced from leaked material — excluded categorically. `claude-code/` ships only the one configuration-focused agent that doesn't touch that internal surface.
- A larger bug-bounty-hunting agent family, except the one report-writing agent (no offensive tooling) — the hunting/auth/recon/automation/orchestration members of that family are excluded.
- Several domain-specific agent families (music production, political analysis, and similar) — out of scope for a Claude Code engineering-agent release.

Package-level READMEs note anything that was specifically requested for that package and left out, with the reason (usually: superseded by a newer agent already in the package, or genuinely doesn't exist anywhere in the source collection).

## Honesty note

These agents are extracted from a working private platform and generalized for public use — they aren't written from scratch as a demo. Expect the occasional rough edge as a result; a sanitization pass runs after this one to scrub anything deployment-specific that slipped through.

## License

MIT — see [`LICENSE`](LICENSE). Contributions welcome — see [`CONTRIBUTING.md`](CONTRIBUTING.md).
