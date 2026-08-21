---
id: INDEX-ELBOW
title: Índice dinámico — Codo
Relaciones: REG-000005 — Miembro superior STR-000230 — Codo
type: Index
status: Draft
version: 0.1
region: REG-000005
created: 2026-08-21
updated: 2026-08-21
---

# Índice dinámico — Codo

## Relaciones

- [[REG-000005]] — Miembro superior
- [[STR-000230]] — Codo

## Anatomía

```dataview
TABLE id, title, status
FROM "knowledge/anatomy/upper_limb/elbow"
SORT id ASC
```

## Tests clínicos

```dataview
TABLE id, title, clinical_domain, status
FROM "knowledge/tests/elbow"
SORT id ASC
```

## Patologías

```dataview
TABLE id, title, status
FROM "knowledge/pathology/elbow"
SORT id ASC
```

## Hallazgos ecográficos

```dataview
TABLE id, title, status
FROM "knowledge/ultrasound/findings"
WHERE contains(file.outlinks, [[STR-000233]]) OR contains(file.outlinks, [[PAT-000006]])
SORT id ASC
```