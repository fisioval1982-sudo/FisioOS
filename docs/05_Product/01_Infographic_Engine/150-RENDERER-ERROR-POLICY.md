---
id: INFOGRAPHIC-RENDERER-ERROR-POLICY
title: Renderer Error Policy
type: validation_policy
status: Draft
version: 0.1
product: PRODUCT-INFOGRAPHIC-ENGINE
---

# Renderer Error Policy

## Blocking error classes

- `SPEC_INVALID`
- `RENDER_GATE_BLOCKED`
- `UNKNOWN_COMPONENT`
- `UNKNOWN_TOKEN`
- `UNKNOWN_LAYOUT`
- `ASSET_MISSING`
- `ASSET_NOT_APPROVED`
- `UNRESOLVED_DECISION`
- `CONTENT_REFERENCE_MISSING`
- `OUTPUT_ADAPTER_UNAVAILABLE`

## Required behavior

Every blocking error must:
1. stop canonical rendering;
2. identify the failing path or reference;
3. provide a deterministic error code;
4. avoid fallback rendering.

## Forbidden behavior

The renderer must not:
- replace a missing asset;
- guess a token;
- substitute a component;
- shrink or reorder content to force fit;
- generate CSS or HTML to repair a problem;
- silently continue after a blocking error.
