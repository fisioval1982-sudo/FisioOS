---
id: CASE-XXXXXX
title: Caso clínico
type: Caso
status: Draft
version: 0.1
region:
side:
source: Caso clínico real anonimizado
source_type: clinical_case
source_file: CASE-XXXXXX_REPORT.pdf
source_url:
created_by: Pablo Salvador Coloma
reviewer:
review_date:
confidence:
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: []
---


# CASE-XXXXXX — Caso clínico

## Resumen clínico

Describir de forma anonimizada el contexto clínico relevante, mecanismo, evolución, síntomas y limitaciones funcionales.

## Exploración clínica

Registrar únicamente los datos disponibles y clínicamente relevantes.

## Hallazgos ecográficos

Describir los hallazgos principales y relacionarlos, cuando corresponda, con nodos `FIND-*` y `STR-*` existentes.

## Diagnóstico funcional

Registrar la hipótesis o diagnóstico funcional cuando proceda.

## Diagnóstico ecográfico

Registrar la interpretación ecográfica dentro del contexto clínico.

No convertir automáticamente un hallazgo aislado en diagnóstico.

## Imágenes ecográficas

Relacionar únicamente las imágenes pertenecientes a este caso:

- [[IMG-XXXXXX]]

Cada imagen tendrá su propia ficha `IMG-*` y su archivo original correspondiente almacenado en Google Drive.

## Informe original

Archivo:

`CASE-XXXXXX_REPORT.pdf`

El archivo original se conserva en Google Drive conforme a `ADR-008` y `ADR-013`.

## Correlación clínico-ecográfica

Relacionar los hallazgos de imagen con la exploración clínica sin asumir causalidad cuando no pueda establecerse.

## Tratamiento propuesto

Registrar únicamente cuando forme parte del caso documentado.

## Entidades relacionadas

Añadir únicamente relaciones reales y justificadas con:

- `STR-*`
- `FIND-*`
- `PAT-*`
- `TEST-*`
- `TRT-*`
- `EX-*`
- `IMG-*`

## Procedencia

La procedencia documental se registra mediante los campos `source_*` del frontmatter conforme a `PROVENANCE-STANDARD`.

## Validación

Registrar revisión clínica, coherencia entre informe e imágenes y cualquier limitación relevante.

## Estado

Draft
