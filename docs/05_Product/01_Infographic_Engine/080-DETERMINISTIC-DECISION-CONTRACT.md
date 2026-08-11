---
id: INFOGRAPHIC-DETERMINISTIC-DECISION-CONTRACT
title: Deterministic Decision Contract
type: governance_standard
status: Draft
version: 1.0
product: PRODUCT-INFOGRAPHIC-ENGINE
---

# Deterministic Decision Contract

## Purpose

Define exactly which decisions a GPT may make, which decisions require explicit approval, and which decisions are forbidden.

## Principle

The GPT is an analyst and specification author.

It is not the final designer and it is not the canonical renderer.

## Decision classes

### Class A — Fixed

The GPT must not change these values.

Examples:

- approved anatomy asset IDs;
- laterality;
- geometry lock;
- brand tokens marked as locked;
- component behavior;
- renderer behavior;
- approved copy that is marked immutable.

### Class B — Controlled choice

The GPT may choose only from an explicit enumeration.

Examples:

- approved component type;
- approved semantic callout type;
- approved alignment mode;
- approved canvas format;
- approved fit mode.

### Class C — Bounded numeric choice

The GPT may provide a numeric value only inside a declared range or discrete scale.

Examples:

- column span;
- section order;
- spacing token index;
- maximum text length;
- image crop percentage where explicitly permitted.

### Class D — Human approval required

The GPT may propose a value, but the value is not canonical until approved.

Examples:

- new design token;
- new component;
- new visual language;
- new illustration style;
- new layout family;
- brand identity change.

### Class E — Forbidden

The GPT must not perform these actions.

Examples:

- arbitrary HTML;
- arbitrary CSS;
- mirroring anatomy;
- replacing a missing approved asset with a generated substitute;
- silently rewriting clinical claims;
- inventing unsupported content;
- creating new component types during rendering;
- bypassing schema validation.

## Missing-information policy

When required information is missing:

1. do not infer a final value;
2. mark the decision as unresolved;
3. return a structured validation error or approval request;
4. stop canonical rendering.

## No-improvisation rule

No output may become canonical if it contains:

- values outside the schema;
- values outside approved enums;
- freeform CSS;
- unknown components;
- unapproved assets;
- unresolved decisions.

## Canonical decision lifecycle

```text
Observation
↓
Candidate decision
↓
Classification
↓
Validation
↓
Approval if required
↓
Locked decision
↓
Rendering
```
