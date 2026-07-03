---
id: STRUCTURE-001
title: Arquitectura de carpetas FisioOS v1.0
version: 1.0
status: Approved
owner: Pablo Salvador Coloma
created: 2026-07-04
updated: 2026-07-04
related:
  - DOC-000
  - SPEC-000
  - SPEC-001
  - ONTO-000
tags:
  - structure
  - repository
  - architecture
---

# STRUCTURE-001 — Arquitectura de carpetas FisioOS v1.0

## Estado

Aprobado.

## Regla principal

La estructura instalada en Obsidian es la estructura oficial de FisioOS v1.0.

No se renombrarán carpetas existentes salvo ADR aprobado.

## Estructura oficial

```text
FisiOS_v1/

docs/
├── 00_Project/
├── 01_Vision/
├── 02_Constitution/
├── 03_Architecture/
├── 04_Ontology/
├── 05_Product/
├── 06_Research/
├── 07_Guides/
├── 08_ADR/
└── 09_Roadmap/

templates/

knowledge/
├── anatomy/
├── exercise/
├── findings/
├── glossary/
├── pathology/
├── regions/
├── relations/
├── tests/
├── treatment/
└── ultrasound/

corpus/
├── cases/
├── episodes/
├── exports/
└── reports/

library/
├── annotations/
├── images/
├── svg/
└── videos/

media/

research/
├── bibliography/
├── guidelines/
├── papers/
└── protocols/

software/
├── ai/
├── api/
├── backend/
├── database/
├── frontend/
└── scripts/
```

## Significado de las carpetas

### docs/

Documentación oficial, especificaciones, ADR, guías y roadmap.

### templates/

Plantillas reutilizables para documentos, entidades, casos, informes y especificaciones.

### knowledge/

Conocimiento reutilizable de FisioOS: anatomía, regiones, hallazgos, patologías, tests, tratamientos, ejercicio, ecografía, relaciones y glosario.

### corpus/

Casos reales anonimizados, episodios, informes y exportaciones estructuradas.

### library/

Biblioteca multimedia: imágenes, anotaciones, SVG y vídeos.

### research/

Bibliografía, artículos, guías, protocolos y material de investigación.

### software/

Código futuro: API, base de datos, backend, frontend, IA y scripts.

## Convención lingüística

Se conserva la nomenclatura instalada actualmente:

- `pathology`, no `pathologies`.
- `treatment`, no `treatments`.
- `exercise`, no `exercises`.
- `ultrasound`, no `imaging`.

La prioridad es estabilidad de enlaces y consistencia del repositorio.

## Regla de cambio

Cualquier cambio de estructura deberá registrarse mediante ADR.
