---
id: ANATOMY-COMMON-AI-FAILURES
title: Common AI Failures in Anatomy Assets
status: Approved
version: 1.0
---

# Common AI Failures

## Duplicación anatómica

Ejemplos:

- dos cavidades glenoideas;
- dos acromiones;
- dos coracoides;
- extremos duplicados.

Prevención: declarar cantidades exactas y añadir validación final.

## Lateridad incorrecta

Prevención: declarar hueso derecho o izquierdo y posición en la imagen de los extremos medial y lateral.

## Vista oblicua

Prevención: exigir proyección ortográfica, cámara perpendicular, sin perspectiva, sin tilt y sin rotación.

## Mezcla de superficies

Ejemplo: espina escapular visible en una vista anterior estricta.

Prevención: declarar qué superficie domina y qué hitos deben permanecer ocultos.

## Morfología cilíndrica

Frecuente en clavícula.

Prevención: describir cambios de sección, estrechamiento, torsión y aplanamiento lateral.

## Fondos y halos

Prevención: fondo blanco uniforme durante generación y posterior exportación PNG RGBA sin halo.

## Geometría inconsistente entre vistas

Prevención: utilizar Geometry Lock y declarar que solo cambia el punto de vista.
