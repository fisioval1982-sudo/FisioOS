---
id: LIBRARY-SYSTEM
title: Library System v1
status: Approved
version: 1.1
---

# Library System

Define la gestión de bibliotecas reutilizables de FisioOS.

## Bibliotecas oficiales

- anatomy
- ultrasound
- exercises
- illustrations
- icons
- html-components
- evidence-figures

## Separación entre conocimiento y archivos

Las bibliotecas contienen metadatos, prompts, relaciones, estados y documentación.

Los archivos físicos viven en `/assets`.

## Estructura de una biblioteca

Cada biblioteca puede contener:

- `README.md`
- una ficha `LIBRARY-XXXXXX.md`
- `INDEX.md`
- `assets/`
- `prompts/`
- documentación específica

## Activos maestros

Un activo maestro es una referencia geométrica o visual estable utilizada para generar activos derivados.

Debe disponer de:

- identificador único;
- ficha Markdown;
- archivo maestro;
- prompt maestro cuando proceda;
- control de versión;
- validación clínica;
- validación visual;
- licencia y procedencia;
- relaciones con activos derivados.

## Regla de inmutabilidad

Un archivo aprobado no se sobrescribe con cambios anatómicos o visuales sustanciales.

Todo cambio sustancial genera una nueva versión.

## Rutas oficiales

- Metadatos: `/library/<library>/assets/`
- Prompts: `/library/<library>/prompts/`
- Archivos físicos: `/assets/<library>/`
