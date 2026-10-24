---
id: FISIOOS-CURRENT-HANDOFF
title: FisioOS Current Handoff
type: Project Handoff
status: Active
version: 1.10
created: 2026-08-21
updated: 2026-10-24
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

`ae09b86 — docs(project): update handoff after treatment exercise and CASE-000007 work`

Último commit clínico confirmado y subido:

`1ffff83 — docs(clinical): add CASE-000007 and ultrasound image records`

Tras el push de ae09b86 se comprobó:

`## main...origin/main`

El árbol de trabajo estaba limpio y la rama sincronizada en esa comprobación.

Posteriormente se guardaron y revisaron cambios locales en:

- `knowledge/ultrasound/images/IMG-000022.md`
- `corpus/cases/shoulder/CASE-000007.md`

Ambos pasan documentalmente a versión 0.2 y mantienen Review.

Esta actualización del handoff acompaña ese bloque. Los cambios actuales todavía requieren comprobación final, staging explícito, commit y push.

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

La confirmación del plano de una imagen no se traslada automáticamente a otra captura.

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

En la revisión local del 2026-10-24, CASE-000007 e IMG-000022 pasan a Review 0.2.

IMG-000021, IMG-000023, IMG-000024 e IMG-000025 conservan Review 0.1 en el estado documentado.

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
| IMG-000022 | Espacio subcoracoideo derecho | 1,23 cm / 12,3 mm; longitudinal respecto al subescapular, confirmado por el explorador |
| IMG-000023 | Tendón del subescapular derecho | Patrón fibrilar local; plano pendiente |
| IMG-000024 | Espacio subacromial derecho | 1,05 cm / 10,5 mm; plano pendiente |
| IMG-000025 | Supraespinoso derecho | Área focal de menor ecogenicidad señalada; plano pendiente |

El explorador confirmó que IMG-000022 mide el espacio subcoracoideo y que IMG-000024 mide el espacio subacromial.

No se clasificaron las distancias como normales o disminuidas.

IMG-000025 no confirma por sí sola una rotura parcial ni cuantifica su extensión.

Los planos de IMG-000023, IMG-000024 e IMG-000025 siguen pendientes.

Las cinco fichas tienen `findings: []`.

No se crearon nuevos STR, FIND ni PAT.

### Revisión local del 2026-10-24

El explorador confirmó para IMG-000022:

- plano longitudinal respecto al tendón del subescapular;
- identificación de la apófisis coracoides;
- visualización del tendón pasando por debajo de ella.

La orientación longitudinal se refiere al eje del tendón, no a la línea de medición.

IMG-000022 pasa a versión 0.2:

- `plane: Longitudinal`;
- incorporación de STR-000203 y STR-000266 en `structures`;
- registro de la confirmación del explorador y su fecha;
- conservación de 1,23 cm / 12,3 mm;
- conservación de `findings: []` y Review;
- retirada del plano como dato pendiente.

CASE-000007 pasa a versión 0.2:

- incorpora la confirmación específica de IMG-000022;
- añade STR-000266 a sus estructuras relacionadas;
- actualiza los planos pendientes;
- conserva Review, las mediciones y las interpretaciones atribuidas al informe;
- registra el cambio en su historial de revisión.

La relación anatómica del tendón con la coracoides no se interpreta como compresión patológica.

No se establece conflicto subcoracoideo, causalidad del dolor ni indicación terapéutica.

La posición del brazo, la rotación y las referencias precisas de los cálipers siguen pendientes de documentación.

La confirmación del plano no estandariza por sí misma la medición ni equivale a validación clínica final.

Los cambios de ambas fichas se revisaron mediante diff. Su commit y push siguen pendientes en este punto del trabajo.

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
- Confirmar planos de IMG-000023, IMG-000024 e IMG-000025.
- Completar condiciones de adquisición y referencias de cálipers de IMG-000022 e IMG-000024.
- Completar URLs individuales cuando proceda.
- Mantener IMG-000022 en Review aunque su plano ya esté confirmado.

### CASE-000007

- Completar fechas y contexto clínico relevante.
- Registrar síntomas, movilidad, fuerza, objetivos y capacidad funcional.
- Documentar tratamiento aplicado y evolución si existen.
- Mantener separadas observaciones, información del explorador, informe e interpretación.
- No confirmar rotura o extensión únicamente desde IMG-000025.

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

La revisión del 2026-10-24 no crea entidades ni consume nuevos IDs.

Siguientes candidatos, siempre sujetos a comprobación del namespace real:

- CASE-000008.
- IMG-000026.
- STR-000269, solo si hace falta.
- FIND-000010, solo si está suficientemente sustentado.
- PAT-000015, solo si hace falta.

No se consideran reservados por aparecer en este documento.

## Verificación de bloques anteriores

### Incorporación de CASE-000007

- Lectura del contenido guardado de los seis archivos.
- Revisión documental frente a los textos validados.
- Staging de archivos explícitos.
- `git diff --cached --check` sin errores.
- Resumen staged: seis archivos y 1.080 líneas añadidas.
- Commit 1ffff83 completado.
- Push `dd1cd12..1ffff83 main -> main` correcto.
- Estado final limpio y sincronizado.

### Handoff anterior

- Commit ae09b86 completado.
- Push `1ffff83..ae09b86 main -> main` correcto.
- Estado final limpio y sincronizado.

Estas comprobaciones corresponden a esos bloques anteriores, no a los cambios locales posteriores.

## Verificación del bloque actual

Se han leído y revisado los cambios guardados de:

- IMG-000022, versión 0.2.
- CASE-000007, versión 0.2.

El diff muestra la confirmación anatómica y del plano, manteniendo Review y las mediciones originales.

Esta versión 1.10 del handoff todavía debe guardarse y revisarse.

Quedan pendientes:

- comprobación de espacios y formato mediante `git diff --check`;
- comprobación del estado Git y del alcance de los cambios;
- staging explícito de los archivos revisados;
- comprobación del contenido staged;
- commit;
- push;
- comprobación final de sincronización y árbol limpio.

No se afirma haber ejecutado un validador automático de YAML, IDs o enlaces.

No se afirma validación clínica definitiva ni revisión bibliográfica nueva durante esta actualización documental.

## Punto exacto de reanudación

Último commit confirmado y sincronizado:

`ae09b86`

Último caso incorporado y sincronizado:

CASE-000007 e IMG-000021–000025, mediante 1ffff83.

Trabajo local posterior:

- IMG-000022: Review 0.2, plano longitudinal respecto al subescapular confirmado.
- CASE-000007: Review 0.2, actualizado para reflejar esa confirmación.
- CURRENT_HANDOFF: actualización propuesta a versión 1.10.

Acción inmediata:

Guardar y revisar este handoff, completar las comprobaciones de los tres archivos y versionar y subir el bloque siguiendo el flujo de un comando cada vez.

No asumir commit ni push hasta comprobar sus resultados.

Después:

Resolver los planos pendientes y las condiciones de adquisición de forma controlada, o continuar con otra prioridad indicada por el usuario.

Antes de cualquier nueva incorporación:

1. Leer el contexto maestro y este handoff.
2. Comprobar estado Git.
3. Verificar archivos y namespaces reales.
4. Continuar desde el estado encontrado.