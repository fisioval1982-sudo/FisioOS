---
id: MODULE-006
title: Exercise Engine de FisioOS
type: module
status: Approved
version: 1.0
created: 2026-07-18
owner: Pablo Salvador Coloma
---

# MODULE-006 — Exercise Engine de FisioOS

## Objetivo

Definir el estándar clínico para crear, validar, relacionar y reutilizar ejercicios terapéuticos dentro de FisioOS.

## Fuente única

- Entidades de ejercicio: `knowledge/exercise/`
- Arquitectura, normas e índices: `docs/`
- Plantillas: `templates/`

## Flujo

1. Ejercicio candidato.
2. Revisión clínica.
3. Normalización.
4. Estado `Review`.
5. Validación.
6. Estado `Approved`.
7. Enlace con patologías, protocolos, casos, publicaciones y activos visuales.

## Componentes

- [[EX-INDEX-001]]
- [[EX-CATEGORIES-001]]
- [[EX-EQUIPMENT-001]]
- [[EX-PHASES-001]]
- [[EX-QUALITY-001]]
- [[ADR-010]]
