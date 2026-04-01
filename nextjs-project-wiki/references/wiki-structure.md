# Wiki Structure

Use this file when planning or reorganizing `docs/wiki/`.

The wiki should explain how the project works, not merely restate the file tree.

## Required pages

### `docs/wiki/index.md`

Purpose:

- define what the product or application is
- orient the reader to the major wiki sections
- summarize the main runtime surfaces: UI, API, auth, data, integrations

Suggested sections:

- Project Summary
- Current Routing Mode
- Main Business Domains
- Main Runtime Surfaces
- Wiki Map

### `docs/wiki/architecture.md`

Purpose:

- describe the repository's major layers and boundaries
- explain how requests move through the system
- identify the main modules that hold business logic

Suggested sections:

- Repository Shape
- Runtime Boundaries
- UI Layer
- Server Layer
- Shared Libraries
- External Dependencies

### `docs/wiki/routing.md`

Purpose:

- explain route structure and navigation surfaces
- show how App Router and Pages Router are used
- document middleware and route-level constraints

Suggested sections:

- Routing Overview
- App Routes
- Page Routes
- Dynamic Segments
- Middleware and Rewrites
- Navigation by Domain

### `docs/wiki/rendering-and-data-flow.md`

Purpose:

- explain Server Components versus Client Components
- document data fetching patterns, cache behavior, and mutations
- show how state moves between UI and server

Suggested sections:

- Rendering Model
- Data Fetching
- Cache and Revalidation
- Mutations and Server Actions
- Client State

### `docs/wiki/auth-and-state.md`

Purpose:

- explain authentication, authorization, session handling, and shared state
- document state containers that materially shape user behavior

Suggested sections:

- Auth Providers
- Session and Cookies
- Authorization Checks
- Shared Client State
- Form and Mutation State

### `docs/wiki/config-and-env.md`

Purpose:

- explain runtime configuration and deployment-relevant assumptions
- identify key environment variables and what they influence

Suggested sections:

- Configuration Files
- Environment Variables
- Build-Time Assumptions
- Runtime Integrations

### `docs/wiki/api/index.md`

Purpose:

- summarize the API surface
- list domain pages under `docs/wiki/api/`
- call out public versus internal interface counts or categories

Suggested sections:

- API Overview
- Public Interfaces
- Internal Interfaces
- Domain Index

### `docs/wiki/api/<domain>.md`

Purpose:

- document the endpoints that belong to one business domain
- connect route files to validators, services, and callers

Suggested sections:

- Domain Summary
- Public Endpoints
- Internal Endpoints
- Shared Dependencies
- Main Callers

### `docs/wiki/features/<domain>.md`

Purpose:

- explain one business domain end to end
- connect pages, state, APIs, and services into one reader-friendly view

Suggested sections:

- Domain Purpose
- User-Facing Surfaces
- Main Flows
- Dependencies
- Related APIs
- Open Constraints or Notable Risks

## Optional pages

Generate only when the repository clearly contains the relevant concept:

- `docs/wiki/data-models.md`
- `docs/wiki/integrations.md`
- `docs/wiki/background-jobs.md`

## Manifest shape

`docs/wiki/_meta/manifest.json` should be simple and machine-readable.

Suggested shape:

```json
{
  "generated_at": "<ISO timestamp>",
  "wiki_root": "docs/wiki",
  "router_mode": "app|pages|hybrid",
  "pages": [
    {
      "path": "docs/wiki/routing.md",
      "sources": ["app", "pages", "middleware.ts"]
    }
  ]
}
```

Keep the manifest compact. Its job is traceability, not prose.
