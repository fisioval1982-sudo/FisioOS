# Vocabulario de estados

## Ciclo general de entidades

- `Candidate`
- `Draft`
- `Review`
- `Approved`
- `Deprecated`

## Estados para documentos no clínicos

- `Accepted`: utilizado en decisiones de arquitectura aceptadas.
- `Active`: utilizado en documentos de contexto y registros de biblioteca en uso.
- `Official`: utilizado para una plantilla designada como oficial.

El significado y alcance de los estados se describen en [[STATUS-LIFECYCLE]].

Los estados de documentos no clínicos no equivalen automáticamente a `Approved` ni certifican validación clínica.

La incorporación de estos valores documenta usos existentes. No implica cambiar automáticamente los estados de documentos ya registrados.