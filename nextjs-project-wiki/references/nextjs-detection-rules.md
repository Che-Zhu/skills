# Next.js Detection Rules

Use this file before planning the wiki so the generated pages reflect the repository's actual Next.js shape.

## Confirm it is a Next.js repository

Look for strong signals such as:

- `next` dependency in `package.json`
- `next.config.*`
- `app/` and/or `pages/`
- `public/`
- Next.js scripts such as `next dev`, `next build`, or `next start`

If those signals are missing or contradictory, do not use this skill.

## Detect routing mode

Classify the repository as:

- `app` when it primarily uses `app/`
- `pages` when it primarily uses `pages/`
- `hybrid` when both are materially active

Do not classify the repository as `hybrid` just because `pages/api/` exists alongside an App Router UI. Use `hybrid` when both page-rendering systems materially shape the application.

Inspect:

- `app/**/page.*`
- `app/**/layout.*`
- `app/**/route.*`
- `pages/**/*.{js,jsx,ts,tsx}`
- `pages/api/**/*`
- `middleware.*`

## Detect rendering and mutation patterns

Look for:

- Server Components versus Client Components through `"use client"`
- server actions
- `fetch` cache usage and `revalidate`
- data loaders in server code
- client stores, contexts, or query libraries
- form handlers and mutation hooks

## Detect auth and state

Look for:

- auth libraries such as NextAuth, Auth.js, Clerk, Lucia, Supabase Auth, custom session logic
- cookie access
- middleware-based gating
- server-side authorization helpers
- client-side stores and context providers

## Detect API surface

Look for:

- `app/api/**/route.*`
- `pages/api/**/*`
- request validation libraries
- server services called from route handlers
- internal fetch callers across components, hooks, and server modules

## Detect config and environment

Inspect:

- `next.config.*`
- `.env.example`, `.env.local.example`, or other env templates
- deployment configs when present
- integration setup files

Use only what the repository can actually support with evidence.
