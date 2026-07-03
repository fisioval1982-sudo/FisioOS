---
id: SPEC-001
title: MetaModelo de FisioOS
version: 0.1
status: Draft
owner: Pablo Salvador Coloma
created: 2026-07-03
updated: 2026-07-03
related:
  - DOC-016
  - DOC-001
tags:
  - metamodel
  - architecture
  - ontology
---

# MetaModelo de FisioOS

## 1. Objetivo

El MetaModelo define cómo se construye cualquier entidad dentro de FisioOS.

No define todavía todas las entidades clínicas. Define las reglas para crear entidades presentes y futuras.

## 2. Conceptos fundamentales

### Entidad

Unidad identificable del sistema.

Ejemplos: supraespinoso, tendinopatía, hipoecogenicidad, EPI, test de Jobe.

### Relación

Vínculo entre dos entidades.

Ejemplos: pertenece_a, puede_presentar, se_explora_con, puede_tratar.

### Atributo

Propiedad descriptiva de una entidad.

### Evento

Cambio relevante en el tiempo.

### Estado

Situación actual de una entidad o documento.

### Regla

Restricción o principio lógico que limita relaciones o inferencias.

## 3. Identificadores permanentes

Toda entidad tendrá un identificador único.

- STR-000001 para estructuras anatómicas.
- PAT-000001 para patologías.
- FIND-000001 para hallazgos.
- TRT-000001 para tratamientos.
- EXE-000001 para ejercicios.
- TEST-000001 para tests.
- DOC-000001 para documentos.
- ADR-000001 para decisiones arquitectónicas.

## 4. Tipos principales de entidad

- Estructura anatómica.
- Región anatómica.
- Hallazgo.
- Patología.
- Síntoma.
- Test clínico.
- Tratamiento.
- Ejercicio.
- Imagen.
- Documento.
- Caso clínico.
- Episodio clínico.
- Bibliografía.
- Regla.
- Protocolo.

## 5. Tipos principales de relación

- es_un
- pertenece_a
- parte_de
- puede_presentar
- puede_asociarse_a
- se_explora_con
- se_observa_en
- puede_tratar
- contraindicado_en
- recomendado_en
- genera
- deriva_de
- evidencia_por
- tiene_nivel_de_confianza

## 6. Reglas iniciales

1. Una observación no puede convertirse automáticamente en diagnóstico.
2. Un diagnóstico requiere contexto clínico.
3. Una imagen puede contener hallazgos, pero no tratamientos.
4. Un tratamiento puede aplicarse a una patología o episodio, pero no a una imagen.
5. Toda entidad publicada debe tener estado y nivel de confianza.
6. Toda relación importante debe ser explicable.

## 7. Ciclo de vida de una entidad

Draft → Review → Approved → Deprecated

## 8. Próximo paso

Construir la Ontología Clínica sobre este MetaModelo.
