# API Rules

Use this file when generating `docs/wiki/api/index.md` and `docs/wiki/api/<domain>.md`.

## Discovery scope

Inspect at minimum:

- `app/api/**/route.*`
- `pages/api/**/*`
- `middleware.*` when it affects API access or routing
- validators, schemas, service modules, and server helpers directly used by the endpoints

Do not stop after reading the route file if the real contract is defined in called validators or services.

## Classification

Every endpoint should be classified as either `public` or `internal`.

Use these rules:

- `public`: clearly intended for external or third-party consumption, public clients, or documented external use
- `internal`: primarily used by the app itself, internal dashboards, server-side orchestration, or private integrations

Do not introduce a third classification.

## Grouping

Group endpoint pages by business domain rather than only by path prefix when that improves readability.

Examples:

- auth
- billing
- workspace
- editor
- notifications

If path structure and business structure disagree, prefer the grouping that best reflects how the product is understood by developers.

## Minimum endpoint entry

Each endpoint entry should include:

- method and path
- classification: `public` or `internal`
- source location
- auth requirements
- route params, query params, request body, and relevant headers
- response shape
- main error semantics
- notable side effects
- main callers when discoverable

When request or response details are only partially discoverable, document the verified contract and name the module that owns the deeper validation or serialization. Do not invent a complete schema.

## Suggested endpoint template

```md
### `POST /api/<path>`

Type: `public`

Source:

- `<path>` - route entry
- `<path>` - validator or service

Auth:

- <auth requirement>

Request:

- Params: <summary>
- Query: <summary>
- Body: <summary>
- Headers: <summary>

Response:

- Success: <summary>
- Failure: <summary>

Side effects:

- <effect>

Main callers:

- `<path>` - <role>
```

## API index expectations

`docs/wiki/api/index.md` should summarize:

- the main API domains
- public interfaces
- internal interfaces
- notable auth or middleware gates

It should help the reader find domain pages quickly rather than restate every endpoint in full.
