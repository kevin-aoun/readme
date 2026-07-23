<!--
README template — the hub. Delete sections a project doesn't need.
Keep the "builders' tail" (Design decisions / Code map) INLINE here until it
graduates into DESIGN.md / REFERENCE.md (see reference/doc-set.md).
Fill every {{…}}. If a fact isn't discoverable, leave a TODO — never invent.
-->

# {{Project Name}}

{{One sentence: what it does + core stack.}} Built with {{**X**, **Y**, **Z**}}.
<!-- Badges (public/OSS only): build · version · license -->

## What it does

{{2–4 sentences, or a short bullet list of the capabilities / "halves".}}

> **Design principle:** {{the one rule that explains a lot of the codebase — delete if none}}

## Ports & Services
<!-- Delete for a library/CLI. -->
| Port | Service | Description |
|------|---------|-------------|
| {{8000}} | {{API}} | {{…}} |

## Prerequisites
| Tool | Version | Check | Install |
|------|---------|-------|---------|
| {{Python}} | {{3.10+}} | `{{python --version}}` | {{link}} |

## Getting Started
<!-- Use Option A/B only if there are genuinely two paths. Always end with a verify step. -->
1. `{{cp .env.example .env}}`  → set `{{REQUIRED_KEY}}`
2. `{{docker compose up -d --build}}`
3. **Verify** → {{open http://localhost:8000/docs — Swagger loads}}

## Architecture
<!-- ONE diagram that earns its place. -->
```mermaid
flowchart TD
  {{A}} --> {{B}} --> {{C}}
```
{{One sentence stating the layering/coupling rule.}}

| Module | Role |
|--------|------|
| `{{module/}}` | {{what it does}} |

## Where to put new code
| If you want to add… | Put it in… | Example |
|---------------------|------------|---------|
| {{a new endpoint}} | {{`module/router.py`}} | {{`parser/router.py`}} |
| {{a new integration}} | {{`integrations/<name>/`}} | {{`…/notion/`}} |

## API
<!-- Group by module. Point to /docs for request bodies instead of duplicating them. -->
### {{Group}}
| Method | Path | Description |
|--------|------|-------------|
| {{POST}} | `{{/api/v1/…}}` | {{…}} |

## Configuration
| Variable | Required | Description |
|----------|----------|-------------|
| `{{LLM_API_KEY}}` | {{Yes}} | {{…}} |

> {{Secrets policy — where keys live, what's server-only.}}

## Workflow example
```bash
# 1. {{ingest}}
{{curl -X POST …}}
# 2. {{ask}}
{{curl -X POST …}}
```

<!-- ────────────── builders' tail: inline until it graduates ────────────── -->

## Design decisions
<!-- Graduate to DESIGN.md when this grows. Record the rejected alternative. -->
| Decision | Why it holds up (and what we rejected) |
|----------|----------------------------------------|
| {{choice}} | {{rationale; rejected: {{alt}} because {{reason}}}} |

## Code map
<!-- Graduate to REFERENCE.md when this dwarfs the quickstart. -->
| Path | Responsibility |
|------|----------------|
| `{{path}}` | {{…}} |

### Invariants & gotchas (read before editing)
1. {{the thing that breaks if you rename/move it wrong}}

## Docs
- {{[REFERENCE.md](REFERENCE.md) — where the code lives}}
- {{[DESIGN.md](DESIGN.md) — decisions & the model}}
- Source of truth: {{`/docs` (Swagger) for request bodies}}
