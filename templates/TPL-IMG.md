---
id: IMG-XXXXXX
title: Imagen ecográfica
type: Imagen clínica
status: Draft
version: 0.1
case:
region:
side:
structure:
view:
plane:
modality: Ultrasound
source:
source_type: clinical_image
source_file:
source_url:
created_by:
reviewer:
review_date:
confidence:
created: YYYY-MM-DD
updated: YYYY-MM-DD
---

# IMG-XXXXXX — Imagen ecográfica

## Caso relacionado

Añadir únicamente un caso clínico real existente:

- [[CASE-XXXXXX]]

## Estructura anatómica

Añadir únicamente nodos `STR-*` reales correspondientes a las estructuras identificables en la imagen.

## Hallazgos ecográficos

Añadir únicamente nodos `FIND-*` reales cuando el hallazgo esté suficientemente sustentado.

La ausencia de un nodo adecuado debe representarse dejando esta sección sin enlace, no mediante un identificador provisional.

## Características de adquisición

Registrar cuando se conozca:

- región anatómica;
- lado;
- estructura;
- plano;
- orientación;
- modo ecográfico;
- Doppler cuando proceda;
- posición del paciente;
- maniobra dinámica cuando proceda.

## Descripción de la imagen

Describir únicamente lo observable en la imagen.

Separar la descripción visual de la interpretación clínica.

## Interpretación clínica

Registrar la interpretación derivada de la imagen dentro del contexto del caso.

Una imagen aislada no debe convertirse automáticamente en diagnóstico.

## Procedencia

El archivo binario original se conserva externamente en Google Drive conforme a `ADR-008` y `ADR-013`.

`source_file` debe coincidir con el identificador y nombre del archivo original.

Ejemplo:

`IMG-000004.jpg`

`source_url` debe apuntar al archivo o a la carpeta del caso correspondiente en Google Drive.

## Relaciones

Añadir únicamente relaciones reales y justificadas con:

- `CASE-*`
- `STR-*`
- `FIND-*`
- `PAT-*` cuando la relación dependa del caso completo y no solo de la apariencia aislada de la imagen.

## Validación

Registrar:

- calidad técnica;
- identificabilidad anatómica;
- presencia de artefactos;
- suficiencia para análisis;
- revisión clínica cuando proceda.

## Estado

Draft