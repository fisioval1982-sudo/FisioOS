# ASSET-NAMING-STANDARD

## Patrón general

`<region>_<joint-or-area>_<structure>_<side>_<view>_<variant>_vNN.<ext>`

## Ejemplo

`upper-limb_shoulder_scapula_right_posterior_master_v01.png`

## Valores de variante

- source
- master
- web
- preview
- thumbnail
- transparent
- labelled
- composite

## Reglas

1. Usar minúsculas.
2. Separar conceptos con guiones.
3. No usar espacios, tildes ni caracteres especiales.
4. Usar `right`, `left`, `bilateral` o `midline`.
5. La versión debe tener dos dígitos: `v01`.
6. Un cambio anatómico sustancial incrementa la versión.
7. Las variantes derivadas conservan la versión del activo maestro.
8. El identificador del activo vive en la ficha, no en el nombre del archivo.

## Ejemplos de escápula

- `upper-limb_shoulder_scapula_right_posterior_master_v01.png`
- `upper-limb_shoulder_scapula_right_anterior_web_v01.png`
- `upper-limb_shoulder_scapula_right_lateral_thumbnail_v01.png`
