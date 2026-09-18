---
id: FISIOOS-CURRENT-HANDOFF
title: FisioOS Current Handoff
type: Project Handoff
status: Active
version: 1.4
created: 2026-08-21
updated: 2026-09-18
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

`19e0ac73dea5d142ae732d0f5ec61ed2a520824f`

Último commit:

`19e0ac7 — feat(clinical): add CASE-000004 shoulder ultrasound case`

Commits recientes relevantes:

- `19e0ac7 — feat(clinical): add CASE-000004 shoulder ultrasound case`
- `7270bfe — docs(project): update handoff after ultrasound case architecture`
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

limpio después del push de `19e0ac7`.

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

La arquitectura CASE + IMG se ha utilizado ya en dos casos ecográficos reales consecutivos:

- `CASE-000003`
- `CASE-000004`

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

Estructuras incorporadas con `CASE-000003`:

- `STR-000260 — Bursa subcoracoidea`
- `STR-000261 — Tubérculo mayor del húmero`

Estructuras incorporadas con `CASE-000004`:

- `STR-000262 — Tubérculo menor del húmero`
- `STR-000263 — Ligamento transverso del húmero`
- `STR-000264 — Deltoides`
- `STR-000265 — Cabeza del húmero`
- `STR-000266 — Apófisis coracoides`
- `STR-000267 — Espacio subcoracoideo`
- `STR-000268 — Acromion`

`STR-000263` permanece en `Review` y utiliza una formulación anatómica cautelosa debido a la variabilidad y discusión anatómica sobre la consideración del ligamento transverso del húmero como estructura independiente.

### Codo

Bloque específico:

`STR-000230` → `STR-000259`

Último STR existente confirmado:

`STR-000268`

Región anatómica utilizada para miembro superior:

`REG-000005 — Miembro superior`

No crear nuevos IDs anatómicos sin comprobar previamente el namespace real.

---

## Patología

### Hombro

Patologías relevantes:

- `PAT-000001 — Tendinopatía del supraespinoso`
- `PAT-000002 — Bursopatía subacromial-subdeltoidea`
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

Hallazgos reutilizables posteriores:

- `FIND-000007 — Señal Doppler intratendinosa`
- `FIND-000008 — Distensión bursal con contenido anecoico`
- `FIND-000009 — Irregularidad cortical insercional`

Último FIND existente confirmado:

`FIND-000009`

### Regla arquitectónica

Los hallazgos reutilizables no deben duplicarse innecesariamente por estructura o caso.

La localización anatómica debe establecerse mediante relaciones con `CASE`, `IMG` y `STR`.

Los hallazgos deben describir observaciones ecográficas y no convertirse automáticamente en diagnósticos.

### Precaución con FIND-000001

`FIND-000001 — Hipoecogenicidad intratendinosa` posee un título genérico, pero su descripción histórica está ligada al supraespinoso y a los casos piloto.

No reutilizar automáticamente en otros tendones hasta normalizar este nodo.

En `IMG-000010` la heterogeneidad e hipoecogenicidad del subescapular no se vinculó a `FIND-000001` debido a:

- posible anisotropía;
- incertidumbre de la captura aislada;
- especificidad histórica del nodo.

---

## Arquitectura de casos clínicos ecográficos

Modelo consolidado:

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

Entidad:

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

Cuando exista incertidumbre entre anisotropía y alteración tendinosa real, debe conservarse explícitamente la incertidumbre y evitar crear o asignar un `FIND` patológico sin evidencia suficiente.

---

## CASE-000003

Archivo:

`corpus/cases/shoulder/CASE-000003.md`

Título:

`Hombro derecho — tendinopatía del supraespinoso y bursitis subcoracoidea`

Hallazgos principales:

- tendinopatía del supraespinoso sin evidencia de rotura;
- bursopatía subcoracoidea;
- distensión bursal con contenido anecoico;
- pruebas clínicas de hombro positivas;
- resto del manguito evaluado dentro del estudio global.

Anatomía generada:

- `STR-000260 — Bursa subcoracoidea`
- `STR-000261 — Tubérculo mayor del húmero`

Patología generada:

- `PAT-000013 — Bursopatía subcoracoidea`

Hallazgo generado:

- `FIND-000008 — Distensión bursal con contenido anecoico`

---

## Imágenes de CASE-000003

### IMG-000004

`Porción larga del bíceps derecho — corte transversal`

Estructura:

`STR-000204`

No se asignó FIND patológico específico.

### IMG-000005

`Espacio subcoracoideo y tendón del subescapular derecho — corte transversal`

Medición visible:

`1,01 cm`

Interpretación:

ancho del espacio subcoracoideo.

No corresponde al espesor de la bursa.

### IMG-000006

`Espacio subacromial y tendón del supraespinoso derecho`

Medición visible:

`0,98 cm`

Interpretación:

ancho del espacio subacromial.

El campo `plane:` permanece pendiente de clasificación definitiva.

### IMG-000007

`Tendón del supraespinoso derecho — corte transversal`

Hallazgo directamente atribuible:

`FIND-000001 — Hipoecogenicidad intratendinosa`

La caracterización como tendinopatía pertenece a la integración del estudio completo.

---

## CASE-000004

Archivo:

`corpus/cases/shoulder/CASE-000004.md`

Título:

`Hombro izquierdo — tendinopatía focal del supraespinoso y bursopatía SASD`

Estado:

`Review`

Contexto clínico:

- dolor de hombro izquierdo de larga evolución;
- actividad deportiva y entrenamiento en gimnasio;
- trabajo de oficina;
- aumento del dolor y limitación funcional durante la fase aguda;
- mayor sintomatología en elevación y gestos por encima de la cabeza.

Hallazgos del estudio ecográfico:

- tendón del supraespinoso con patrón fibrilar conservado en la mayor parte de su espesor;
- pequeño foco de hipoecogenicidad intratendinosa;
- sin rotura parcial descrita;
- sin rotura completa;
- mínima reacción de la bursa subacromial-subdeltoidea;
- subescapular sin rotura estructural significativa en el estudio global;
- porción larga del bíceps correctamente situada en la corredera;
- infraespinoso sin alteraciones estructurales significativas;
- sin calcificaciones tendinosas descritas;
- sin derrame glenohumeral significativo.

Diagnóstico ecográfico estructurado:

- `PAT-000001 — Tendinopatía del supraespinoso`
- `PAT-000002 — Bursopatía subacromial-subdeltoidea`

Diagnóstico funcional documentado en el informe:

`Síndrome subacromial de sobreuso`

Este diagnóstico funcional se conserva como parte del caso y no se ha creado automáticamente como nueva entidad `PAT`.

---

## Imágenes de CASE-000004

Se crearon cinco imágenes:

### IMG-000008

`Corredera bicipital — corte transversal`

Estructura principal:

`STR-000204 — Porción larga del bíceps`

Referencias anatómicas relevantes:

- `STR-000211 — Subescapular`
- `STR-000261 — Tubérculo mayor del húmero`
- `STR-000262 — Tubérculo menor del húmero`
- `STR-000263 — Ligamento transverso del húmero`
- `STR-000264 — Deltoides`

No se asignó FIND patológico específico.

### IMG-000009

`Espacio subcoracoideo — corte ecográfico`

Estructura principal:

`STR-000267 — Espacio subcoracoideo`

Referencias:

- `STR-000265 — Cabeza del húmero`
- `STR-000203 — Tendón del subescapular`
- `STR-000266 — Apófisis coracoides`
- `STR-000264 — Deltoides`

El plano no se documentó porque no se estableció con suficiente certeza.

No se asignó FIND patológico específico.

### IMG-000010

`Tendón del subescapular en inserción — corte transversal`

Estructura principal:

`STR-000203 — Tendón del subescapular`

Hallazgos asociados:

- `FIND-000006 — Ausencia de rotura completa`
- `FIND-000009 — Irregularidad cortical insercional`

Se documentó heterogeneidad e hipoecogenicidad insercional, pero no se convirtió en `FIND-000001` debido a posible anisotropía y falta de certeza suficiente.

No existe evidencia suficiente en esta captura aislada para afirmar rotura parcial.

### IMG-000011

`Supraespinoso y espacio subacromial — corte longitudinal`

Plano registrado con cautela como probablemente longitudinal en la descripción técnica.

Medición visible:

`≈ 1,55 cm`

Interpretación:

medición del espacio subacromial según la referencia presente en la imagen.

Hallazgo asociado:

`FIND-000006 — Ausencia de rotura completa`

La heterogeneidad fibrilar observada se mantiene como observación inespecífica por posible anisotropía.

### IMG-000012

`Supraespinoso en inserción sobre tubérculo mayor — corte longitudinal`

Estructura principal:

`STR-000201 — Tendón del supraespinoso`

Hallazgo asociado:

`FIND-000006 — Ausencia de rotura completa`

El tendón mantiene continuidad hasta su inserción.

La discreta heterogeneidad e hipoecogenicidad insercional no se convirtió automáticamente en un FIND debido a posible anisotropía o cambios tendinosos leves.

No se documentan signos inequívocos de rotura parcial profunda ni rotura transfixiante en la captura aislada.

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

Ejemplo:

`FisioOS/Casos ecográficos/Miembro superior/Hombro/CASE-000003/`

Convenciones:

- cada CASE tiene un ID global permanente;
- cada IMG tiene un ID global permanente;
- los IMG no reinician numeración por caso ni por región;
- los IDs nunca se reutilizan;
- el identificador de Drive debe coincidir con el identificador de FisioOS;
- el informe se denomina `CASE-XXXXXX_REPORT.pdf`;
- las imágenes se denominan `IMG-XXXXXX.jpg` o formato equivalente admitido.

Para `CASE-000004`, las referencias `source_url` permanecen pendientes hasta registrar la ubicación correspondiente en Google Drive.

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

Debe mantenerse diferenciación entre:

1. contenido del informe original;
2. observación directa de una imagen;
3. interpretación clínica;
4. inferencia del sistema.

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

Flujo preferido para creación de nuevos nodos:

1. identificar la entidad o imagen;
2. comprobar IDs y nodos existentes;
3. crear el archivo Markdown en Obsidian;
4. pegar el contenido completo;
5. realizar una validación global;
6. stagear únicamente archivos explícitamente revisados.

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
15. No asignar un FIND cuando una alteración pueda explicarse razonablemente por anisotropía y no exista evidencia suficiente.
16. No inferir el plano ecográfico cuando no pueda establecerse con suficiente certeza.
17. No incorporar identidad del paciente a los nodos clínicos anonimizados.

---

## Deuda estructural conocida

### FIND-000045

Existe una referencia textual previa a `FIND-000045`, pero no se confirmó la existencia de un archivo correspondiente.

Debe investigarse posteriormente como posible referencia colgante o deuda histórica.

No utilizar `FIND-000045` hasta verificar su origen.

### FIND-000001

El título es genérico, pero su descripción histórica está ligada al supraespinoso y a los casos piloto.

Debe valorarse una normalización futura antes de reutilizarlo sistemáticamente en otros tendones.

### Airtable histórico

Existen nodos antiguos que todavía contienen referencias de procedencia a:

`Airtable / Hombro.zip`

Airtable ya no forma parte del flujo actual de creación de casos.

Estas referencias históricas no deben eliminarse de forma oportunista durante la creación de nuevos casos.

Debe abordarse como una migración de procedencia separada y controlada.

### IMG-000006

El plano ecográfico permanece sin clasificar formalmente:

`plane:`

No completar por inferencia sin revisión clínica.

### Procedencia externa

Permanecen pendientes algunos `source_url` de casos e imágenes almacenados externamente.

No inventar URLs.

---

## Próxima fase recomendada

Prioridad inmediata:

1. actualizar, validar, commit y push de este `CURRENT_HANDOFF.md`;
2. después continuar enriqueciendo el grafo mediante nuevos casos clínicos reales;
3. mantener numeración global:
   - siguiente CASE esperado: `CASE-000005`;
   - siguiente IMG esperado: `IMG-000013`;
   - siguiente STR esperado, si realmente se necesita: `STR-000269`;
   - siguiente FIND esperado, si realmente se necesita: `FIND-000010`;
4. comprobar siempre los namespaces reales antes de utilizar esos IDs;
5. crear nuevas STR, FIND o PAT únicamente cuando el caso lo requiera;
6. mantener explícita la diferencia entre imagen aislada y estudio ecográfico completo.

No abrir nuevas capas taxonómicas de forma especulativa.

La prioridad continúa siendo enriquecer FisioOS mediante casos reales, imágenes clínicas y relaciones verificables.

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

Último bloque clínico completado:

`CASE-000004`

Últimas imágenes incorporadas:

`IMG-000008` → `IMG-000012`

Último commit clínico sincronizado:

`19e0ac7 — feat(clinical): add CASE-000004 shoulder ultrasound case`

Siguiente acción inmediata:

validar, commit y push de esta actualización de `CURRENT_HANDOFF.md`.

Después:

iniciar `CASE-000005` cuando exista un nuevo caso clínico real para incorporar.

Numeración esperada:

- `CASE-000005`
- `IMG-000013`
