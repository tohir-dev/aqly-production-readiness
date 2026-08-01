# Production Readiness — the launch-blocker gate for Claude

"Is this ready to ship?" is usually answered by whoever wrote it, from memory, at the end of a long
day. This skill replaces that with a gate: a fixed MUST-HAVE checklist, scaled to the size of what
you built, where **every item has to be answered with evidence** and the verdict is a hard pass or
fail.

The rule that makes it useful: an item claimed met with no evidence is **not met**. If the
dependency scanner was never run, that is an unmet item — not a pass by default. If a restore path
exists but was never tested, that is not a backup story.

## What it checks

**Security** — secrets out of source, input validated at trust boundaries, server-side
authorization, a real dependency scan with output shown, TLS and encryption at rest.

**Reliability** — no silent failures, timeouts and retries on external calls, health checks, graceful
shutdown.

**Data & recovery** — a backup story with a *tested* restore, backward-compatible migrations.

**Observability** — structured logs on important paths, traceable key operations.

**Release safety** — reproducible build from a clean checkout, automated build and test that passes,
a documented rollback path, config separated from code.

**Docs & legal** — an honest README including limitations, dependency license conflicts checked, a
LICENSE file, a CHANGELOG entry.

Plus a SHOULD-HAVE maturity list (SBOM, canary rollout, DR game-days, distributed tracing, on-call)
recorded as follow-ups — never as blockers on a small build.

Items marked *(always)* cannot be waived at any size. Everything else scales: a local CLI is not held
to a multi-region SaaS bar.

## Install

**Project scope** — available in one repo:

```bash
mkdir -p .claude/skills && cp -R production-readiness .claude/skills/
```

**Personal scope** — available everywhere:

```bash
mkdir -p ~/.claude/skills && cp -R production-readiness ~/.claude/skills/
```

## Try it

```
Are we ready to ship this? Run the production readiness gate.
```

```
Gate this service before I deploy it Friday.
```

You get every item marked met (with the evidence), not met (with what is missing and who owns it), or
N/A (with a reason) — then a `pass` or `fail` verdict.

## Works well with

The **Software Team** skill, whose `sre-readiness` agent uses this as its final gate before delivery.
It also stands entirely on its own — point it at any repo.

## Requirements

- Claude Code (or any Claude client that supports skills).
- Whatever tooling your stack needs for the checks it runs (test runner, dependency scanner). The
  skill will report a missing scanner as an unmet item rather than skipping it.
- No API keys, no external services. One Markdown file.

## License

See [LICENSE](LICENSE).

---

### Part of Aqly Skills

Six other standalone multi-agent skills for Claude Code, each sold separately:

- [software-team](https://github.com/tohir-dev/aqly-software-team) — 40-agent software company
- [research-team](https://github.com/tohir-dev/aqly-research-team) — 20-archetype research org
- [analyst-team](https://github.com/tohir-dev/aqly-analyst-team) — business-intelligence org
- [sales-team](https://github.com/tohir-dev/aqly-sales-team) — 17-role revenue engine
- [marketing-team](https://github.com/tohir-dev/aqly-marketing-team) — 15-agent marketing agency
- [financist-team](https://github.com/tohir-dev/aqly-financist-team) — 8-lens finance analysis
