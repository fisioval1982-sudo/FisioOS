---
id: ONTO-METADATA-STANDARD
title: Estándar de metadatos
type: ontology-standard
status: Review
version: 1.1
---

# METADATA-STANDARD

## Obligatorios

```yaml
id:
title:
type:
status:
version:
created:
updated:
owner:
source:
```

## Recomendados

```yaml
aliases:
reviewer:
language:
region:
tags:
relationships:
evidence_level:
confidence:
```

## Reglas

- Fechas en formato `YYYY-MM-DD`.
- `status` se interpreta según el tipo de entidad o documento, conforme a [[STATUS-LIFECYCLE]].
- Las entidades de conocimiento utilizan el ciclo general: `Candidate`, `Draft`, `Review`, `Approved` y `Deprecated`.
- Los estados `Accepted`, `Active` y `Official` se documentan para los usos no clínicos descritos en [[STATUS-LIFECYCLE]].
- Los estados de documentos no clínicos no equivalen automáticamente a validación clínica.
- `source` identifica documento, URL, registro o lote.
- `reviewer` es obligatorio para aprobar contenido clínico.
- Un campo vacío dentro de un bloque de ejemplo YAML describe un metadato posible y no representa el estado del documento que contiene el ejemplo.

## Estado

Review.

Pendiente de revisar la coherencia con [[STATUS-LIFECYCLE]] y con `vocabularies/STATUSES.md`.