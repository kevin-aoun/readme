---
name: readme
description: >-
  Write, update, or standardize a project's documentation — a README-as-hub
  (human-first but agent-readable: what it is, ports/services, prerequisites,
  getting-started with verify steps, an architecture diagram, a "where to put
  new code" table, endpoint/config tables) plus, when a concern outgrows the
  hub, sibling docs REFERENCE.md (code map) and DESIGN.md (decisions + why).
  Use whenever the user asks to create/refresh a README or project docs,
  document a repo, or make their docs consistent/production-grade. The skill
  SCANS the repo first, then drafts to the standard.
---

# README (project documentation)

A project's docs are a **README hub** plus optional siblings that peel off only
when they earn it. The README serves humans first (quickstart, diagram) and
agents too. Depth graduates into `REFERENCE.md` (where the code lives) and
`DESIGN.md` (why it's built this way) when it outgrows the hub — otherwise it
stays concatenated at the **end** of the README.

## Workflow

1. **Scan before you write — never invent.** Read the repo and gather the facts
   each section needs; if a fact isn't discoverable, write `<!-- TODO: … -->`
   rather than guessing. Look at:
   - manifests & entry points: `package.json`, `pyproject.toml`/`requirements.txt`, `go.mod`, `Dockerfile`, `docker-compose.yml`, `Makefile`, `.env.example`
   - the directory tree (top 2–3 levels) → the module/"where to put code" map
   - routers/handlers → the endpoint tables; config loaders → the env table
   - any existing README / docs (preserve true content, restructure the rest)
2. **Decide shape** — single-file vs graduated (see `reference/doc-set.md`).
   Default to single-file; the design/code-map tail lives at the end of the README.
3. **Draft to the standard** — canonical section order + the fill-in templates in
   `assets/`. Match the repo's real names, commands, ports, and paths.
4. **Verify** — every command is copy-pasteable, links resolve, tables have no
   empty cells, and **no endpoint/env/port is invented**. Prefer running a
   `--help`/`--version` or reading the route file over assuming.
5. **Leave a sync note** — docs drift; state where the source of truth is.

## Canonical README order (the hub)

User-facing first, "for builders" last — a newcomer hits *run it* before *why*.

1. **Title + one-line what-it-is** (badges only if public/OSS)
2. **What it does / why it exists** — 2–4 sentences; a "design principle" callout if there is one
3. **Ports & Services** — the moving-parts table (skip if not a service)
4. **Prerequisites** — tool / version / how-to-check / install
5. **Getting Started** — numbered, copy-paste, **with a verify step**; split local-vs-Docker when both exist
6. **Architecture** — *one* diagram that earns its place (mermaid) + a module/layer table
7. **Where to put new code** — the task → location → example table
8. **API / Endpoints** — grouped tables (method · path · purpose)
9. **Configuration** — env-var table (variable / required / description) + secrets policy
10. **Workflow example** — the golden path, end to end
11. *(builders' tail — inline until it graduates)* **Design decisions** · **Code map / extending**
12. **Docs map** — pointers to siblings + source-of-truth

Section-by-section detail, patterns, and mini-examples: **`reference/sections.md`**.

## Signature rules (what makes it production-grade)

- **Tables > prose** for anything enumerable (ports, env, endpoints, module map).
- **Every command copy-pasteable + a verify line** ("→ should print X").
- **Decisions record the road not taken** — `decision · why · rejected alternative`.
- **An Invariants / gotchas section wherever there are footguns** (things that break if you edit them wrong).
- **A "where to put new code" table** — task → location → example. (The single highest-leverage section for a living codebase.)
- **One job per doc + cross-link** every sibling; **state the source of truth**.
- **Never fabricate** — unknowns become `<!-- TODO -->`, not confident fiction.
- Prefer one strong **mermaid** diagram over three weak ones; drop it if it doesn't clarify.

## When to ask the user

- **Split now or keep single-file?** — if it's borderline against the graduation rule.
- **Public/OSS vs internal** — only affects badges/license/contributing; if unclear, ask.
- **Anything you couldn't discover** — real ports, the run command, required env — ask rather than invent.
- Don't ask about section order or formatting — that's this standard.

## Files in this skill

- `reference/sections.md` — every section: purpose + pattern + a mini-example.
- `reference/doc-set.md` — README/REFERENCE/DESIGN(/DOCS/TODO) roles, the graduation rule, cross-linking.
- `assets/README.template.md` · `assets/REFERENCE.template.md` · `assets/DESIGN.template.md` — fill-in skeletons.
