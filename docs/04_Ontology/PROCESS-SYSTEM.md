---
id: PROCESS-SYSTEM
title: Sistema de procesos de FisioOS
type: operational-standard
status: Approved
version: 1.0
---

# PROCESS-SYSTEM

Un `PROCESS` describe una secuencia completa, humana, asistida o automatizada.

Un `WORKFLOW` describe una implementación operativa concreta dentro de un proceso.

## Metadatos

```yaml
id:
title:
purpose:
inputs:
outputs:
actors:
steps:
controls:
capabilities:
workflows:
status:
version:
```

Ejemplo: `PROCESS-000001 — Gestión de un caso ecográfico` puede contener `WORKFLOW-000001 — PDF + imágenes → extracción → validación → Airtable → Obsidian`.
