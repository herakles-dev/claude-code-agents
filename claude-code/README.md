# claude-code

Configuration helpers for Claude Code itself: status line, output styles, preferences, workflow customization, and Skills lifecycle management. Reach for these when you're tuning your own Claude Code setup rather than working on a project.

| Agent | What it does / when to reach for it |
|---|---|
| `claude-code-config.md` | Configures Claude Code itself — status line, output styles, preferences, and workflow customization. Reach for it when tuning your own setup rather than a project. |
| `skills-manager.md` | Creates, edits, validates, and maintains Claude Code Skills (the `SKILL.md` + YAML frontmatter files under `.claude/skills/`) — description optimization, format validation, agent-skill mapping. Reach for it when adding or cleaning up your own Skills rather than agents. |

## Not included by design

This package intentionally ships a small, narrowly-scoped pair of agents. A handful of Claude Code internal-architecture agents (agent coordination internals, MCP implementation details, tool execution pipeline, prompt-assembly, and safety-architecture internals) were excluded — that's implementation detail not meant for external distribution, not general-purpose configuration guidance.
