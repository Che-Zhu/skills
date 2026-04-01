# Page Rules

Use this file for shared writing rules across all wiki pages.

## Writing style

- Write in English.
- Prefer direct, concrete prose over marketing language.
- Optimize for fast comprehension by a new engineer or coding agent.
- Explain behavior and boundaries before implementation trivia.

## Evidence rules

- Base claims on code first.
- Use repository docs only as support, not as a replacement for code inspection.
- Do not invent background jobs, cache rules, auth semantics, or deployment behavior that the repository does not show.

## Page design rules

- Prefer concise sections with meaningful headings.
- Link related wiki pages when cross-navigation helps.
- Mention source paths when they add verification value.
- Avoid exhaustive file listings unless the page is specifically about repository structure.

## Shared section pattern

Use a structure close to this when it fits:

```md
# <Page Title>

## Overview

<What this surface is and why it matters.>

## How It Works

<Main runtime path or interaction model.>

## Key Modules

- `<path>` - <role>
- `<path>` - <role>

## Constraints

- <important limitation or invariant>
- <important limitation or invariant>
```

Adapt the sections when another structure better fits the material.

## What to avoid

- file-by-file narration with no higher-level synthesis
- one paragraph per component when components are not the primary abstraction
- inflated certainty when the code evidence is weak
- copying large amounts of existing README text into the wiki
