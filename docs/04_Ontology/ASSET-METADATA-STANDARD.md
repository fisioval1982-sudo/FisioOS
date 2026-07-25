# ASSET-METADATA-STANDARD

## Campos mínimos

- id
- title
- type
- status
- version
- library
- region
- structure
- side
- view
- projection
- layer
- asset_role
- asset_origin
- source
- license
- clinical_status
- visual_status
- publication_status
- prompt_master
- prompt_version
- parent_asset
- derived_assets
- file_source
- file_master
- file_web
- file_preview
- file_thumbnail
- approved_by
- approval_date
- anatomical_notes

## Campos condicionales

Para masters anatómicos y sus derivados, cuando apliquen:

- creation_history
- geometry_family
- geometry_status
- native_resolution
- export_resolution
- resolution_type
- known_limitations

## Reglas de representación

- `status` representa el estado de aprobación o ciclo de vida; no codifica limitaciones técnicas.
- `known_limitations` contiene una lista de limitaciones que no invalidan la aprobación.
- Las referencias internas en YAML usan IDs planos, nunca wikilinks.
- Los wikilinks se reservan para el cuerpo Markdown.
- `native_resolution` y `export_resolution` usan `WIDTHxHEIGHT` con `x` ASCII.
- Un archivo reescalado debe usar `resolution_type: upscaled` y nunca declararse como master nativo.
- Las vistas aprobadas de una misma geometría comparten un único `geometry_family`.

## Estados independientes

`status` representa el estado global.

Los campos siguientes permiten separar validaciones:

- `clinical_status`
- `visual_status`
- `publication_status`

## Valores recomendados

### asset_role

- master_base
- derived_structure
- composite
- overlay
- publication_asset

### asset_origin

- approved_master
- derived_asset
- external_source

### creation_history

Procedencia histórica opcional y estructurada:

```yaml
creation_history:
  initial_generation_method: AI-assisted
  anatomical_review_status: approved
```

La historia de creación no sustituye a `source`, que identifica la colección o institución canónica.

### geometry_status

- unlocked
- locked

### resolution_type

- native
- upscaled

### projection

- orthographic
- perspective
- oblique
- sectional

### publication_status

- Internal
- Ready
- Published
- Deprecated

## Ejemplo de master anatómico aprobado

```yaml
status: Approved
asset_origin: approved_master
source: FisioForYou Anatomy Library
library: LIBRARY-000001
geometry_family: scapula_right_master_v1
geometry_status: locked
native_resolution: 1254x1254
export_resolution: 1254x1254
resolution_type: native
known_limitations:
  - High-resolution native master is pending.
```
