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
- source
- generation_method
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
- limitations

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

### generation_method

- generated
- edited
- photographed
- scanned
- rendered
- manually_illustrated

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
