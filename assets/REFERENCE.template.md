<!--
REFERENCE template — the code map. Graduate here from the README when the map
outgrows the quickstart. Audience: future Claude + curious devs. Documents
STRUCTURE — keep it in sync when you move or add things.
-->

# REFERENCE — codebase map

> What is where, and how it's divided. Sibling docs (mutually exclusive):
> [README.md](README.md) = run it & the shape · [DECISIONS.md](DECISIONS.md) = why it's built this way.
> Keep this in sync when you move or add things.

## 1. What this repo is
{{1–3 sentences; if it's two halves living together, name them.}}

## 2. Top-level layout
| Path | What |
|------|------|
| `{{path/}}` | {{…}} |

## 3. {{Main package}} — file by file
| File | Responsibility |
|------|----------------|
| `{{file.py}}` | {{…}} |

<!-- If there's a registry/catalog (blocks, plugins, commands), table it here. -->

## 4. {{Runtime / data flow}}
{{How a request/run actually moves through the system; the key entry points.}}

## 5. HTTP surface & URL topology
<!-- If applicable: how the frontend path maps to backend routes. -->
| Method + path | Purpose |
|---------------|---------|
| `{{GET /…}}` | {{…}} |

## 6. Invariants & gotchas (read before editing)
1. {{identifier namespaces / "must be named exactly X" / license bar / …}}

## 7. How to add a new {{thing}} (checklist)
1. {{step}}
2. {{step}}

## 8. Validate / run
```bash
{{syntax check / typecheck / build / e2e proof — copy-pasteable}}
```

## 9. Deeper notes
- {{[DECISIONS.md](DECISIONS.md) — decisions & rationale}}
- {{source of truth for X}}
