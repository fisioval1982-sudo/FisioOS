---
id: ONTO-MIGRATION-POLICY
title: Política de migraciones
type: ontology-standard
status: Approved
version: 1.0
---

# MIGRATION-POLICY

## Prioridad

1. Mantener ID.
2. Cambiar título o aliases.
3. Deprecar y redirigir.
4. Fusionar duplicados.
5. Migrar ID solo como último recurso.

## Toda migración debe incluir

- Motivo.
- Entidades afectadas.
- Mapa antiguo → nuevo.
- Riesgos.
- Copia de seguridad.
- Validación posterior.
- Changelog.

No se realizarán migraciones estructurales durante la carga de un lote clínico.
