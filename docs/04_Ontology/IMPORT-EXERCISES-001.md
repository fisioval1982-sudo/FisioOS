---
id: IMPORT-EXERCISES-001
title: Protocolo de importación de ejercicios externos
type: import-protocol
status: Approved
version: 1.0
---

# IMPORT-EXERCISES-001 — Importación de ejercicios externos

## exercises-dataset

Puede usarse para explorar nombres, músculos, material y preselección de ejercicios.

No puede usarse automáticamente para aprobar ejercicios, reutilizar imágenes sin licencia, aceptar dosificaciones como clínicas o asociar patologías sin revisión.

## KeraalDataset

Se utilizará para estudiar errores de ejecución, feedback correctivo y análisis de pose.

## Flujo

1. Importar metadatos.
2. Eliminar duplicados.
3. Filtrar ejercicios no clínicos.
4. Normalizar nombres.
5. Crear candidatos.
6. Revisar clínicamente.
7. Crear activos visuales propios.
8. Aprobar.
