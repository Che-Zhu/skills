# PRD Template

Use this template as a starting point for implementation-facing PRDs.

Adapt section names when needed, but keep the semantic structure intact.

```md
# <Feature or Workflow Name>

Status: Draft

## Goal

Define the product behavior and control-plane semantics for <feature/workflow>.

## Scope

This document covers:

- <in-scope item>
- <in-scope item>
- <in-scope item>

This document does not define:

- <out-of-scope item>
- <out-of-scope item>

## User Intent

When the user asks to <do something>, the system receives these requested outcomes:

1. <requested outcome>
2. <requested outcome>

## Success Semantics

### <primary success concept>

<Define what counts as success for the main resource or workflow.>

### <secondary success concept if needed>

<Define what counts as success for the sub-transaction, task, or follow-up action.>

## Failure Semantics

### <primary failure concept>

<Define what counts as failure and whether it invalidates the whole workflow.>

### <partial failure concept if needed>

<Define which failures preserve already-created state instead of rolling it back.>

## Status Requirements

The system should represent:

1. <main resource status>
2. <sub-transaction or task status>

For the current product behavior:

- <status combination>
- <status combination>

## UI Requirements

For the current stage of the product:

- <UI expectation>
- <UI expectation>
- <UI expectation>

## Retry Behavior

<Define automatic retries, manual retries, or no retries.>

Requirements:

- <retry rule>
- <retry rule>
- <retry rule>

## Persistence Requirements

The system must persist enough state to represent:

- <state requirement>
- <state requirement>
- <state requirement>

## Metadata or External Association Requirements

<Define whether external metadata or associations should be retained after failure.>

## Non-Goals

This PRD does not define:

- <non-goal>
- <non-goal>
- <non-goal>

## Implementation Notes

Current implementation should preserve this product contract:

- <implementation-facing constraint>
- <implementation-facing constraint>
```

## Writing guidance

- Prefer product semantics before implementation details.
- Distinguish layered success when the main resource and a sub-transaction can succeed independently.
- Make partial success explicit rather than implicit.
- Keep non-goals sharp so the PRD stays actionable.
