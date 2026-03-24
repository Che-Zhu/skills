# Whitepaper Template

Use this when the repository needs a long-lived product-definition document rather than a feature PRD.

Adapt the sections to the product, but keep the semantic separation intact.

```md
# <Product Name> Whitepaper

> Status: Draft
> Purpose: Internal product-definition document for long-lived boundaries and phase direction.

## 1. Why <Product Name>

- Why this product should exist
- Which user problem or operational problem it is trying to solve
- Which existing category descriptions are insufficient

## 2. Product Definition

- What the product is
- What the product is not
- What outcome the product optimizes for
- What should count as success beyond "code was generated"

## 3. Core Abstractions

Define the product's primary nouns.

For each abstraction:

- what it is
- why it matters
- what boundary it protects

## 4. Runtime or Execution Model

- How the system runs or reconciles work
- Which implementation choices are default versus product-defining
- Which infrastructure assumptions must stay replaceable

## 5. Product Boundaries

- What remains in-product
- What is delegated to providers or external systems
- What the product must not collapse into

## 6. Phase 1

### Goals

- <goal>
- <goal>

### Non-Goals

- <non-goal>
- <non-goal>

### Success Criteria

- <criterion>
- <criterion>

## 7. Closing Note

Restate the durable product thesis in a few lines.
```

## Writing guidance

- Use this document to define the product's enduring semantics.
- Do not use it to define one narrow workflow.
- Keep infrastructure and provider choices framed as implementation, unless they are truly the product.
- If the repository already has feature PRDs, the whitepaper should sit above them and define the stable frame they inherit.
