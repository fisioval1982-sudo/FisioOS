---
id: FISIOOS-CURRENT-HANDOFF
title: FisioOS Current Handoff
type: Project Handoff
status: Active
version: 1.15
created: 2026-08-21
updated: 2026-10-26
---

# FisioOS — Current Handoff

## Propósito

Estado operativo de FisioOS para retomar el proyecto sin depender del historial de conversación.

Consultar también:

- `docs/00_PROJECT_CONTEXT/FISIOOS_MASTER_CONTEXT.md`
- ADR aceptados.
- Archivos reales del repositorio.

Este documento resume el estado documentado; no sustituye la revisión de las entidades ni su validación clínica.

## Repositorio y estado Git

Repositorio local:

`~/Documents/GitHub/FisiOS_v1`

Remoto:

https://github.com/fisioval1982-sudo/FisioOS.git

Rama: `main`.

Último commit confirmado y subido:

`73719fe — docs(clinical): document IMG-000022 measurement conditions and update case and handoff`

Ese commit incorporó:

- IMG-000022 en Review 0.3.
- CASE-000007 en Review 0.6.
- CURRENT_HANDOFF en versión 1.14.

Push confirmado:

`7ed50ee..73719fe main -> main`

Después se comprobó:

`## main...origin/main`

El árbol de trabajo estaba limpio y la rama sincronizada en esa comprobación.

Posteriormente se guardaron y revisaron mediante diff cambios locales en:

- `knowledge/ultrasound/images/IMG-000024.md`: Review 0.3.
- `corpus/cases/shoulder/CASE-000007.md`: Review 0.7.

Esta actualización del handoff acompaña la documentación de las referencias de los cálipers y de la posición durante la medición de IMG-000024.

La confirmación del explorador corresponde al 2026-10-25. Su incorporación a CASE-000007 0.7 y a este handoff corresponde al 2026-10-26.

Los cambios actuales todavía requieren comprobación final, staging explícito, commit y push.

No interpretar el estado limpio anterior como descripción del árbol de trabajo después de estas modificaciones.

## Arquitectura vigente

[[ADR-014]] sustituye la dependencia operativa de Airtable definida en ADR-007.

Distribución de responsabilidades:

- Git y Markdown: conocimiento estructurado y versionado.
- Obsidian: edición y navegación.
- GitHub: copia remota e histórico.
- Google Drive: binarios clínicos originales.

Airtable no es una dependencia operativa. Sus referencias conservadas son históricas o de procedencia.

Los originales PDF, imágenes y otros medios clínicos pesados permanecen fuera de Git conforme a [[ADR-008]] y [[ADR-013]].

El repositorio conserva metadatos, relaciones, descripciones y trazabilidad.

## Reglas de trabajo

1. Trabajar paso a paso.
2. Dar una única acción o comando cada vez cuando se trabaje con archivos o Git y esperar el resultado.
3. No utilizar `git add .`.
4. Stagear exclusivamente archivos concretos revisados.
5. Comprobar contenido y estado antes del commit.
6. Comprobar sincronización después del push.
7. No inventar datos clínicos, referencias bibliográficas, URLs ni resultados.
8. Mantener los nodos en `Review` mientras no estén suficientemente sustentados.
9. No reutilizar IDs ni reservarlos a partir de ejemplos.
10. Comprobar el namespace real antes de crear entidades.
11. Evitar duplicados y conexiones especulativas.
12. No incorporar identidad del paciente a los nodos anonimizados.
13. No completar planos ni condiciones de adquisición por inferencia insuficientemente sustentada.

En el terminal del usuario `rg` no está disponible. Utilizar `grep` o `git grep`.

Para evitar el paginador:

`git -C "$HOME/Documents/GitHub/FisiOS_v1" --no-pager ...`

Los textos Markdown se pegan en Obsidian, no en la terminal.

El usuario prefiere recibir el Markdown completo para sustituir el contenido de una nota.

Los comandos Git se ejecutan en Terminal.

Diferenciar la fecha de una confirmación del explorador, la fecha de actualización documental y la fecha de exploración clínica.

## Separación de afirmaciones clínicas

Diferenciar siempre:

1. Observación directa.
2. Información del caso, del informe o confirmada por el explorador.
3. Interpretación clínica.
4. Inferencia.
5. Evidencia científica.

Una captura estática no verifica automáticamente las conclusiones del estudio completo ni sus maniobras dinámicas.

La hipoecogenicidad o heterogeneidad aisladas no se convierten automáticamente en lesión estructural confirmada.

Los tests clínicos no equivalen por sí solos a un diagnóstico estructural.

Una confirmación anatómica del explorador debe registrarse como tal, diferenciada de la observación directa.

La confirmación del plano o de las condiciones de adquisición de una imagen no se traslada automáticamente a otra captura.

La orientación longitudinal respecto a un tendón no describe necesariamente la dirección de una línea de medición.

La confirmación del plano no completa las referencias de los cálipers ni estandariza por sí misma una medición.

La descripción retrospectiva de referencias y posición mejora la documentación, pero no demuestra por sí misma estandarización ni reproducibilidad.

No convertir «rotación externa máxima alcanzada por el paciente» en un ángulo medido ni en una amplitud normal.

No convertir la descripción «codo en línea recta apuntando hacia atrás» en un valor angular ni en extensión completa del codo.

No atribuir automáticamente un protocolo estandarizado a una postura descrita por el explorador.

La identificación del plano y de la región de inserción de un tendón no confirma por sí misma una lesión ni su extensión.

Las relaciones FIND → TRT o EX no son indicaciones automáticas.

La ecografía aporta información estructural. La decisión terapéutica integra síntomas, exploración, función, objetivos y tolerancia.

Distinguir tratamiento propuesto, tratamiento aplicado y resultados documentados.

## Estado general del conocimiento

La base estructurada incluye hombro, codo, anatomía, tests, patologías, hallazgos ecográficos, casos, imágenes, tratamientos y ejercicios.

Modelo:

- CASE: caso clínico.
- IMG: imagen individual y su descripción.
- STR: estructura anatómica.
- FIND: hallazgo reutilizable.
- PAT: entidad patológica.
- TRT: intervención terapéutica.
- EX: ejercicio.

Plantillas:

- `templates/TPL-CASE.md`
- `templates/TPL-IMG.md`

Ubicaciones principales:

- Casos: `corpus/cases/shoulder/`
- Imágenes: `knowledge/ultrasound/images/`
- Tratamientos: `knowledge/treatment/shoulder/`
- Ejercicios: `knowledge/exercise/shoulder/`
- Anatomía de hombro: `knowledge/anatomy/upper_limb/shoulder/`
- Patología de hombro: `knowledge/pathology/shoulder/`

## Anatomía y tests

Tests de hombro documentados:

`TEST-000001` → `TEST-000019`

Tests de codo documentados:

`TEST-000020` → `TEST-000030`

Último TEST conocido: `TEST-000030`.

Bloques anatómicos documentados:

- Hombro: `STR-000201` → `STR-000229`.
- Codo: `STR-000230` → `STR-000259`.
- Incorporaciones posteriores de hombro: `STR-000260` → `STR-000268`.

Referencias relevantes:

- STR-000201: tendón del supraespinoso.
- STR-000203: tendón del subescapular.
- STR-000204: porción larga del bíceps.
- STR-000205: bursa subacromial-subdeltoidea.
- STR-000206: espacio subacromial.
- STR-000260: bursa subcoracoidea.
- STR-000261: tubérculo mayor del húmero.
- STR-000262: tubérculo menor del húmero.
- STR-000263: ligamento transverso del húmero.
- STR-000264: deltoides.
- STR-000265: cabeza del húmero.
- STR-000266: apófisis coracoides.
- STR-000267: espacio subcoracoideo.
- STR-000268: acromion.

STR-000263 permanece en Review con formulación anatómica cautelosa.

Último STR conocido: `STR-000268`.

Región utilizada: `REG-000005 — Miembro superior`.

Estos límites deben comprobarse de nuevo antes de asignar IDs.

## Patologías y hallazgos

Último PAT conocido: `PAT-000014`.

Patologías relevantes:

- PAT-000001: tendinopatía del supraespinoso.
- PAT-000002: bursopatía subacromial-subdeltoidea.
- PAT-000013: bursopatía subcoracoidea.
- PAT-000014: rotura parcial del tendón del supraespinoso.

PAT-000014 permanece en Review. Se creó con CASE-000006 y se relaciona en CASE-000007 con la interpretación del informe, sin afirmar que una captura aislada confirme la rotura.

Hallazgos existentes:

- FIND-000001: hipoecogenicidad intratendinosa.
- FIND-000002: engrosamiento tendinoso.
- FIND-000003: pérdida parcial del patrón fibrilar.
- FIND-000004: contenido anecoico bursal leve.
- FIND-000005: disminución del espacio subacromial.
- FIND-000006: ausencia de rotura completa.
- FIND-000007: señal Doppler intratendinosa.
- FIND-000008: distensión bursal con contenido anecoico.
- FIND-000009: irregularidad cortical insercional.

Último FIND conocido: `FIND-000009`.

FIND-000001–000006 fueron enriquecidos y permanecen en Review 1.1. Su revisión bibliográfica formal sigue pendiente antes de considerar Approved.

Commits de ese bloque:

- `7d1e625`: FIND-000001.
- `e8bc934`: FIND-000002.
- `7aa2f3b`: FIND-000003.
- `5bc8085`: FIND-000004.
- `cc095e8`: FIND-000005.
- `75513b2`: FIND-000006.
- `3575cc4`: corrección de frontmatter duplicado de FIND-000003.

No se creó FIND-000010 durante la incorporación de CASE-000006 ni CASE-000007.

### FIND-000045 — resuelto

Es un ID ficticio del ejemplo de `docs/03_Architecture/SPEC-000.md`.

No es una entidad ausente y no debe crearse ni reservarse.

## Bloque completado: TRT y EX

Se enriquecieron los cuatro tratamientos y los cuatro ejercicios del piloto.

Todos se mantienen en Review. El enriquecimiento documental no equivale a aprobación clínica ni a comprobación bibliográfica definitiva.

### Tratamientos

| ID | Título | Commit |
| --- | --- | --- |
| TRT-000001 | Control motor escapular | 52e83ca |
| TRT-000002 | Fortalecimiento progresivo del manguito rotador | 01d52dc |
| TRT-000003 | Reeducación del ritmo escapulohumeral | 82cdb62 |
| TRT-000004 | Movilización escapular | 0f2fd6d |

### Ejercicios

| ID | Título | Commit |
| --- | --- | --- |
| EX-000001 | Rotación externa isométrica | 7c7ef93 |
| EX-000002 | Abducción isométrica contra pared | ddca948 |
| EX-000003 | Ejercicios pendulares | f3a9aa7 |
| EX-000004 | Punches de serrato anterior | dd1cd12 |

Los ocho commits fueron subidos a main.

Principios mantenidos:

- Dosificación contextual, sin cifras universales inventadas.
- Selección y progresión según objetivos, capacidad y respuesta.
- Separación entre mecanismos propuestos y resultados demostrados.
- No asumir una posición escapular universalmente ideal.
- No atribuir analgesia automática a los isométricos.
- No convertir relaciones documentales en prescripciones.
- Registro de precauciones, suspensión y reevaluación.
- Trazabilidad y límites de la evidencia.

Consultar cada ficha antes de reutilizar recomendaciones o referencias.

[[ADR-010]] establece el modelo de EX, incluida dosificación contextual y registro de contraindicaciones y criterios de suspensión.

La auditoría de octubre identificó TRT y EX como cuello de botella documental. Su enriquecimiento se completó; la validación sigue abierta.

## Casos anteriores conservados

Los resúmenes siguientes son antecedentes documentales. No representan una nueva validación de sus conclusiones clínicas.

### CASE-000003

Hombro derecho; informe de tendinopatía del supraespinoso y bursopatía subcoracoidea.

Imágenes: IMG-000004–000007.

Generó STR-000260, STR-000261, PAT-000013 y FIND-000008.

IMG-000005 registra 1,01 cm como espacio subcoracoideo, no como grosor bursal.

IMG-000006 registra 0,98 cm como espacio subacromial; su plano sigue pendiente.

### CASE-000004

Hombro izquierdo; tendinopatía focal del supraespinoso y bursopatía SASD descritas en el informe.

Imágenes: IMG-000008–000012.

Generó STR-000262–000268.

IMG-000009 conserva el plano sin clasificar.

Las variaciones tendinosas inespecíficas no se convirtieron automáticamente en FIND patológicos.

### CASE-000005

Hombro izquierdo; pintor con limitación funcional y pérdida de fuerza.

Imágenes: IMG-000013–000015.

Se reutilizaron entidades existentes, sin crear nuevos STR, FIND o PAT.

Las conclusiones del informe se mantienen separadas del alcance de las capturas individuales.

### CASE-000006

Hombro derecho; dolor desde noviembre tras bajar una garrafa de aproximadamente 5 litros.

Imágenes: IMG-000016–000020.

Introdujo PAT-000014 en Review.

La interpretación de lesión parcial procede de la integración del estudio descrito, sin confirmación inequívoca mediante una única captura.

IMG-000017 registra 0,96 cm (9,6 mm).

No se creó FIND-000010 ni una patología nueva para los cambios acromioclaviculares.

No confundir este caso con CASE-000007.

## Último caso incorporado: CASE-000007

Commit de incorporación:

`1ffff83 — docs(clinical): add CASE-000007 and ultrasound image records`

Se incorporaron seis archivos:

- `corpus/cases/shoulder/CASE-000007.md`
- `knowledge/ultrasound/images/IMG-000021.md`
- `knowledge/ultrasound/images/IMG-000022.md`
- `knowledge/ultrasound/images/IMG-000023.md`
- `knowledge/ultrasound/images/IMG-000024.md`
- `knowledge/ultrasound/images/IMG-000025.md`

Los seis nodos se incorporaron en Review 0.1.

Estado documental al preparar este handoff el 2026-10-26:

| Entidad | Estado | Versión | Situación |
| --- | --- | --- | --- |
| CASE-000007 | Review | 0.7 | Cambio local revisado; pendiente de commit |
| IMG-000021 | Review | 0.1 | Sin cambios en este bloque |
| IMG-000022 | Review | 0.3 | Sincronizada mediante 73719fe |
| IMG-000023 | Review | 0.2 | Sincronizada mediante cb0b9a6 |
| IMG-000024 | Review | 0.3 | Cambio local revisado; pendiente de commit |
| IMG-000025 | Review | 0.2 | Sincronizada mediante 7ed50ee |

### Información del caso

Hombro derecho doloroso desde septiembre tras cierre forzado de una puerta en contexto laboral.

El informe recoge limitación funcional, Neer positivo y Jobe positivo.

No constan año de inicio, fecha de exploración, edad, sexo, dominancia ni medidas funcionales iniciales.

No completar estos datos por inferencia.

### Interpretación del informe

El informe describe tendinopatía del supraespinoso con lesión parcial insercional de predominio articular/intrasustancia, sin rotura completa ni retracción, y cambios bursales leves.

También describe reducción dinámica subacromial, cambios leves peritendinosos bicipitales y cambios degenerativos acromioclaviculares.

Estas afirmaciones se registran como contenido del informe.

La relación con PAT-000001, PAT-000002 y PAT-000014 representa esa interpretación documental, sujeta a revisión.

No se asumieron:

- causalidad directa entre tests y cambios ecográficos;
- origen traumático de todas las alteraciones;
- predominio biomecánico demostrado;
- capacidad tisular para una carga concreta;
- pronóstico individual favorable por ausencia de rotura completa.

### Tratamiento

La orientación terapéutica se conserva como propuesta del informe.

No constan aplicación, dosis ni resultados.

No se asignaron automáticamente TRT o EX.

### Imágenes

| ID | Contenido | Dato o límite principal |
| --- | --- | --- |
| IMG-000021 | Bíceps derecho en corredera | Plano transversal; descripción local |
| IMG-000022 | Espacio subcoracoideo derecho | 1,23 cm / 12,3 mm; longitudinal respecto al subescapular; referencias y posición descritas por el explorador |
| IMG-000023 | Tendón del subescapular derecho | Patrón fibrilar local; plano longitudinal confirmado específicamente |
| IMG-000024 | Espacio subacromial derecho | 1,05 cm / 10,5 mm; longitudinal respecto al supraespinoso; referencias y posición descritas por el explorador |
| IMG-000025 | Supraespinoso derecho | Área focal de menor ecogenicidad; longitudinal en región de inserción y referencia cortical humeral confirmados |

El explorador confirmó que IMG-000022 mide el espacio subcoracoideo y que IMG-000024 mide el espacio subacromial.

Las condiciones de medición se documentan individualmente en los apartados siguientes.

No se clasificaron las distancias como normales o disminuidas.

IMG-000025 no confirma por sí sola una rotura parcial ni cuantifica su extensión.

No quedan planos pendientes en el conjunto IMG-000021–IMG-000025 según la documentación actual.

Las cinco fichas conservan `findings: []`.

No se crearon nuevos STR, FIND ni PAT.

### Revisiones de planos completadas y sincronizadas

#### IMG-000022

Confirmación del explorador del 2026-10-24:

- longitudinal respecto al tendón del subescapular;
- identificación de la apófisis coracoides;
- visualización del tendón pasando por debajo de ella.

IMG-000022 pasó a Review 0.2 con `plane: Longitudinal` y STR-000203 y STR-000266 en `structures`.

CASE-000007 pasó a Review 0.2 e incorporó STR-000266.

Se conservaron 1,23 cm (12,3 mm) y `findings: []`.

La relación anatómica con la coracoides no se interpretó como compresión patológica.

Bloque sincronizado mediante 115cbcc, incluyendo handoff 1.10.

#### IMG-000023

Confirmación específica del explorador del 2026-10-24:

- corte longitudinal del tendón del subescapular.

La confirmación no procede de trasladar el plano de IMG-000022.

IMG-000023 pasó a Review 0.2 con `plane: Longitudinal`.

CASE-000007 pasó a Review 0.3.

Se conservaron STR-000203, `findings: []` y la separación entre apariencia local e integridad global descrita en el informe.

Bloque sincronizado mediante cb0b9a6, incluyendo handoff 1.11.

#### IMG-000024

Confirmación específica del explorador del 2026-10-24:

- longitudinal respecto al tendón del supraespinoso;
- identificación del tendón a su salida por el espacio subacromial.

La referencia a su salida describe la región anatómica y no equivale a observar deslizamiento mediante una secuencia dinámica.

IMG-000024 pasó a Review 0.2 con `plane: Longitudinal` y STR-000201 en sus estructuras relacionadas.

CASE-000007 pasó a Review 0.4 el 2026-10-25, incorporando la confirmación del día anterior.

Se conservaron 1,05 cm (10,5 mm) y `findings: []`.

En aquella revisión permanecían pendientes las referencias de los cálipers y la posición. Su confirmación posterior se documenta más adelante.

Bloque sincronizado mediante bff887a, incluyendo handoff 1.12.

#### IMG-000025

Confirmación específica del explorador del 2026-10-25:

- longitudinal respecto al tendón del supraespinoso;
- representación de la región de su huella de inserción o footprint;
- visualización de la cortical de la cabeza del húmero.

La referencia cortical humeral y la localización de la huella de inserción se conservan como identificaciones diferenciadas.

IMG-000025 pasó a Review 0.2 con `plane: Longitudinal` y STR-000265 en sus estructuras relacionadas.

CASE-000007 pasó a Review 0.5 y añadió STR-000265.

Se mantuvieron la observación del área focal señalada, `findings: []` y Review.

La confirmación anatómica no establece rotura parcial, extensión, porcentaje de espesor afectado, antigüedad, progresión, capacidad de carga ni pronóstico.

Permanecen pendientes la corroboración del área señalada y la validación clínica final.

Bloque sincronizado mediante 7ed50ee, incluyendo handoff 1.13.

Las enumeraciones de planos pendientes de los historiales del caso describen el estado existente en cada revisión.

### Condiciones de medición de IMG-000022 — completadas documentalmente y sincronizadas

El 2026-10-25, el explorador confirmó específicamente:

- línea recta desde el punto más bajo de la apófisis coracoides hasta la cortical de la cabeza humeral;
- codo junto al tronco;
- rotación externa máxima alcanzada por el paciente.

No se aporta cuantificación angular de la rotación externa.

La expresión «punto más bajo» conserva la descripción del explorador. No se sustituye por una referencia anatómica más específica sin confirmación.

No se presupone que la línea represente una distancia mínima ni una perpendicular a ambas corticales.

La posición máxima alcanzada por el paciente no se convierte en una amplitud normal ni en una medición clínica de movilidad.

IMG-000022 pasó a Review 0.3:

- incorporó referencias y posición como información retrospectiva del explorador;
- añadió STR-000265;
- actualizó condiciones documentadas y limitaciones;
- conservó el plano longitudinal;
- conservó 1,23 cm (12,3 mm);
- conservó `findings: []`.

Permanecen sin especificar:

- posición corporal;
- grado de flexión del codo;
- carácter activo, asistido o pasivo de la rotación;
- respuesta sintomática durante la medición;
- orientación y presión del transductor.

No se documentan mediciones repetidas ni comparación contralateral específica para esta captura.

No se establece reproducibilidad ni correspondencia con un protocolo estandarizado.

CASE-000007 pasó a Review 0.6:

- incorporó la confirmación en fuentes, descripción de la captura y procedencia;
- diferenció las condiciones descritas de los detalles aún pendientes;
- mantuvo pendientes las condiciones de IMG-000024 en aquella versión;
- conservó historiales, estructuras, patologías atribuidas al informe y mediciones.

Las condiciones de IMG-000022 no se extrapolan a otras capturas.

Bloque sincronizado mediante 73719fe, incluyendo handoff 1.14.

### Condiciones de medición de IMG-000024 — cambios locales actuales

El 2026-10-25, el explorador confirmó específicamente:

- línea recta desde el borde inferior del acromion hasta la cortical de la cabeza humeral;
- palma de la mano sobre el glúteo;
- codo dirigido hacia atrás, descrito como «en línea recta apuntando hacia atrás».

No convertir esta descripción del codo en un ángulo ni interpretarla como extensión completa del codo.

No atribuir automáticamente un protocolo estandarizado a la posición descrita.

Las referencias y la posición proceden de la confirmación retrospectiva del explorador. Se diferencian de la lectura directa de 1,05 cm (10,5 mm).

No se especifican los puntos corticales exactos dentro de las referencias descritas.

No se presupone una distancia mínima entre superficies ni una perpendicular a ambas corticales.

IMG-000024 pasa a Review 0.3:

- incorpora las referencias de los cálipers y la posición;
- añade STR-000268 y STR-000265 a sus estructuras relacionadas;
- actualiza los datos documentados y las limitaciones;
- conserva el plano longitudinal respecto al supraespinoso;
- conserva 1,05 cm (10,5 mm);
- conserva `findings: []`.

Permanecen sin especificar:

- posición corporal;
- lado del glúteo utilizado como apoyo;
- grados de elevación, extensión o rotación del hombro;
- grado de flexión del codo;
- carácter activo, asistido o pasivo de la posición;
- respuesta sintomática durante la medición;
- orientación y presión del transductor.

No se documentan mediciones repetidas ni comparación contralateral específica para esta captura.

La descripción no demuestra estandarización, reproducibilidad ni equivalencia con una medición estandarizada de distancia acromiohumeral.

La actualización no clasifica la distancia como normal, aumentada o disminuida.

No confirma reducción dinámica, compresión sintomática ni causalidad del dolor.

CASE-000007 pasa a Review 0.7, actualizado el 2026-10-26:

- incorpora la confirmación del explorador del 2026-10-25;
- añade STR-000268 a sus estructuras relacionadas;
- actualiza fuentes, descripción de IMG-000024, condiciones pendientes y procedencia;
- diferencia la fecha de confirmación de la fecha de incorporación documental;
- retira las referencias y la posición de IMG-000024 de los datos totalmente desconocidos;
- conserva los detalles aún no especificados;
- mantiene historiales, patologías atribuidas al informe, mediciones y Review.

La posición de adquisición no sustituye una medición clínica de movilidad.

No se incorporan nuevos FIND, diagnósticos ni indicaciones terapéuticas.

Los cambios guardados de IMG-000024 y CASE-000007 se han revisado mediante diff.

Su commit y push siguen pendientes al redactar este handoff.

### Procedencia externa

Carpeta facilitada por el usuario:

https://drive.google.com/drive/folders/13cdK0eqBZ3iXtPjxMam_F-M_AEDypjvP

Referencia documental del informe:

`CASE-000007_REPORT.pdf`

Los source_url de CASE-000007 e IMG-000021–000025 apuntan a la carpeta, no a URLs individuales verificadas.

No afirmar una verificación independiente del contenido de Drive.

## Trazabilidad y almacenamiento

Convención:

`FisioOS/Casos ecográficos/REGIÓN/ZONA/CASE-XXXXXX/`

Informe:

`CASE-XXXXXX_REPORT.pdf`

Imágenes:

`IMG-XXXXXX.jpg` o formato equivalente documentado.

Los IDs de IMG son globales y no reinician por caso.

Los source_url de CASE-000003–000007 están registrados como carpetas de procedencia.

La trazabilidad individual de imágenes permanece pendiente cuando proceda.

Campos de procedencia:

- source
- source_type
- source_file
- source_url
- created_by
- reviewer
- review_date
- confidence

Consultar `docs/04_Ontology/PROVENANCE-STANDARD.md`.

## Obsidian e índices

Índices existentes:

- `knowledge/index/INDEX-SHOULDER.md`
- `knowledge/index/INDEX-ELBOW.md`

Utilizan Dataview.

Configuración documentada:

- `.obsidian/community-plugins.json` versionado.
- `.obsidian/plugins/` excluido de Git.
- Consultas JavaScript desactivadas.
- Preferencia por consultas declarativas.

La navegación y configuración no se han vuelto a comprobar durante este bloque.

## Pendientes vigentes

### Validación clínica

- Mantener TRT-000001–000004 y EX-000001–000004 en Review.
- Completar comprobaciones clínicas y bibliográficas antes de valorar Approved.
- Revisar bibliografía de FIND-000001–000006.
- No interpretar estados Approved heredados de otros nodos como validación nueva.

### Imágenes

- Confirmar plano de IMG-000006.
- Conservar pendiente el plano de IMG-000009 mientras no exista confirmación.
- Completar los detalles de adquisición aún no especificados de IMG-000022 e IMG-000024 cuando proceda.
- Conservar sus referencias y posiciones como información del explorador, sin afirmar estandarización.
- Corroborar la interpretación del área señalada en IMG-000025.
- Completar URLs individuales cuando proceda.
- Mantener IMG-000021–IMG-000025 en Review.
- No confundir confirmación del plano o descripción de la medición con validación clínica final.

No quedan planos pendientes en las cinco imágenes de CASE-000007 según la documentación actual.

Las referencias de los cálipers y las posiciones de IMG-000022 e IMG-000024 ya cuentan con descripción específica del explorador. Los detalles restantes se enumeran en sus fichas.

### CASE-000007

- Completar fechas y contexto clínico relevante.
- Registrar síntomas, movilidad, fuerza, objetivos y capacidad funcional.
- Documentar tratamiento aplicado y evolución si existen.
- Mantener separadas observaciones, información del explorador, informe e interpretación.
- No confirmar rotura o extensión únicamente desde IMG-000025.
- No utilizar las posiciones de adquisición de IMG-000022 e IMG-000024 como resultados de mediciones clínicas de movilidad.

### Mantenimiento

- Revisar de forma controlada descripciones heredadas excesivamente mecanicistas.
- No modificar retrospectivamente casos o asignar tratamientos sin evidencia documental.
- Mantener mantenimiento y cambios clínicos como bloques revisables separados.

## Numeración para futuras incorporaciones

Últimos IDs conocidos:

- CASE-000007.
- IMG-000025.
- STR-000268.
- FIND-000009.
- PAT-000014.
- TEST-000030.
- TRT-000004.
- EX-000004.

Las revisiones de planos y condiciones de medición documentadas en este bloque no crean entidades ni consumen nuevos IDs.

Siguientes candidatos, siempre sujetos a comprobación del namespace real:

- CASE-000008.
- IMG-000026.
- STR-000269, solo si hace falta.
- FIND-000010, solo si está suficientemente sustentado.
- PAT-000015, solo si hace falta.

No se consideran reservados por aparecer en este documento.

## Verificación de bloques anteriores

Los siguientes bloques se completaron mediante staging explícito, commit, push y comprobación final de árbol limpio y rama sincronizada.

| Bloque | Commit | Resumen documentado | Push |
| --- | --- | --- | --- |
| Incorporación de CASE-000007 e IMG-000021–000025 | 1ffff83 | Seis archivos; 1.080 líneas añadidas | dd1cd12..1ffff83 |
| Handoff 1.9 | ae09b86 | Actualización del contexto del proyecto | 1ffff83..ae09b86 |
| Plano de IMG-000022 y handoff 1.10 | 115cbcc | Tres archivos; 221 inserciones y 48 eliminaciones | ae09b86..115cbcc |
| Plano de IMG-000023 y handoff 1.11 | cb0b9a6 | Tres archivos; 176 inserciones y 63 eliminaciones | 115cbcc..cb0b9a6 |
| Plano de IMG-000024 y handoff 1.12 | bff887a | Tres archivos; 198 inserciones y 58 eliminaciones | cb0b9a6..bff887a |
| Plano de IMG-000025 y handoff 1.13 | 7ed50ee | Tres archivos; 217 inserciones y 67 eliminaciones | bff887a..7ed50ee |
| Condiciones de IMG-000022 y handoff 1.14 | 73719fe | Tres archivos; 270 inserciones y 70 eliminaciones | 7ed50ee..73719fe |

En los bloques clínicos indicados se revisaron los cambios y se comprobó `git diff --cached --check` sin errores.

Estas comprobaciones corresponden a esos bloques anteriores, no a los cambios locales posteriores.

Una comprobación de espacios mediante Git no equivale a validación clínica, bibliográfica ni del esquema YAML.

## Verificación del bloque actual

Se han leído y revisado mediante diff los cambios guardados de:

- IMG-000024, versión 0.3.
- CASE-000007, versión 0.7.

Los cambios incorporan la confirmación del explorador sobre las referencias de los cálipers y la posición durante la medición subacromial.

Se mantienen Review, la distancia de 1,05 cm (10,5 mm) y la separación entre observación directa e información del explorador.

No se añaden FIND ni se clasifica la distancia como patológica.

El caso conserva los historiales anteriores y diferencia las condiciones documentadas de los detalles aún no especificados.

Esta versión 1.15 del handoff se prepara para acompañar ese bloque.

Quedan pendientes:

- guardar y revisar el cambio del handoff;
- comprobar espacios mediante `git diff --check`;
- comprobar estado Git y alcance de los cambios;
- stagear explícitamente los archivos revisados;
- comprobar el contenido staged;
- realizar commit;
- realizar push;
- comprobar sincronización y árbol limpio.

No se afirma haber ejecutado un validador automático de YAML, IDs o enlaces.

No se afirma validación clínica definitiva ni revisión bibliográfica nueva durante esta actualización documental.

## Punto exacto de reanudación

Último commit confirmado y sincronizado:

`73719fe`

Último caso incorporado:

CASE-000007, con IMG-000021–000025, mediante 1ffff83.

Última revisión sincronizada del caso:

Review 0.6 mediante 73719fe.

Trabajo local posterior:

- IMG-000024: Review 0.3, referencias de los cálipers y posición durante la medición documentadas por confirmación del explorador.
- CASE-000007: Review 0.7, actualizado para reflejar esas condiciones y los detalles aún pendientes.
- CURRENT_HANDOFF: actualización propuesta a versión 1.15.

Acción inmediata:

Guardar y revisar este handoff, completar las comprobaciones de los tres archivos y versionar y subir el bloque siguiendo el flujo de un comando cada vez.

Archivos del bloque:

- `knowledge/ultrasound/images/IMG-000024.md`
- `corpus/cases/shoulder/CASE-000007.md`
- `docs/00_PROJECT_CONTEXT/CURRENT_HANDOFF.md`

No asumir commit ni push hasta comprobar sus resultados.

Después:

Continuar con los detalles aún no especificados de IMG-000022 e IMG-000024, la corroboración del área señalada en IMG-000025, la validación clínica y bibliográfica pendiente o con otra prioridad indicada por el usuario.

Los planos de IMG-000006 e IMG-000009 continúan pendientes en sus respectivos casos.

Antes de cualquier nueva incorporación:

1. Leer el contexto maestro y este handoff.
2. Comprobar estado Git.
3. Verificar archivos y namespaces reales.
4. Continuar desde el estado encontrado.