---
id: INFOGRAPHIC-RENDER-GATE
title: Infographic Render Gate
type: validation_policy
status: Draft
version: 0.1
product: PRODUCT-INFOGRAPHIC-ENGINE
---

# Infographic Render Gate

The render gate is the final pre-render checkpoint.

## Render is allowed only if

- schema validation passes;
- unresolved required decisions equal zero;
- all required assets are approved;
- no blocking validation errors exist.

## Render must stop if

- a required decision is unresolved;
- an asset is missing or pending;
- a component type is unknown;
- a layout family is unknown;
- a required field is missing;
- the specification contains forbidden freeform render instructions.

## Principle

A failed render gate is not a prompt to improvise.

It is a request to resolve the blocking condition.
