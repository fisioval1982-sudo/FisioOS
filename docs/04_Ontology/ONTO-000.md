---
id: ONTO-000
title: Especificación de la Ontología Clínica de FisioOS
version: 1.0
status: Draft
owner: Pablo Salvador Coloma
created: 2026-07-03
updated: 2026-07-03
related:
  - SPEC-000
  - SPEC-001
  - DOC-016
tags:
  - ontology
  - knowledge
  - architecture
---

# ONTO-000 — Especificación de la Ontología Clínica de FisioOS

## Estado del documento

- Código: ONTO-000
- Versión: 1.0
- Estado: Draft
- Nivel: Arquitectura

## 1. Objetivo

Este documento define las reglas de construcción de la Ontología Clínica de FisioOS.

La ontología constituye el vocabulario oficial del sistema y proporciona un lenguaje único para representar conocimiento fisioterapéutico.

Toda entidad clínica deberá existir previamente en esta ontología antes de poder utilizarse en:

- Informes ecográficos
- Casos clínicos
- Biblioteca ecográfica
- Publicaciones
- Investigación
- Inteligencia artificial
- API
- SaaS

## 2. Principios

1. Un único concepto por entidad.
2. Un único identificador permanente.
3. Un único nombre oficial.
4. Relaciones explícitas.
5. Reutilización.
6. Versionado.
7. Trazabilidad.
8. Evidencia documentada.
9. Explicabilidad.
10. Independencia tecnológica.

## 3. Tipos de entidades

| Código | Tipo |
|--------|------|
| STR | Anatomía |
| REG | Región anatómica |
| FIND | Hallazgo ecográfico |
| PAT | Patología |
| SYM | Síntoma |
| EXAM | Exploración |
| TEST | Test clínico |
| MOD | Modalidad ecográfica |
| TRT | Tratamiento |
| EX | Ejercicio |
| DOC | Documento |
| BIB | Bibliografía |

## 4. Sistema de identificadores

Formato:

```
PREFIJO-000001
```

Ejemplos:

```
STR-000001
PAT-000001
FIND-000001
TRT-000001
```

Los identificadores nunca cambian ni se reutilizan.

## 5. Relaciones permitidas

- pertenece_a
- es_un
- puede_presentar
- puede_mostrar
- puede_tratarse_con
- contraindicado_en
- se_explora_con
- se_localiza_en
- deriva_de
- requiere

## 6. Atributos obligatorios

- ID
- Nombre oficial
- Sinónimos
- Tipo
- Descripción
- Relaciones
- Bibliografía
- Nivel de evidencia
- Autor
- Estado
- Versión
- Fecha de creación
- Fecha de modificación

## 7. Estados

Draft → Review → Approved → Deprecated

## 8. Reglas

- Una estructura anatómica nunca será una patología.
- Un hallazgo nunca será un tratamiento.
- Una imagen nunca será un diagnóstico.
- Nunca existirán entidades duplicadas.

## 9. Jerarquía

Sistema musculoesquelético → Región → Estructura → Subestructura.

## 10. Relaciones anatómicas

Ejemplo:

Tendón rotuliano → se_inserta_en → Polo inferior de la rótula.

## 11. Relaciones clínicas

Ejemplo:

Tendón rotuliano → puede_presentar → Tendinopatía.

## 12. Relaciones ecográficas

Ejemplo:

Tendinopatía → puede_mostrar → Hipoecogenicidad.

## 13. Relaciones terapéuticas

Ejemplo:

Tendinopatía → puede_tratarse_con → Heavy Slow Resistance.

## 14. Relaciones documentales

Las entidades podrán relacionarse con informes, casos clínicos, imágenes, publicaciones y vídeos docentes.

## 15. Relación con SPEC-001

SPEC-001 define cómo se construyen las entidades.

## 16. Relación con SPEC-000

El Knowledge Engine utiliza esta ontología para razonar.

## 17. Compatibilidad

Diseñada para exportarse a Neo4j, RDF, OWL, JSON, PostgreSQL y Airtable.

## 18. Criterios de calidad

- Sin duplicados.
- Relaciones explícitas.
- Evidencia documentada.
- Identificadores permanentes.
- Reutilización completa.

## 19. Roadmap

v1: Anatomía, Hallazgos, Patologías, Tratamientos.

v2: Ejercicio, Imagen, Investigación.

v3: Knowledge Graph, IA y Agentes.

## 20. Declaración final

La Ontología Clínica constituye el lenguaje oficial de FisioOS. Todo conocimiento del ecosistema deberá apoyarse en esta ontología.
