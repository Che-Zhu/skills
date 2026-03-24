# AGENTS Template

Use this when the repository needs a root `AGENTS.md` that tells agents how to work.

This file should define process and decision hierarchy, not re-explain the full product thesis.

```md
# <Project Name> Agent Guide

This file defines how AI agents should work in this repository.

## Repository Intent

- What this repository exists to produce
- Which artifacts or documents are the source of truth

## Core Principle

- The single sentence that explains how work should happen in this repo

## Required Workflow

1. Read the highest-level product docs first.
2. Refine or write the relevant feature PRD.
3. Define or update acceptance tests.
4. Implement only the scoped behavior.
5. Verify against the tests.
6. Stop when the scoped behavior is complete.

## Document Hierarchy

1. <highest-level product document>
2. <feature PRDs>
3. <acceptance tests>
4. <implementation files>

Explain how conflicts should be resolved.

## PRD Rules

- Which sections PRDs must define
- What makes a PRD incomplete

## Test Rules

- Which behavior tests must cover
- What counts as a good acceptance test

## AI Execution Rules

- scope control rules
- no ad hoc feature expansion
- no silent semantic changes

## File Organization Rules

- naming and responsibility boundaries

## Architecture Constraints

- durable product or system boundaries that implementations must not violate

## MVP Bias

- what "smallest complete loop" means for this repo

## Communication Style

- what agents should report before and after changes
```

## Writing guidance

- Keep this file operational.
- Prefer imperative rules over vague suggestions.
- Make the repository's source-of-truth order explicit.
- If the project depends on whitepapers, PRDs, and acceptance tests, encode that workflow here.
