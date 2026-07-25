---
id: ANATOMY-GEOMETRY-LOCK
title: Anatomy Geometry Lock
status: Approved
version: 1.1
---

# Anatomy Geometry Lock

## Principio

Cuando una estructura anatómica alcanza el estado `master_base`, su geometría queda bloqueada.

## Cambios permitidos

- cambio de cámara;
- cambio de vista;
- exportación;
- resolución;
- fondo;
- conversión de formato;
- corrección técnica que no altere la anatomía.

## Cambios prohibidos

- longitud;
- proporciones;
- curvaturas;
- torsión;
- lateridad;
- hitos anatómicos;
- relación entre procesos;
- número de estructuras;
- reinterpretación morfológica.

## Derivaciones

Todo activo derivado debe declarar:

- activo padre;
- vista;
- cambios añadidos;
- elementos preservados;
- versión;
- prompt o instrucción de edición.

## Familia bloqueada — escápula derecha

La colección [[ASSET-000005]] queda bloqueada como una única familia formada por:

- [[ASSET-000001]] — posterior;
- [[ASSET-000002]] — anterior;
- [[ASSET-000003]] — lateral;
- [[ASSET-000004]] — superior.

El bloqueo se aplica conjuntamente a las cuatro vistas. Ninguna vista puede regenerarse, redibujarse, reflejarse o corregirse anatómicamente de forma aislada. Toda sustitución futura requiere conservar la coherencia multivista y repetir la revisión clínica, visual y técnica.
