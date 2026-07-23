---
id: GENERATIVE-ASSET-STANDARD
title: Generative Asset Standard
status: Approved
version: 1.0
---

# Generative Asset Standard

## Objetivo

Regular los activos creados o modificados mediante modelos generativos.

## Requisitos

Todo activo generativo debe conservar:

- prompt maestro;
- versión del prompt;
- imagen fuente o referencia;
- método de generación;
- revisión anatómica;
- revisión visual;
- limitaciones conocidas;
- relación con el activo padre.

## Principio de geometría congelada

Cuando un activo se aprueba como `master_base`, su geometría no debe reinterpretarse en activos derivados.

Las nuevas estructuras deben añadirse mediante edición sobre el activo aprobado siempre que sea técnicamente posible.

## Prompt maestro

Debe contener:

- objetivo;
- orientación;
- estructuras obligatorias;
- exclusiones;
- errores prohibidos;
- estilo;
- color;
- fondo;
- composición;
- validación final.

## Derivación

Todo activo derivado debe declarar:

- `parent_asset`;
- cambios introducidos;
- elementos preservados;
- prompt o instrucción de edición;
- versión.

## Prohibiciones

- sobrescribir un master aprobado;
- eliminar el prompt original;
- cambiar lateridad sin crear un activo nuevo;
- mezclar vistas en un mismo identificador;
- presentar una ampliación reescalada como aumento real de detalle.
