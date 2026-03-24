---
name: project-foundation-docs
description: Create or refresh a repository's foundation documents: a product whitepaper under docs/, a root AGENTS.md, and a root README.md. Use when a project needs its product framing, agent workflow rules, and repo entrypoint established before feature PRDs or implementation.
---

# Project Foundation Docs

Use this skill to create or tighten the three repo-level baseline documents that define how a project thinks, how agents should work, and how a reader should enter the repo.

Prefer this skill when the user asks for any of these outcomes:

- create a project whitepaper
- create or rewrite the root `AGENTS.md`
- create or rewrite the root `README.md`
- establish the documentation baseline for a new project
- align those three files so they do not contradict each other

Do not use this skill for:

- feature PRDs under `docs/prd/`
- acceptance tests
- implementation planning for one feature
- marketing copy or launch copy

## Output contract

Default output paths:

- `docs/whitepaper.md`, or the repo's existing whitepaper path if one already exists
- `AGENTS.md` in the repository root
- `README.md` in the repository root

These files must keep different responsibilities:

- whitepaper: long-lived product definition, core abstractions, architecture boundaries, phase goals
- `AGENTS.md`: repository-local operating rules for agents
- `README.md`: short project entrypoint and document map

Avoid cross-file duplication.

- `README.md` should stay short
- `AGENTS.md` should define process, not restate the whole product thesis
- the whitepaper should define the product, not become a contribution guide

## Working order

1. Read existing `docs/whitepaper*`, root `AGENTS.md`, and root `README.md` if present.
2. Infer the repo's product intent, abstractions, maturity, and language from existing docs and code.
3. Write or refine the whitepaper first. Use `references/whitepaper-template.md` if the repo has no solid whitepaper yet.
4. Derive the agent operating model into root `AGENTS.md`. Use `references/agents-template.md`.
5. Compress the repo entrypoint into `README.md`. Use `references/readme-template.md`.
6. Check terminology consistency across all three files.

When only one of the three files exists, use it as the anchor and derive the other two from it.

## Minimum inputs to extract or infer

Before drafting, identify or infer:

- product name
- target user or operator
- job to be done
- product type: app, platform, workflow system, API, template system, internal tool, and so on
- source of truth for behavior: whitepaper, PRDs, tests, specs, code
- phase-one scope and non-goals
- the agent workflow expected in this repository
- the dominant language of the repository docs

If some of these are missing, make explicit assumptions instead of blocking on every detail.

## Whitepaper rules

The whitepaper should define durable product boundaries rather than a single feature.

Include the product's:

- reason for existing
- product definition
- core abstractions
- runtime or execution model if relevant
- product boundaries
- phase-one goals, non-goals, and success criteria

Keep the whitepaper product-defining, not task-defining.

- do not turn it into a feature PRD
- do not make one provider the product identity unless that is truly intended
- do not bury the main abstraction under implementation details

For a starting skeleton, read `references/whitepaper-template.md`.

## AGENTS.md rules

`AGENTS.md` should tell agents how to work in this repository.

It should usually define:

- repository intent
- required workflow
- document hierarchy and source of truth
- PRD rules
- test rules
- execution scope rules
- architecture constraints
- communication style for agents

If the repo already follows a workflow like `whitepaper -> PRD -> acceptance tests -> implementation`, preserve that order and make it explicit.

For a starting skeleton, read `references/agents-template.md`.

## README rules

`README.md` should let a reader understand the repo in under a minute.

Prefer:

- one short project definition
- one short explanation of the repo's current state
- links to the key documents
- local development commands only if the repo is already runnable and the commands matter

Do not turn the README into a second whitepaper.

For a starting skeleton, read `references/readme-template.md`.

## Editing guidance

- Prefer refining existing files over replacing their voice unless the current file is clearly a placeholder.
- Preserve established filenames and document language when reasonable.
- If feature PRDs already exist, point to them from `README.md` or `AGENTS.md` without redefining them.
- If the repository already has strict product semantics, make the whitepaper the highest-level source and align the other two files underneath it.
- State assumptions when the repo's product boundaries are still partly invented.

## References

- Read `references/whitepaper-template.md` when creating or heavily rewriting a whitepaper.
- Read `references/agents-template.md` when creating or heavily rewriting root `AGENTS.md`.
- Read `references/readme-template.md` when creating or heavily rewriting `README.md`.
