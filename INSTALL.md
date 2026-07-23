# FISIOOS UPDATE 0009 — Anatomy Library v1

## Instalación

Copia el contenido de esta carpeta sobre la raíz del repositorio `FisioOS`.

La estructura está preparada para fusionarse con las carpetas ya existentes:

- `docs/`
- `templates/`
- `library/`
- `assets/`

No crees una carpeta adicional llamada `19_Anatomy_Library` ni `libraries`.

## Archivos gráficos incluidos

Se incluyen las tres imágenes aprobadas en cuatro variantes:

- `source/`: JPEG original recibido.
- `master/`: PNG con transparencia, a resolución nativa de 1254 × 1254 px.
- `web/`: PNG de 2048 × 2048 px.
- `previews/`: WEBP de 1200 × 1200 px.
- `thumbnails/`: PNG de 600 × 600 px.

## Advertencia de resolución

Los archivos fuente disponibles tienen 1254 × 1254 px. Las versiones de 2048 px son reescaladas y no añaden detalle anatómico real.

Para cerrar definitivamente la categoría `master`, conviene sustituir en el futuro los PNG de `master/` por versiones generadas o renderizadas a 3000 × 3000 px o más, manteniendo exactamente el mismo nombre.

## Commit recomendado

`Add Anatomy Library v1 and scapula master assets`
