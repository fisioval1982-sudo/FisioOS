---
id: INFOGRAPHIC-RENDER-PLAN-CONTRACT
title: Render Plan Contract
type: data_contract
status: Draft
version: 0.1
product: PRODUCT-INFOGRAPHIC-ENGINE
---

# Render Plan Contract

## Purpose

Define the machine-readable output produced by the renderer before any format-specific rendering.

## Principle

The render plan is fully resolved.

It must not contain:
- unresolved design decisions;
- prose instructions;
- freeform CSS;
- unknown components;
- unknown assets;
- implicit browser behavior.

## Required domains

A render plan must contain:
- renderer version;
- infographic ID;
- canvas metrics;
- resolved regions;
- resolved components;
- resolved assets;
- resolved token references;
- deterministic ordering;
- validation metadata.

## Why this layer exists

The render plan prevents an output adapter from becoming a second designer.

HTML, SVG, PNG and PDF must all originate from the same resolved render plan.
