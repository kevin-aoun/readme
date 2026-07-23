# The doc-set — roles, graduation rule, cross-linking

Docs start as **one README** and split only when a concern outgrows the hub.
This file defines the sibling roles and *when* to peel each one off.

## Roles (one job per doc)

| Doc | Job | Primary reader | Lives where |
|---|---|---|---|
| **README.md** | The hub: what it is, run it, the shape of it. Human-first, agent-readable. | new users + everyone | always |
| **REFERENCE.md** | **Where the code lives** — file-by-file map, HTTP surface, invariants/gotchas, "add a new X" checklist. | future Claude + curious devs | when the code map dwarfs the quickstart |
| **DECISIONS.md** | **Why it's built this way** — decisions with rejected alternatives, the execution/state model. | future Claude + curious devs | when decisions accumulate |
| **DOCS.md** *(optional)* | Per-component reference (each block/module: what it does, config, I/O). | devs building *with* the components | when components are many and stable |
| **TODO.md** *(optional)* | Open decisions parked for input (newest first); shipped work → CHANGELOG. | maintainers | when decisions outlive a session |

These aren't "internal vs public" — a good README serves both audiences at once
(mermaid + quickstart for humans; precise tables + a code map for agents).
REFERENCE and DECISIONS simply go **deeper** for readers who need the why/where.

## The graduation rule

**Default: single file.** Keep *Design decisions* and *Code map* concatenated at
the **end** of the README (after the user-facing sections) — the RAG-API style.
A newcomer still hits "run it" first; the why/where sinks to the bottom.

**Graduate a section into its own sibling when any of these is true:**
- it's grown past **~1–2 screens** and has a different cadence than getting-started;
- the **decision log** has several `rejected-alternative` entries → **DECISIONS.md**;
- the **code map** becomes a file-by-file table longer than the quickstart → **REFERENCE.md**;
- **per-component** docs repeat the same shape many times → **DOCS.md**;
- **open decisions** pile up and outlive the current session → **TODO.md**.

**When you graduate:** replace the inline section with a **one-line pointer**, move
the content verbatim into the sibling, and cross-link back. The README stays the hub.

```md
## Design decisions
The reasoning and rejected alternatives live in [DECISIONS.md](DECISIONS.md).
```

## Cross-linking discipline

- Every sibling opens with a one-line "**what this is / what it's not**" and links
  its siblings (mutually exclusive: "this = blocks · REFERENCE = where code lives · DECISIONS = why").
- The README's **Docs map** section links every sibling.
- Name the **source of truth** for anything generated or live (Swagger/OpenAPI for
  request bodies, a schema file for data shapes, Claude memory for strategy).
- Relative links only (`[REFERENCE.md](REFERENCE.md)`), so they work on GitHub and locally.

## Keep-in-sync note

Docs drift the moment code moves. Two cheap habits:
- Put a line in REFERENCE.md: *"documents structure — keep in sync when you move/add things."*
- Prefer **pointers to the source of truth** over copies (link Swagger; don't paste every request body). The less duplicated, the less rots.
