---
id: ONTO-STATUS-LIFECYCLE
title: Ciclo de vida de entidades
type: ontology-standard
status: Review
version: 1.1
---

# STATUS-LIFECYCLE

## Ciclo de entidades

El ciclo general de las entidades de conocimiento es:

```text
Candidate → Draft → Review → Approved → Deprecated
```

- **Candidate:** entidad importada o detectada sin revisión.
- **Draft:** entidad en construcción.
- **Review:** contenido preparado y pendiente de validación.
- **Approved:** contenido validado e incorporado.
- **Deprecated:** entidad que no debe utilizarse en nuevos contenidos.

En el contenido clínico, `Approved` requiere revisión humana. `Review` no equivale a validación clínica final.

## Estados de documentos no clínicos

Además del ciclo general, algunos tipos de documentos utilizan los siguientes estados:

- **Accepted:** decisión de arquitectura aceptada, utilizada en ADR.
- **Active:** documento de contexto o registro de biblioteca en uso.
- **Official:** plantilla designada como oficial.

Estos estados describen la situación del documento en su propio contexto. No equivalen automáticamente a `Approved` ni certifican validación clínica.

Los ADR que ya utilizan `Approved` conservan ese estado. La existencia de `Accepted` no implica convertir automáticamente los ADR de un estado a otro.

## Reglas

- El significado de `status` se interpreta según el tipo de entidad o documento.
- El contenido clínico requiere revisor humano para su aprobación.
- Las correcciones mayores incrementan la versión.
- Una entidad deprecada no se elimina si tiene enlaces.
- Las plantillas de metadatos pueden incluir campos `status:` vacíos como ejemplos; no son estados del documento que las contiene.
- Antes de introducir otro valor, documentar su significado y alcance.

## Estado

Review.

Esta versión documenta los estados no clínicos observados en el repositorio. Pendiente de revisión junto con `METADATA-STANDARD.md` y el vocabulario de estados para asegurar su coherencia.