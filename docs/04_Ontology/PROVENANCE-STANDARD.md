---
id: ONTO-PROVENANCE-STANDARD
title: Estándar de procedencia
type: ontology-standard
status: Approved
version: 1.0
---

# PROVENANCE-STANDARD

Toda entidad relevante debe responder de dónde procede, quién la creó, quién la revisó, cuándo se creó, cuándo se actualizó y qué fuente la respalda.

## Campos

```yaml
source:
source_type:
source_file:
source_url:
created_by:
reviewer:
review_date:
confidence:
```

## Tipos de afirmación

- verified_fact
- source_claim
- clinical_interpretation
- system_inference
- pending_verification

Una inferencia nunca se presentará como hecho verificado.
