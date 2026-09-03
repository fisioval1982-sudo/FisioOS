---
id: FISIOOS-CURRENT-HANDOFF
title: FisioOS Current Handoff
type: Project Handoff
status: Active
version: 1.3
created: 2026-08-21
updated: 2026-09-04
---

# FisioOS — Current Handoff

## Propósito

Este documento describe el estado operativo inmediato de FisioOS.

Debe actualizarse al terminar una sesión o bloque importante de trabajo para permitir retomar el proyecto desde un nuevo chat sin depender del historial de conversación.

Para el contexto estructural y las decisiones persistentes consultar:

`FISIOOS_MASTER_CONTEXT.md`

---

## Estado Git

Repositorio:

`FisiOS_v1`

Rama:

`main`

Estado confirmado:

`main == origin/main`

HEAD confirmado:

`23f69c4de8e310982ba9167ff26a94b9c006ebab`

Último commit:

`23f69c4 — feat(clinical): add CASE-000003 ultrasound case and images`

Commits recientes relevantes:

- `23f69c4 — feat(clinical): add CASE-000003 ultrasound case and images`
- `9e66087 — feat(clinical): update case template for ultrasound provenance`
- `1da1a89 — feat(ontology): add clinical image entity and template`
- `9766755 — docs(adr): define external storage for ultrasound cases`
- `f0422e4 — fix(knowledge): link dynamic indexes to graph`
- `c1a0034 — feat(ultrasound): add reusable intratendinous Doppler finding`
- `09439ac — feat(knowledge): add elbow dynamic index`
- `e285874 — feat(knowledge): add shoulder index and update handoff`
- `2c8e780 — chore(obsidian): add Dataview and normalize anatomy metadata`

Último estado confirmado del working tree:

limpio después del push de `23f69c4`.

---

## Estado general del conocimiento

FisioOS dispone actualmente de una base clínica estructurada para:

- hombro;
- codo;
- anatomía;
- tests clínicos;
- patologías;
- hallazgos ecográficos;
- casos clínicos;
- imágenes clínicas;
- tratamientos;
- ejercicios.

Se utiliza Obsidian como interfaz del grafo y Dataview para navegación dinámica.

---

## Tests clínicos

### Hombro

Batería completada:

`TEST-000001` → `TEST-000019`

### Codo

Batería completada:

`TEST-000020` → `TEST-000030`

Último TEST existente confirmado:

`TEST-000030`

Principios de modelado:

1. un test clínico no equivale a un diagnóstico estructural;
2. diferenciar dolor, aprehensión, laxitud, debilidad y síntomas neurales;
3. evitar sobreinterpretar pruebas aisladas;
4. utilizar relaciones anatómicas reales y evitar placeholders.

---

## Anatomía

### Hombro

Bloque anatómico previo:

`STR-000201` → `STR-000229`

Nuevas estructuras incorporadas con `CASE-000003`:

- `STR-000260 — Bursa subcoracoidea`
- `STR-000261 — Tubérculo mayor del húmero`

### Codo

Bloque específico:

`STR-000230` → `STR-000259`

Último STR existente confirmado:

`STR-000261`

Región anatómica utilizada para miembro superior:

`REG-000005 — Miembro superior`

No crear nuevos IDs anatómicos sin comprobar previamente el namespace real.

---

## Patología

### Hombro

Patologías ya existentes relevantes:

- `PAT-000001 — Tendinopatía del supraespinoso`
- `PAT-000002 — Bursopatía subacromial-subdeltoidea`

Nueva patología incorporada:

- `PAT-000013 — Bursopatía subcoracoidea`

### Codo

Bloque:

`PAT-000006` → `PAT-000012`

Último PAT existente confirmado:

`PAT-000013`

Las patologías deben mantenerse separadas de los hallazgos ecográficos individuales.

Un hallazgo aislado no implica automáticamente una entidad diagnóstica.

---

## Hallazgos ecográficos

Hallazgos iniciales de hombro:

- `FIND-000001 — Hipoecogenicidad intratendinosa`
- `FIND-000002 — Engrosamiento tendinoso`
- `FIND-000003 — Pérdida parcial del patrón fibrilar`
- `FIND-000004 — Contenido anecoico bursal leve`
- `FIND-000005 — Disminución del espacio subacromial`
- `FIND-000006 — Ausencia de rotura completa`

Hallazgo global reutilizable:

- `FIND-000007 — Señal Doppler intratendinosa`

Nuevo hallazgo global:

- `FIND-000008 — Distensión bursal con contenido anecoico`

Regla arquitectónica:

Los hallazgos que puedan reutilizarse entre regiones o estructuras deben modelarse como entidades globales y no duplicarse innecesariamente por región.

`FIND-000008` no identifica una bursa concreta ni incorpora severidad.

La localización anatómica y la magnitud deben establecerse mediante las relaciones con CASE, IMG y STR.

---

## Arquitectura de casos clínicos ecográficos

Se ha consolidado el modelo:

`CASE` → caso clínico estructurado.

`IMG` → imagen clínica original individual asociada al caso.

`STR` → estructura anatómica.

`FIND` → hallazgo ecográfico.

`PAT` → entidad patológica.

Los casos integran:

- contexto clínico;
- exploración;
- hallazgos ecográficos;
- diagnóstico funcional;
- diagnóstico ecográfico;
- imágenes;
- informe original;
- correlación clínico-ecográfica;
- tratamiento;
- entidades relacionadas;
- procedencia;
- validación;
- estado.

Plantilla actual:

`templates/TPL-CASE.md`

---

## Entidad IMG

Se incorporó formalmente la entidad:

`IMG | Imagen clínica`

Definición operativa:

Imagen clínica original anonimizada asociada a un caso, destinada a documentación, clasificación, análisis e IA.

Plantilla:

`templates/TPL-IMG.md`

Ubicación de metadatos:

`knowledge/ultrasound/images/`

Principio fundamental:

Una imagen estática solo debe contener los hallazgos atribuibles razonablemente a esa imagen.

Las conclusiones procedentes del estudio ecográfico global deben identificarse como tales y no presentarse como inferencias exclusivas de una captura.

---

## CASE-000003

Primer caso desarrollado con el nuevo modelo completo de procedencia e imágenes.

Archivo:

`corpus/cases/shoulder/CASE-000003.md`

Título:

`Hombro derecho — tendinopatía del supraespinoso y bursitis subcoracoidea`

Estado:

`Analizado`

Hallazgos principales:

- tendinopatía del supraespinoso sin evidencia de rotura;
- bursopatía subcoracoidea;
- distensión bursal con contenido anecoico;
- pruebas clínicas de hombro positivas;
- resto del manguito evaluado dentro del estudio global.

Nueva anatomía generada:

- `STR-000260 — Bursa subcoracoidea`
- `STR-000261 — Tubérculo mayor del húmero`

Nueva patología:

- `PAT-000013 — Bursopatía subcoracoidea`

Nuevo hallazgo:

- `FIND-000008 — Distensión bursal con contenido anecoico`

---

## Imágenes de CASE-000003

Se crearon:

### IMG-000004

`Porción larga del bíceps derecho — corte transversal`

Estructura:

`STR-000204`

La imagen documenta la porción larga del bíceps en la corredera bicipital.

No se asignó FIND patológico específico a esta captura.

### IMG-000005

`Espacio subcoracoideo y tendón del subescapular derecho — corte transversal`

Estructura principal:

`STR-000203`

Relaciones:

- `STR-000260`
- `FIND-000008`
- `PAT-000013`

Medición visible:

`1,01 cm`

Interpretación de la medición:

ancho del espacio subcoracoideo.

No corresponde al espesor de la bursa.

### IMG-000006

`Espacio subacromial y tendón del supraespinoso derecho`

Estructuras principales:

- `STR-000201`
- `STR-000205`
- `STR-000206`

Medición visible:

`0,98 cm`

Interpretación:

ancho del espacio subacromial.

El campo `plane:` quedó pendiente de clasificación definitiva.

### IMG-000007

`Tendón del supraespinoso derecho — corte transversal`

Estructura:

`STR-000201`

Hallazgo directamente atribuible a la imagen:

`FIND-000001 — Hipoecogenicidad intratendinosa`

La caracterización como tendinopatía pertenece a la integración del estudio completo.

---

## Almacenamiento de originales clínicos

Decisión arquitectónica consolidada mediante:

- `ADR-008`
- `ADR-013`

Los archivos binarios clínicos originales no se versionan en Git.

Google Drive almacena:

- informes PDF;
- imágenes ecográficas originales;
- otros medios clínicos pesados.

FisioOS almacena:

- metadatos;
- IDs;
- relaciones;
- hallazgos;
- interpretación estructurada;
- trazabilidad.

---

## Convención de almacenamiento en Google Drive

Jerarquía adoptada:

`FisioOS/Casos ecográficos/REGIÓN/ZONA/CASE-XXXXXX/`

Ejemplo actual:

`FisioOS/Casos ecográficos/Miembro superior/Hombro/CASE-000003/`

Contenido:

- `CASE-000003_REPORT.pdf`
- `IMG-000004.jpg`
- `IMG-000005.jpg`
- `IMG-000006.jpg`
- `IMG-000007.jpg`

Convenciones:

- cada CASE tiene un ID global permanente;
- cada IMG tiene un ID global permanente;
- los IMG no reinician numeración por caso ni por región;
- los IDs nunca se reutilizan;
- el identificador de Drive debe coincidir con el identificador de FisioOS.

---

## Procedencia y trazabilidad

Estándar:

`docs/04_Ontology/PROVENANCE-STANDARD.md`

Campos principales:

- `source`
- `source_type`
- `source_file`
- `source_url`
- `created_by`
- `reviewer`
- `review_date`
- `confidence`

Tipos conceptuales de afirmación:

- hecho verificado;
- afirmación procedente de fuente;
- interpretación clínica;
- inferencia del sistema;
- pendiente de verificación.

Una inferencia nunca debe presentarse como un hecho verificado.

En `CASE-000003` los `source_url` permanecen pendientes de incorporar.

---

## Índices dinámicos

Disponibles:

- `knowledge/index/INDEX-SHOULDER.md`
- `knowledge/index/INDEX-ELBOW.md`

Ambos utilizan Dataview.

Se añadieron wikilinks estructurales para evitar que los índices quedasen aislados en el grafo.

Shoulder:

- `REG-000005`
- `STR-000100`

Elbow:

- `REG-000005`
- `STR-000230`

---

## Obsidian y Dataview

Dataview está instalado y operativo.

Configuración:

- `.obsidian/community-plugins.json` versionado;
- `.obsidian/plugins/` excluido de Git;
- consultas JavaScript desactivadas;
- utilización preferente de consultas Dataview declarativas.

La anatomía existente fue normalizada para incorporar `region:`.

---

## Reglas de trabajo consolidadas

1. No utilizar `git add .`.
2. Stagear únicamente archivos explícitamente revisados.
3. Verificar `git status` antes y después del staging.
4. Verificar el contenido staged antes del commit.
5. Verificar sincronización con `origin/main` antes de cerrar un bloque.
6. No reutilizar IDs.
7. Comprobar el namespace antes de crear CASE, IMG, STR, FIND, PAT o TEST.
8. No crear wikilinks provisionales como `[[TEST-*]]` o `[[STR-*]]`.
9. No duplicar anatomía existente.
10. No confundir hallazgo ecográfico con diagnóstico.
11. No confundir observación de una imagen estática con conclusión del estudio completo.
12. Mantener separados originales binarios y conocimiento estructurado.
13. Evitar sobreconectar el grafo.
14. Registrar incertidumbre, procedencia e interpretación de forma explícita.

---

## Deuda estructural conocida

### FIND

Existe una referencia textual previa a `FIND-000045`, pero no se confirmó la existencia de un archivo correspondiente.

Debe investigarse posteriormente como posible referencia colgante o deuda histórica.

No utilizar `FIND-000045` hasta verificar su origen.

### IMG-000006

El plano ecográfico permanece sin clasificar formalmente:

`plane:`

No completar por inferencia sin revisión clínica.

### Procedencia

Los `source_url` de `CASE-000003` y sus IMG siguen pendientes de incorporar.

---

## Próxima fase recomendada

Prioridad inmediata:

1. terminar la actualización y commit de este `CURRENT_HANDOFF.md`;
2. después iniciar `CASE-000004` utilizando desde el principio la arquitectura CASE + IMG;
3. mantener numeración global:
   - siguiente CASE esperado: `CASE-000004`;
   - siguiente IMG esperado: `IMG-000008`;
4. crear nuevas STR, FIND o PAT únicamente cuando el nuevo caso realmente lo requiera;
5. seguir utilizando los casos reales para aumentar progresivamente la profundidad del grafo.

No abrir nuevas capas taxonómicas de forma especulativa.

La prioridad es enriquecer FisioOS mediante casos reales, imágenes clínicas y relaciones verificables.

---

## Comprobaciones al retomar

Antes de modificar nada:

```bash
git status --short
git rev-parse HEAD
git rev-parse origin/main
```
Después:

1. leer `FISIOOS_MASTER_CONTEXT.md`;
2. leer `CURRENT_HANDOFF.md`;
3. comprobar los últimos IDs reales;
4. verificar el contenido del repositorio;
5. continuar desde el estado encontrado y no desde recuerdos de conversaciones anteriores.

---

## Punto exacto de reanudación

Último bloque completado:

`CASE-000003`

Último commit sincronizado:

`23f69c4 — feat(clinical): add CASE-000003 ultrasound case and images`

Siguiente acción prevista:

actualizar y versionar este `CURRENT_HANDOFF.md`.

Después:

iniciar `CASE-000004`.
