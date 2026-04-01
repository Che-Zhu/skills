---
name: nextjs-project-wiki
description: Generate and refresh a repository-local wiki for a single-repo Next.js project under docs/wiki/. Use when Codex needs to create, rebuild, or update an English code-driven project wiki with architecture, routing, business-domain pages, and API endpoint documentation split into public and internal interfaces.
---

# Next.js Project Wiki

Use this skill to create or refresh a machine-managed repo wiki for a single-repo Next.js codebase.

Prefer this skill when the user asks to:

- generate a project wiki or repo wiki for a Next.js repository
- rebuild or refresh `docs/wiki/` after code changes
- document the repository's architecture, routes, rendering model, or API endpoints
- turn a Next.js codebase into a shared knowledge base for developers or agents

Do not use this skill for:

- monorepos
- non-Next.js repositories
- one-off `README.md`, whitepaper, or PRD work
- standalone OpenAPI or Swagger generation without the broader repo wiki
- workflows that must preserve manual edits inside `docs/wiki/`

## Output contract

Output root: `docs/wiki/`

Treat `docs/wiki/` as fully managed by this skill. You may create, overwrite, reorganize, and delete files there to match the current codebase.

Default outputs:

- `docs/wiki/index.md`
- `docs/wiki/architecture.md`
- `docs/wiki/routing.md`
- `docs/wiki/rendering-and-data-flow.md`
- `docs/wiki/auth-and-state.md`
- `docs/wiki/config-and-env.md`
- `docs/wiki/api/index.md`
- `docs/wiki/api/<domain>.md`
- `docs/wiki/features/<domain>.md`
- `docs/wiki/_meta/manifest.json`

Optional outputs, only when the repository clearly warrants them:

- `docs/wiki/data-models.md`
- `docs/wiki/integrations.md`
- `docs/wiki/background-jobs.md`

All wiki content should be written in English unless the user explicitly asks for another language.

## Source of truth

The codebase is the primary source of truth.

Use existing docs, comments, or configuration to support or clarify what the code already shows, but do not let an older wiki override the current code.

When information is incomplete:

- prefer conservative wording over confident invention
- omit unsupported claims
- avoid pretending an architectural pattern exists unless the repository actually shows it

## Working order

1. Confirm the repository is a single-repo Next.js project and identify whether it uses the App Router, Pages Router, or both. Read `references/nextjs-detection-rules.md`.
2. Read the primary evidence: `package.json`, `next.config.*`, `app/`, `pages/`, `middleware.*`, route handlers, API routes, server modules, services, validators, env examples, and any relevant existing docs.
3. Build the wiki page plan. Read `references/wiki-structure.md` and `references/domain-page-rules.md`.
4. Rebuild `docs/wiki/` from the current repository state rather than trying to preserve prior generated prose.
5. Generate API pages using `references/api-rules.md`.
6. Write `docs/wiki/_meta/manifest.json` with source mappings and generation metadata.
7. Verify terminology consistency, cross-links, and page coverage.

## Page rules

- Write for fast onboarding of developers and agents.
- Prefer system behavior, business flow, and architecture boundaries over file-by-file paraphrase.
- Do not generate one page per component unless the repository itself is structured around that component as a major product surface.
- Prefer business-domain pages over directory-shaped pages.
- Include source paths when they materially help readers trace the claim back to code.
- Keep headings stable and predictable so future refreshes remain coherent.

For shared page-writing rules and section patterns, read `references/page-rules.md`.

## API rules

API documentation is a required part of this skill, not an optional appendix.

Every documented endpoint should be classified as either `public` or `internal`.

Use `references/api-rules.md` to:

- discover endpoints
- classify them
- group them into domain pages
- document request and response behavior

Do not stop at route files alone. Follow linked validators, services, and auth checks when needed to explain the actual interface.

## Domain rules

Feature pages must be organized by business domain rather than raw directory structure.

Examples of valid domains:

- auth
- billing
- dashboard
- editor
- notifications

If the repository does not have explicit business-domain names, infer the smallest stable set of domains from routes, navigation structure, API groupings, and service boundaries.

Use `references/domain-page-rules.md` for domain discovery and page structure.

## Refresh behavior

Default to a full rebuild of `docs/wiki/`.

That means:

- generated files may be rewritten wholesale
- stale pages may be deleted
- filenames may change if the current repository structure demands it

Prefer stable filenames when the same concept still exists, but correctness matters more than continuity.

## Manifest requirements

`docs/wiki/_meta/manifest.json` should make the generated wiki inspectable by future runs.

At minimum, record:

- generation timestamp
- repo-relative wiki root
- detected Next.js router mode
- generated pages
- major source paths per page

The manifest is a support artifact, not the source of truth.

## References

- Read `references/nextjs-detection-rules.md` before planning page coverage.
- Read `references/wiki-structure.md` when creating or reorganizing the wiki tree.
- Read `references/page-rules.md` for shared writing and linking rules.
- Read `references/api-rules.md` when generating or refreshing API documentation.
- Read `references/domain-page-rules.md` when deciding business-domain pages.
