# Escápula derecha — activos físicos

## Carpetas

- `source/`: archivos originales recibidos.
- `master/`: PNG RGBA transparente a resolución nativa.
- `web/`: PNG de 2048 px.
- `previews/`: WEBP de 1200 px.
- `thumbnails/`: PNG de 600 px.

## Familia maestra aprobada

Los masters canónicos activos son:

- posterior `v02`;
- anterior `v02`;
- lateral `v02`;
- superior `v01`.

Los cuatro archivos tienen 1254 × 1254 px, fondo blanco y no contienen canal alfa. Se conservan exactamente como fueron suministrados, sin recomprimir ni limpiar el fondo.

Los masters y derivados `v01` anteriores se mantienen como historial. Los derivados web, preview y thumbnail de `v01` no deben asociarse a los masters activos `v02`.

## Sustitución futura

Cuando existan versiones de 3000 × 3000 px o superiores:

1. crear una nueva versión sin sobrescribir el master aprobado;
2. regenerar web, preview y thumbnail;
3. actualizar la limitación de resolución en las fichas;
4. incrementar versión solo si cambia la anatomía o el estilo.
