# Domain Page Rules

Use this file when deciding which `docs/wiki/features/<domain>.md` pages to create and how to write them.

## Domain discovery

Prefer business domains over directory names.

Look for domain signals in:

- navigation labels
- route groups
- top-level product areas
- API groupings
- service boundaries
- repeated naming in components, hooks, stores, and server modules

Good domains usually reflect a recognizable product surface such as:

- auth
- billing
- dashboard
- editor
- settings
- notifications

Avoid domains that are too technical, such as:

- components
- hooks
- utils
- server

Use technical slices only when the product itself is centered on that technical surface.

## Domain page goals

A domain page should tell the reader:

- what user problem this domain handles
- which routes or screens belong to it
- which APIs support it
- which services, stores, or integrations are central to it
- what the main success and failure paths look like

## Suggested domain page structure

```md
# <Domain Name>

## Purpose

<What this domain is responsible for.>

## User-Facing Surfaces

- `<route or page>` - <role>
- `<route or page>` - <role>

## Main Flows

- <core flow>
- <core flow>

## Supporting APIs

- `GET /api/<path>` - <role>
- `POST /api/<path>` - <role>

## Key Modules

- `<path>` - <role>
- `<path>` - <role>

## Constraints

- <important invariant or limitation>
```

## Split and merge guidance

- Split domains when one page becomes too broad to explain coherently.
- Merge domains when two areas share the same routes, APIs, and business purpose.
- Prefer a small number of durable domain pages over many thin pages.
