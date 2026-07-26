# security

Application security, privacy compliance, and bug-bounty-report-writing agents. Use these to get a security-focused second opinion on code before it ships, to keep privacy/compliance concerns visible during development, and to turn a validated vulnerability finding into a clean written report.

| Agent | What it does / when to reach for it |
|---|---|
| `security-engineer.md` | Reviews code against the OWASP Top 10 — rate limiting, CORS, input validation, security headers. Reach for it during a security-focused review pass or before a release. |
| `secure-coding-advisor.md` | Covers similar OWASP Top 10 ground, framed for development time rather than after-the-fact review: input validation patterns, XSS/CSRF prevention, secure defaults, and a pre-deployment security checklist. Reach for it while you're writing the code, not just reviewing it. |
| `api-security-expert.md` | Focuses specifically on API endpoints — rate limiting, CORS policy, API versioning, input sanitization, and API key generation/rotation. Reach for it when the surface you're hardening is a public or partner-facing API rather than a general app. |
| `data-privacy-engineer.md` | Privacy and compliance engineering — GDPR, encryption at rest/in transit, PII handling, audit logging, data retention policy. Reach for it whenever user data handling is in scope. |
| `code-quality-engineer.md` | Reviews code for quality and security (OWASP Top 10, SOLID principles), then refactors and pays down technical debt. Also shipped in `engineering/` — duplicated here on purpose since it's directly relevant to a security review pass. |
| `h1-reporter-agent.md` | Writes a professional vulnerability report from a validated finding — impact framing, evidence formatting, submission polish. This is the **only** agent pulled from a larger bug-bounty-hunting agent family; the hunting/recon/exploitation members of that family are deliberately excluded from this release (see "Not included" below). |

## Pulled from archive in this pass

`secure-coding-advisor.md` and `api-security-expert.md` were sitting in an internal archive folder rather than the live agent directory — that was an oversight, not a deliberate retirement. Both are complete, working agent definitions, still referenced by other agents' handoff chains, and cover ground (dev-time secure-coding guidance; API-specific hardening) that the other agents in this package don't fully duplicate. Added here.

## Considered and skipped

`spec-security-architect-agent.md` was also requested for this package but was left out. It's an early, thinner predecessor of the security-architecture role that `spec-security-v11.md` (in `orchestration/`) now fills — same STRIDE-threat-modeling territory, but without the OWASP/CWE mapping, secret-scanning workflow, or self-review step the current version has. It's one of fourteen sibling files from an entire earlier agent generation that's been fully retired in favor of the current one, so it wasn't carried forward.

## Not included by design

The Anthropic built-in `security-review` and `review` skills are not our work and are intentionally excluded from this package regardless of scope.

The hunting/auth/recon/automation/orchestration members of a larger bug-bounty agent family are excluded from this release — only the report-writing agent (`h1-reporter-agent.md`, no offensive tooling) made the cut.
