# QA escápula derecha — familia multivista v1

## Alcance

Comprobación compartida de los masters aprobados posterior, anterior, lateral y superior agrupados en [[ASSET-000005]].

## Clinical QA

- [x] Estructura y lateridad declaradas como escápula derecha.
- [x] Las cuatro vistas requeridas están presentes.
- [x] Pablo Salvador Coloma consta como responsable de la aprobación clínica.
- [x] No se ha regenerado, redibujado, reflejado ni modificado la anatomía.

Codex no emite una aprobación clínica independiente.

## Technical QA

- [x] Cuatro archivos PNG legibles.
- [x] Dimensiones reales registradas: 1254 × 1254 px en las cuatro vistas.
- [x] Rutas y nombres conformes con `ASSET-NAMING-STANDARD`.
- [x] Prompts archivados para las cuatro vistas.

## Metadata QA

- [x] Las cuatro vistas usan `geometry_family: scapula_right_master_v1`.
- [x] El registro multivista usa la misma familia geométrica.
- [x] Los IDs de metadatos son únicos.
- [x] Las referencias YAML normalizadas usan IDs planos.
- [x] Las referencias de imagen resuelven a archivos existentes.
- [x] Las referencias Markdown comprobadas resuelven.

## Image QA

- [x] Lienzo cuadrado uniforme.
- [x] Color óseo y fondo blanco coherentes.
- [x] Sin texto ni marcas de agua detectables.
- [x] Los cuatro originales se conservaron byte por byte como masters.
- [x] SHA-256 verificado contra cada adjunto suministrado.
- [x] Ningún PNG fue modificado por la normalización de metadatos.

La revisión de halos en transparencia no aplica: los PNG suministrados no contienen canal alfa.

## Resultado

**Passed with limitations**.

Limitaciones:

- los masters no son nativos de 3000 × 3000 px;
- no se generaron derivados web, preview ni thumbnail para esta familia aprobada;
- los derivados `v01` preexistentes de posterior, anterior y lateral no corresponden a los nuevos masters `v02`.
