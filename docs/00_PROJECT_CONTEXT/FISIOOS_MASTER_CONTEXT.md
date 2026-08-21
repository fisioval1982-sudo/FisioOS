---
id: FISIOOS-MASTER-CONTEXT
title: FisioOS Master Context
type: Project Context
status: Active
version: 1.0
created: 2026-08-21
updated: 2026-08-21
---

# FisioOS — Master Context

## Propósito de este documento

Este documento constituye la memoria operativa persistente de FisioOS.

Su objetivo es permitir que el proyecto pueda retomarse desde un nuevo chat, una nueva sesión de trabajo o por otro agente sin depender del historial completo de conversaciones anteriores.

No sustituye a la documentación técnica, clínica ni a los ADR. Resume el modelo mental, las convenciones y las decisiones necesarias para trabajar correctamente sobre el repositorio.

---

# 1. Qué es FisioOS

FisioOS es un sistema estructurado de conocimiento clínico orientado a fisioterapia.

El objetivo no es construir una colección de documentos aislados, sino una base de conocimiento interconectada capaz de representar relaciones entre:

- anatomía;
- exploración clínica;
- tests ortopédicos;
- ecografía musculoesquelética;
- patologías;
- casos clínicos;
- biomecánica;
- procedimientos;
- evidencia científica;
- material de referencia.

El repositorio debe funcionar progresivamente como un grafo de conocimiento clínico legible tanto por humanos como por sistemas de IA.

---

# 2. Principio fundamental

FisioOS debe distinguir entre:

1. conocimiento anatómico canónico;
2. estructuras descritas desde una perspectiva ecográfica;
3. tests clínicos;
4. patologías;
5. hallazgos;
6. casos clínicos;
7. regiones anatómicas;
8. material de referencia.

No debe utilizarse un mismo nodo para representar conceptos diferentes simplemente porque compartan una estructura anatómica.

Ejemplo:

- músculo supraespinoso;
- tendón del supraespinoso evaluado ecográficamente;

son conceptos relacionados, pero no necesariamente el mismo nodo semántico.

---

# 3. Identificadores principales

FisioOS utiliza identificadores persistentes.

Entre los actualmente utilizados:

- `STR-*` — estructuras anatómicas;
- `TEST-*` — tests clínicos;
- `CASE-*` — casos clínicos;
- `REG-*` — regiones anatómicas;
- `ADR-*` — Architecture Decision Records;
- `REF-*` — referencias o materiales fuente.

Los identificadores no deben reutilizarse.

Antes de crear un nuevo nodo debe comprobarse cuál es el último identificador existente.

---

# 4. Anatomía

Ruta principal actual:

`knowledge/anatomy/`

Para hombro:

`knowledge/anatomy/upper_limb/shoulder/`

## Principio de modelado

Los nodos anatómicos deben representar entidades anatómicas o regiones anatómicas reales.

Cuando sea necesario deben establecerse relaciones mediante:

- `parent`;
- `related_structures`;
- enlaces Obsidian `[[STR-*]]`.

Las relaciones deben tener significado anatómico, biomecánico o clínico real.

## Evitar sobreconexión

No debe enlazarse una estructura simplemente porque pueda tener alguna relación indirecta.

Una relación debe aportar información útil al grafo.

Especialmente en tests clínicos:

> que una estructura pueda verse sometida a carga durante una maniobra no significa que el test evalúe específicamente esa estructura.

---

# 5. Modelo enriquecido de nodo anatómico

Cuando proceda, los nodos anatómicos pueden incluir:

## Tipo

## Descripción anatómica

## Origen

## Inserción

## Inervación

## Función

## Biomecánica

## Relaciones anatómicas

## Exploración clínica

## Correlación ecográfica

## Patologías relacionadas

## Tests relacionados

## Variantes anatómicas

## Fuente científica

## Procedencia FisioOS

## Estado

No todas las secciones son obligatorias para todas las estructuras.

Debe evitarse inventar información para completar una plantilla.

---

# 6. Anatomía de hombro

Región:

`REG-000005`

Nodo general:

`STR-000100 — Hombro`

Nodo funcional:

`STR-000106 — Manguito rotador`

## Distinción histórica importante

Los nodos:

`STR-000201` a `STR-000207`

se originaron durante el lote piloto de casos/ecografía de hombro.

Algunos están descritos desde la perspectiva de estructuras evaluadas o mencionadas en informes ecográficos y no deben asumirse automáticamente como equivalentes a nodos anatómicos canónicos completos.

Durante la evolución de FisioOS se decidió separar ambos conceptos cuando fuese necesario.

Ejemplo:

`STR-000201 — Tendón del supraespinoso`

no sustituye a:

`STR-000208 — Supraespinoso`

---

# 7. Manguito rotador

Se desarrollaron nodos anatómicos específicos para:

- `STR-000208 — Supraespinoso`
- `STR-000209 — Infraespinoso`
- `STR-000210 — Redondo menor`
- `STR-000211 — Subescapular`

Estos nodos permiten integrar:

- anatomía;
- función;
- biomecánica;
- exploración;
- ecografía;
- patología;
- tests clínicos.

---

# 8. Bíceps y complejo bíceps-labrum

Nodos desarrollados:

- `STR-000212 — Bíceps braquial`
- `STR-000213 — Cabeza larga del bíceps braquial`
- `STR-000214 — Labrum glenoideo`
- `STR-000215 — Labrum glenoideo superior`
- `STR-000216 — Complejo bíceps-labrum`

Se decidió distinguir la anatomía de la cabeza larga del bíceps de:

`STR-000204 — Porción larga del bíceps`

porque este último procedía del modelo inicial relacionado con exploración ecográfica.

---

# 9. Articulación acromioclavicular

Nodo central:

`STR-000217 — Articulación acromioclavicular`

Sistema ligamentario desarrollado:

- `STR-000226 — Ligamento acromioclavicular`
- `STR-000227 — Ligamentos coracoclaviculares`
- `STR-000228 — Ligamento conoide`
- `STR-000229 — Ligamento trapezoide`

Jerarquía conceptual:

Articulación acromioclavicular
├── Ligamento acromioclavicular
└── Ligamentos coracoclaviculares
    ├── Ligamento conoide
    └── Ligamento trapezoide

No debe asumirse que un test provocativo acromioclavicular determina de forma aislada la integridad de estos ligamentos.

---

# 10. Sistema capsulolabral y estabilidad

Entre los nodos desarrollados se encuentran:

- `STR-000218 — Cápsula glenohumeral`
- `STR-000219 — Ligamentos glenohumerales`
- `STR-000220 — Ligamento glenohumeral inferior`
- `STR-000221 — Labrum glenoideo anterior`
- `STR-000222 — Labrum glenoideo posterior`
- `STR-000223 — Intervalo rotador`
- `STR-000224 — Ligamento coracohumeral`
- `STR-000225 — Ligamento glenohumeral superior`

## Intervalo rotador

El intervalo rotador debe entenderse como una región anatómica funcional y no como un ligamento aislado.

Se relaciona especialmente con:

- supraespinoso;
- subescapular;
- cabeza larga del bíceps;
- cápsula glenohumeral;
- ligamento coracohumeral;
- ligamento glenohumeral superior.

---

# 11. Tests clínicos de hombro

Ruta:

`knowledge/tests/shoulder/`

Actualmente se ha completado la batería:

`TEST-000001` → `TEST-000019`

Los 19 nodos existen.

La batería incluye tests relacionados con:

- dolor subacromial;
- manguito rotador;
- subescapular;
- bíceps;
- complejo bíceps-labrum;
- inestabilidad glenohumeral;
- labrum;
- articulación acromioclavicular.

Los últimos nodos creados fueron:

- `TEST-000015 — Signo del surco`
- `TEST-000016 — Prueba de carga y desplazamiento`
- `TEST-000017 — Prueba de Crank`
- `TEST-000018 — Prueba de aducción horizontal cruzada`
- `TEST-000019 — Prueba de cizallamiento acromioclavicular`

---

# 12. Principio de interpretación de tests

Un test clínico no debe presentarse como diagnóstico estructural definitivo cuando la evidencia no lo permite.

Debe distinguirse entre:

- estructura sometida a estrés;
- estructura anatómicamente relacionada;
- objetivo clínico del test;
- interpretación del resultado;
- diagnóstico definitivo.

Los tests deben interpretarse dentro del conjunto de:

- anamnesis;
- mecanismo lesional;
- exploración;
- otros tests;
- imagen cuando esté indicada;
- razonamiento clínico.

---

# 13. Relaciones TEST ↔ STR

Los tests pueden declarar estructuras mediante el campo:

`structures:`

Estas relaciones deben mantenerse conservadoras.

Ejemplo de criterio adoptado:

`TEST-000018` y `TEST-000019`

se relacionan directamente con:

- hombro;
- articulación acromioclavicular;
- ligamento acromioclavicular.

No se añadieron automáticamente conoide y trapezoide porque estas maniobras no determinan específicamente la integridad de cada componente coracoclavicular.

---

# 14. Referencias Obsidian

Se utilizan enlaces:

`[[TEST-000XXX]]`

`[[STR-000XXX]]`

etc.

No deben permanecer referencias provisionales como:

`[[TEST-*]]`

cuando el nodo correspondiente ya existe.

En agosto de 2026 se realizó una limpieza de estos comodines en la batería de hombro.

---

# 15. Calidad y validación

Antes de realizar commits de bloques importantes se ha adoptado la práctica de comprobar:

`git status --short`

`git --no-pager diff --check`

y, una vez staged:

`git --no-pager diff --cached --stat`

`git --no-pager diff --cached --check`

También deben comprobarse cuando sea necesario:

- IDs duplicados;
- referencias provisionales;
- existencia de nodos esperados;
- coherencia de relaciones;
- estado de `main` frente a `origin/main`.

---

# 16. Política de commits

Los commits deben ser semánticamente coherentes.

Evitar mezclar:

- creación de conocimiento clínico;
- mantenimiento del repositorio;
- documentación arquitectónica;
- saneamiento técnico;

cuando puedan separarse razonablemente.

Ejemplo reciente:

`130f9fd`
`feat(shoulder): complete instability labral and acromioclavicular test battery`

separado de:

`1e84b93`
`chore(repo): document media storage and resolve test references`

---

# 17. Multimedia

La política de almacenamiento de archivos multimedia pesados está documentada en:

`docs/08_ADR/ADR-013.md`

Principio:

Los binarios multimedia pesados de referencia no deben almacenarse directamente en Git.

Los originales se externalizan y Git conserva:

- análisis;
- metadatos;
- derivados textuales;
- trazabilidad.

Consultar ADR-013 antes de modificar esta política.

---

# 18. Historial Git saneado

Durante agosto de 2026 se realizó saneamiento del historial para eliminar vídeos MP4/MOV previamente versionados.

Se utilizó `git-filter-repo`.

Antes de la operación se crearon copias de seguridad.

Posteriormente se verificó la ausencia de los blobs de vídeo en las referencias Git conservadas.

No repetir una reescritura de historial sin revisar previamente:

- ADR-013;
- estado remoto;
- backups;
- ramas;
- consecuencias sobre colaboradores.

---

# 19. Problema observado con locks Git

Durante sesiones recientes aparecieron locks residuales:

`.git/index.lock`

y:

`.git/packed-refs.lock`

Antes de eliminarlos debe comprobarse siempre que no exista un proceso Git activo:

`ps aux | grep '[g]it'`

Solo cuando no exista proceso activo puede eliminarse el lock residual.

Nunca eliminar un lock de Git a ciegas.

---

# 20. Forma de trabajo

El desarrollo de FisioOS se realiza de manera incremental.

Flujo preferido:

1. identificar el siguiente nodo;
2. comprobar estructuras existentes;
3. detectar anatomía necesaria;
4. crear primero los nodos anatómicos cuando sean necesarios;
5. crear o enriquecer el test;
6. establecer relaciones;
7. validar;
8. stage;
9. revisar staged diff;
10. commit;
11. push;
12. comprobar `main == origin/main`.

Se evita crear grandes cantidades de nodos sin revisión intermedia.

---

# 21. Principio de evidencia

FisioOS debe diferenciar:

- hechos anatómicos establecidos;
- evidencia clínica;
- asociaciones;
- hipótesis;
- inferencias;
- hallazgos de imagen.

No inventar datos para completar nodos.

Cuando la evidencia de un test sea limitada, debe reflejarse explícitamente.

Las fuentes científicas deben poder identificarse.

---

# 22. Deuda de conocimiento conocida

Existen estructuras que pueden necesitar nodos propios en futuras expansiones.

Ejemplo identificado:

- ligamento glenohumeral medio.

No debe crearse automáticamente únicamente porque se haya detectado su ausencia.

Se creará cuando resulte necesario para el grafo o para el conocimiento que se esté desarrollando.

---

# 23. Fuente de verdad

La prioridad de fuentes para conocer el estado del proyecto debe ser:

1. contenido actual del repositorio;
2. ADR aceptados;
3. este MASTER_CONTEXT;
4. CURRENT_HANDOFF;
5. historial Git;
6. conversaciones previas.

Si una conversación antigua contradice el repositorio actual, debe verificarse el cambio antes de restaurar información antigua.

---

# 24. Actualización de este documento

Actualizar este archivo cuando cambien:

- arquitectura;
- convenciones;
- sistema de IDs;
- principios de modelado;
- decisiones estructurales importantes;
- políticas de almacenamiento;
- metodología de trabajo.

No utilizar este archivo como diario cronológico.

El estado inmediato de trabajo debe registrarse en:

`CURRENT_HANDOFF.md`

---

# 25. Regla para nuevas sesiones

Al iniciar una nueva sesión de trabajo sobre FisioOS:

1. leer este documento;
2. leer `CURRENT_HANDOFF.md`;
3. comprobar el repositorio;
4. verificar `git status --short`;
5. verificar `main` y `origin/main`;
6. no asumir que el estado descrito en una conversación anterior sigue siendo actual.
