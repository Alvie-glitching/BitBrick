# BitBrick

Tablero de dibujo en cuadrícula. Cada cuadrado funciona como un píxel que se activa o desactiva, con colores configurables para ambos estados. El dibujo se exporta como imagen (PNG o JPG) o como datos de texto (TXT), y los archivos TXT se pueden volver a importar.

## Cómo abrirlo

| Forma | Cómo |
|---|---|
| En el navegador | <https://alvie-glitching.github.io/BitBrick/> (publicado con GitHub Pages desde la rama `main`) |
| Como archivo local | Descarga [`index.html`](index.html) y ábrelo con doble clic. No requiere instalación ni conexión a internet. |

BitBrick es un único archivo HTML, sin dependencias externas.

## Primeros pasos

1. Al abrirlo por primera vez aparece un lienzo en blanco de 32 × 32 cuadrados.
2. Ajusta **Ancho** y **Alto** (de 1 a 256) y presiona **Aplicar tamaño**. El dibujo existente se conserva desde la esquina superior izquierda.
3. Elige los colores de **Activado** y **Desactivado**.
4. Dibuja sobre el lienzo y exporta desde el panel **Exportar**.

Para ver un ejemplo, usa el botón **Ejemplo: fábrica** del panel **Importar TXT**.

## Herramientas

| Herramienta | Atajo | Comportamiento |
|---|---|---|
| Lápiz | `B` | Alterna: si el trazo empieza sobre un cuadrado desactivado, activa; si empieza sobre uno activado, desactiva. |
| Borrador | `E` | Desactiva los cuadrados. |
| Relleno | `F` | Activa el área contigua de cuadrados desactivados. |
| Clic derecho | — | Borra con cualquier herramienta. |
| Deshacer / Rehacer | `Ctrl+Z` / `Ctrl+Y` | Hasta 200 pasos. |

También están disponibles: **Invertir**, **Espejo ↔**, **Espejo ↕**, **Mover** (un cuadrado hacia cada lado) y **Limpiar**.

## Exportar

- **Nombre:** se usa en el nombre del archivo y en la cabecera del TXT.
- **Píxeles por cuadrado:** tamaño de cada cuadrado en la imagen exportada (de 1 a 64). El panel muestra las dimensiones resultantes.
- **Fondo transparente:** solo para PNG; los cuadrados desactivados quedan transparentes.
- **Incluir líneas de cuadrícula:** dibuja la cuadrícula en la imagen.
- **PNG**, **JPG** y **TXT** descargan el archivo. **Copiar TXT al portapapeles** copia el texto.

## Importar

- Sube un archivo `.txt` o pega el texto en el recuadro y presiona **Cargar texto pegado**.
- Si la cabecera trae nombre y dimensiones, se usan; si no, el tamaño se deduce de las filas.

## Formato TXT

```
# Ícono fabrica (32 x 32). X = silueta; . = fondo del recuadro.
................................
...X......X......X.....XXXX.....
```

- Las líneas que empiezan con `#` son comentarios. Si la cabecera sigue el formato `Ícono <nombre> (<ancho> x <alto>)`, se toman el nombre y las dimensiones.
- `X` = activado; `.` = desactivado. Al importar, cualquier carácter distinto de `.`, espacio, `0` o `_` cuenta como activado.

Ejemplo completo en [`ejemplos/fabrica.txt`](ejemplos/fabrica.txt).

## Guardado automático

El último dibujo, sus dimensiones, colores y nombre se guardan en el almacenamiento local de cada navegador y se recuperan al volver a abrir la página. No es un respaldo: borrar los datos del navegador lo elimina. Para conservar un dibujo, expórtalo en TXT.

## Estructura

```
index.html        Aplicación completa (HTML, CSS y JavaScript en un solo archivo)
ejemplos/         Dibujos de ejemplo en formato TXT
```

## Planificado

- Versión de escritorio para Windows (`.exe`).
