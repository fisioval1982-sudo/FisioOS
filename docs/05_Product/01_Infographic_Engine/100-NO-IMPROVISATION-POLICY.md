---
id: INFOGRAPHIC-NO-IMPROVISATION-POLICY
title: No Improvisation Policy
type: governance_policy
status: Draft
version: 1.0
product: PRODUCT-INFOGRAPHIC-ENGINE
---

# No Improvisation Policy

## Rule

When the specification does not define a decision and no approved default exists, the system must stop.

It must not improvise.

## Forbidden fallbacks

The system must not:

- choose a visually pleasing alternative;
- use a similar color;
- select a nearby font;
- insert a generic icon;
- generate a replacement illustration;
- resize a component beyond allowed constraints;
- reorder content to make it fit;
- shorten text without explicit permission;
- invent spacing;
- create inline styles;
- use browser defaults as canonical design decisions.

## Explicit defaults

Defaults are allowed only when they are:

1. documented;
2. versioned;
3. approved;
4. represented in machine-readable configuration.

## Conflict policy

If two approved rules conflict:

- do not choose between them automatically;
- emit a conflict;
- identify both rules;
- require resolution before rendering.

## Overflow policy

If content does not fit:

- do not shrink below the approved minimum;
- do not hide content;
- do not truncate silently;
- return an overflow error.

## Asset policy

If an approved asset is missing:

- do not generate a substitute;
- do not use a placeholder as final output;
- return a missing-asset error.
