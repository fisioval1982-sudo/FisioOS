---
id: INFOGRAPHIC-SPECIFICATION-CONTRACT
title: Infographic Specification Contract
type: technical_contract
status: Draft
version: 0.1
product: PRODUCT-INFOGRAPHIC-ENGINE
---

# Infographic Specification Contract

## Purpose

Define the mandatory machine-readable specification that must exist before any canonical infographic rendering.

The specification is the manufacturing plan for the infographic.

## Core rule

A GPT may propose the specification.

A renderer may render only a validated specification.

The renderer must not infer missing design decisions.

## Pipeline

```text
Clinical/content request
↓
Content extraction
↓
Infographic specification
↓
Schema validation
↓
Decision validation
↓
Asset validation
↓
Render gate
↓
Renderer
↓
Visual QA
```

## Required specification domains

Every specification must explicitly define:

- infographic identity and version;
- canvas format;
- content structure;
- layout family;
- layout regions;
- approved or pending assets;
- component instances;
- decision references;
- validation state.

## Separation of responsibilities

### GPT

Allowed to structure content, map content to approved component types, choose only from approved enumerations, identify unresolved decisions, and request approval.

Not allowed to write canonical HTML/CSS, create new component types during rendering, invent missing brand tokens, substitute missing assets, or bypass validation.

### Renderer

Allowed to consume a validated specification, resolve approved tokens and components, and render deterministic output.

Not allowed to redesign, reinterpret content hierarchy, or add visual elements not present in the specification.

## Render gate

Canonical rendering is allowed only when:

1. the specification validates against schema;
2. all required decisions are resolved;
3. all required assets are approved and available;
4. there are no blocking errors.

If any condition fails, `render_allowed` must be `false`.
