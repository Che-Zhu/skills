---
name: prd-writer
description: Write and refine implementation-facing product requirement documents (PRDs) for concrete features and workflows. Use when Codex needs to turn product discussions into clear PRDs that define user intent, scope, success semantics, failure semantics, state requirements, retry behavior, persistence expectations, UI implications, and non-goals.
---

# PRD Writer

Write PRDs that are implementation-facing rather than strategy-heavy.

Default to documents that help engineers and product owners align on system behavior for a specific workflow or feature.

## Write the right kind of PRD

Prefer this skill for:

- feature workflows such as import project, deploy project, install skill, or database creation
- stateful behaviors that need explicit success and failure semantics
- discussions where the code is blocked by unclear product meaning
- refining existing drafts into sharper implementation requirements

Do not use this skill for:

- long-range roadmap planning
- vision documents
- architecture strategy documents that are not feature-specific
- changelogs or release notes

## Drive toward operational clarity

When drafting or reviewing a PRD, make sure the document answers these questions:

1. What is the user actually asking the system to achieve?
2. What is in scope for this document, and what is explicitly out of scope?
3. What counts as success?
4. What counts as failure?
5. Which failures should preserve previously created state instead of rolling it back?
6. Which statuses or records must be persisted?
7. What should the user see in the UI for each important outcome?
8. What retries, follow-up actions, or operator interventions are allowed?

If the conversation does not answer these questions, ask focused follow-up questions before writing the PRD.

## Prefer this PRD structure

Use a structure close to this unless there is a strong reason to deviate:

1. Goal
2. Scope
3. User Intent
4. Success Semantics
5. Failure Semantics
6. Status Requirements
7. UI Requirements
8. Retry Behavior
9. Persistence Requirements
10. Metadata or External Association Requirements
11. Non-Goals
12. Implementation Notes

For a reusable starting skeleton, read `references/prd-template.md`.

## Write with product semantics, not implementation leakage

The PRD should define product behavior first.

Good examples:

- "A project is considered successfully created when its sandbox reaches a runnable state."
- "Repository clone failure does not roll back the project."
- "The UI should show RUNNING + IMPORT FAILED."

Weaker examples:

- "Call function X and then update table Y."
- "The backend should throw an error from helper Z."

Implementation notes are allowed, but they should come after the product behavior is clear.

## Treat state as a first-class requirement

For any workflow that spans time, external systems, or retries, explicitly define:

- which state belongs to the main resource
- which state belongs to the sub-transaction or task
- whether a partially successful result is valid
- whether failed sub-steps should be retryable
- whether metadata should be retained after failure

If the feature depends on asynchronous control-plane behavior, make that explicit in the PRD.

## Distinguish layered success

Many workflows have more than one level of success. For example:

- project creation success
- import transaction success
- deployment success
- task success

Do not collapse these into one generic "success" if the product meaning differs.

If a system can produce a valid resource while a related sub-transaction fails, state that clearly.

## Make non-goals explicit

Always include a non-goals section.

Use it to stop the PRD from expanding into adjacent work such as:

- future UX improvements
- later automation phases
- unrelated architecture changes
- optional retry tooling

This keeps the document actionable.

## Review checklist

Before finalizing, check that the PRD:

- names the user intent plainly
- separates success semantics from failure semantics
- states whether partial success is acceptable
- defines the persisted state needed for correctness
- states what the UI should show
- defines retry behavior
- preserves important metadata rules
- includes non-goals

## Output style

Prefer concise, direct prose.

Use short sections with concrete statements. Avoid bloated templates, generic PM language, and strategy filler.
