# Pre-parcial — Cine Arrabal

- **No toques `index.html`.** Todo se arregla en `estilos.css`.
- Los problemas puntuales están marcados en el CSS con su número, por ejemplo `/* [5] */`.
  Los puntos 1 a 4 no tienen marca: hay que recorrer la hoja entera.
- Así se tiene que ver al terminar: [teléfono](captura-mobile.png) · [compu](captura-desktop.png).

---

## Variables

### 1. Colores
Hay siete colores en hex, casi todos repetidos. Creá una variable en `:root` para cada uno y reemplazalos todos por `var()`.
El nombre dice **para qué se usa**, no qué color es: `--acento`, no `--rojo`.

### 2. Sombras
Hay dos `box-shadow` repetidos. Pasalos a `--sombra` y `--sombra-alta`.

### 3. Fuentes
Hay dos `font-family` repetidos. Pasalos a variables.
Pista: con una regla `h1, h2, h3 { … }` no hace falta repetirla en cada título.

## Unidades

### 4. De `px` a `rem`
`font-size`, `padding`, `margin`, `gap` y `max-width` pasan a `rem`. Para los espacios usá la escala `--s-*` que ya está en `:root`.
Bordes, `border-radius` y sombras **pueden quedar en `px`**.

### 5. `[5]` El hero
- **a)** El título mide `48px` siempre. Hacelo fluido con `clamp()`: nunca menos de `2rem`, nunca más de `3.5rem`, con el preferido en `rem + vw`.
- **b)** `height: 100vh` corta el botón en el teléfono. Son dos arreglos en una línea. No hace falta pantalla completa: con 60 alcanza.

## Mobile first

### 6. `[6]` La media query
Está al revés: usa `max-width`, en `px`. Reescribila mobile first:
- el estilo base, sin media query, es el del teléfono: una columna y la cabecera apilada;
- la media query usa `min-width: 48rem` y sólo **suma**.

## Estados (clase 4)

### 7. `[7]` Hover, orden y transiciones
- **a)** Los `:hover` están sueltos: en el teléfono se quedan pegados.
- **b)** Hay un `:active` que nunca se ve con el mouse. ¿Por qué?
- **c)** Hay `transition: all`. Nombrá sólo lo que cambia.

### 8. `[8]` Foco
- **a)** `outline: none` deja sin anillo a quien navega con Tab. Usá la pseudoclase correcta y un anillo de dos tonos.
  Agregá `--foco: #f2b632` y `--foco-contra: #2b2118`.
- **b)** Con el foco en "Comprar", que se marque la tarjeta entera de la película.

### 9. `[9]` 44 píxeles
Todo lo que se toca mide 44: la marca, los enlaces del menú y los botones. Agregá `--tocable: 44px`. Ojo con `height`.
El enlace del pie está dentro de un párrafo: agrandale el área tocable sin romper el renglón.

### 10. `[10]` Seleccionar por posición
Sin agregar clases al HTML:
- **a)** El primer párrafo de cada sección es la intro, más grande y gris. La regla existe pero no agarra nada. ¿Por qué?
- **b)** Cebrá los horarios: las filas pares van con el color de cebra.
- **c)** La primera fila es la próxima función: negrita y un `border-left` de `4px` con el color de acento.
- **d)** La última fila tiene doble línea abajo. Sacásela sólo a ella.

### Extra (si terminás antes)
Agregá al final la media query para quien pide menos movimiento.

---

## Cómo saber si está bien

- A 320px todo va en una columna y no hay scroll horizontal.
- Arrastrás el ancho de la ventana y el título del hero se agranda y se frena.
- Con Tab ves un anillo en todo; con click del mouse, no.
- Con Tab en "Comprar", la tarjeta entera se marca.
- Debajo del comentario de la consigna, `#` sólo aparece dentro de `:root`.
