# devops

Infrastructure and operations agents — CI/CD, containers, reverse proxy, logs, and reliability. General-purpose; not tied to any particular hosting setup.

| Agent | What it does / when to reach for it |
|---|---|
| `ci-cd-architect.md` | Builds CI/CD pipelines, Docker build steps, deployment automation, health checks, and rollback strategy. Reach for it when setting up or overhauling a build/deploy pipeline. |
| `container-manager.md` | Manages Docker containers via a container-control API — status, pause/resume, resource analysis. Reach for it for day-to-day container operations. |
| `log-analyst.md` | Digs through structured logs for error patterns, cross-service correlation, and root cause. Reach for it when something broke and the log volume is too big to eyeball. |
| `nginx-manager.md` | Automates nginx site configuration — add/remove sites, SSL certs, config validation. Reach for it for reverse-proxy and TLS setup. |
| `sre-specialist.md` | Site-reliability work: incident response, SLOs, observability setup, runbooks, and monitoring/alerting. Reach for it for anything about keeping a running system reliable, including logging/metrics/alerting setup. |

## Considered and skipped

`monitoring-specialist.md` was requested for this package but was left out on purpose: `sre-specialist.md`'s own description states it has absorbed monitoring-specialist's capabilities (logging, metrics, alerting, dashboards), and its body covers that ground directly. Carrying the older one forward alongside its explicit successor would just be duplication.
