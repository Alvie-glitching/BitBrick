# BitBrick

Tablero de dibujo en cuadrícula. Cada cuadrado funciona como un píxel que se activa o desactiva, con colores configurables para ambos estados. El dibujo se exporta como imagen (PNG o JPG) o como datos de texto (TXT).

## Uso

- **En el navegador:** abre la versión publicada en GitHub Pages (ver más abajo), o descarga `index.html` y ábrelo con doble clic. No requiere instalación ni conexión a internet.
- **Dibujar:** el lápiz alterna; si el trazo empieza sobre un cuadrado activado, lo desactiva. Clic derecho siempre borra.
- **Atajos:** `B` lápiz, `E` borrador, `F` relleno, `Ctrl+Z` deshacer, `Ctrl+Y` rehacer.

## Funciones

- Superficie configurable de 1×1 a 256×256 cuadrados.
- Colores de activado y desactivado; cuadrícula visible u oculta.
- Lápiz, borrador, relleno, invertir, espejo horizontal y vertical, desplazar.
- Exportación PNG (con fondo transparente opcional) y JPG, con tamaño de píxel configurable.
- Exportación e importación TXT.

## Formato TXT

```
# Ícono fabrica (32 x 32). X = silueta; . = fondo del recuadro.
................................
...X......X......X.....XXXX.....
```

- Las líneas que empiezan con `#` son comentarios. Si la cabecera sigue el formato `Ícono <nombre> (<ancho> x <alto>)`, se usan el nombre y las dimensiones.
- `X` = activado; `.` = desactivado. Al importar, cualquier carácter distinto de `.`, espacio, `0` o `_` cuenta como activado.

Hay un ejemplo en [`ejemplos/fabrica.txt`](ejemplos/fabrica.txt).

## Estructura

```
index.html        Aplicación completa (HTML, CSS y JavaScript en un solo archivo)
ejemplos/         Dibujos de ejemplo en formato TXT
```
