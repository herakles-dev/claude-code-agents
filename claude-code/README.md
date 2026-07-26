# claude-code

A configuration helper for Claude Code itself: status line, output styles, preferences, and workflow customization. Reach for it when you're tuning your own Claude Code setup rather than working on a project.

| Agent | What it does / when to reach for it |
|---|---|
| `claude-code-config.md` | Configures Claude Code itself — status line, output styles, preferences, and workflow customization. Reach for it when tuning your own setup rather than a project. |

## Not included by design

This package intentionally ships a single, narrowly-scoped agent. A handful of Claude Code internal-architecture agents (agent coordination internals, MCP implementation details, tool execution pipeline, prompt-assembly, and safety-architecture internals) were excluded — that's implementation detail not meant for external distribution, not general-purpose configuration guidance.
