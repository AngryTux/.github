# Orchestrator

**Secure LLM workspace manager and orchestrator.**

Run AI providers in isolated workspaces with kernel-level sandboxing, managed credentials, and full cost visibility. When you need more, orchestrate multiple providers with intelligent routing and consolidated responses.

## What it does

**Isolation** — Every LLM provider runs in its own sandboxed workspace. Credentials are encrypted and scoped. Resources are capped and monitored. Nothing leaks between workspaces.

**Management** — Track every execution: tokens consumed, cost incurred, duration, provider, model. Inspect running workspaces, view stats, audit history. Budget limits per namespace.

**Orchestration** — Coordinate multiple providers for a single task. The Arranger validates intent. The Maestro composes the plan, assigns providers, and consolidates results into one unified response.

## Repositories

| Repository | Description |
|---|---|
| [orchestrator](https://github.com/AngryTux/orchestrator) | Daemon (`orchestratord`) and CLI (`orch`). Written in Rust. |
| [repertoire](https://github.com/AngryTux/repertoire) | Provider specs, isolation profiles, formations, and integration contracts. Pure YAML. |

## Quick start

```bash
# Install
curl -fsSL https://get.orchestrator.dev | sh

# Add a provider
orch provider add claude

# Run isolated
orch run claude

# Orchestrate
orch perform "compare Redis vs Memcached for session storage"
```

## Design

- Rootless — never runs as root
- Kernel 6.12+ — modern Linux isolation primitives
- Declarative — providers, formations, and isolation are YAML specs
- Observable — real-time stats, historical metrics, audit trail

## License

MIT
