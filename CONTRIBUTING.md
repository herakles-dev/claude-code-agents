# Contributing

Thanks for considering a contribution. This is a small, curated set of agents — contributions are welcome, but the bar is "does this earn its place," not "does this add coverage."

## Adding or improving an agent

- One agent, one `.md` file, one clear job. If an agent's description needs "and" three times to explain what it does, it's probably two agents.
- Keep it general-purpose and transferable. If it only makes sense against one specific codebase, deployment, or company's internal tooling, it doesn't belong in this repo.
- Match the existing frontmatter shape (`name`, `description`, and whatever else the surrounding agents in that package use) so a package stays internally consistent.
- Update that package's `README.md` table with a one-sentence, plain-English description — what it does and when to reach for it. No adjective inflation.
- If you're proposing an agent that overlaps heavily with an existing one, say so explicitly and explain why it's not a duplicate (or propose merging into the existing one instead).

## Reporting a problem

- Open an issue describing what you expected the agent to do and what it actually did.
- If it's a specific prompt/output that didn't work, include enough of it to reproduce — redact anything sensitive first.

## Pull requests

- Keep PRs scoped to one agent or one package where possible; it makes review faster and honest.
- Explain the "why" in the PR description, not just the "what" — the same standard the agents themselves are held to.

## What this isn't

This isn't a place for general Claude Code questions, feature requests for Claude Code itself, or domain-specific agents unrelated to general software engineering, DevOps, security, or Claude Code usage. Those are better directed elsewhere.
