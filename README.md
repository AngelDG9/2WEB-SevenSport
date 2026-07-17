# 2WEB-SevenSport
Web Template for SevenSport by 2WEB

## Reseñas de Google (Carrusel)

La sección de reseñas muestra 10 opiniones reales de clientes de Seven Sport extraídas de Google, implementadas como un carrusel automático.

### Estructura

- **HTML** (`index.html`): 10 tarjetas hardcodeadas dentro de un carrusel con flechas de navegación
- **CSS** (`estilos/estilos.css`): Estilos del carrusel al final del archivo, reutilizando la paleta de colores y patrones del resto de la web
- **JavaScript** (`index.html`, inline): Auto-scroll cada 8 segundos + navegación manual con flechas

### Funcionamiento

- Se muestran **3 reseñas** en desktop, **2 en tablet**, **1 en móvil**
- Las tarjetas reciben su ancho en píxeles dinámicamente via JS (`setCardWidths()`), garantizando que encajen perfectamente sin desbordarse ni cortarse
- `box-sizing: border-box` en las tarjetas asegura que padding y border se incluyen en el ancho calculado
- Las reseñas avanzan automáticamente cada **8 segundos** con loop infinito
- Flechas ❮/❯ a los lados permiten navegación manual (resetean el timer)
- Hover en las tarjetas aplica el efecto `translateY(-4px)` del resto de la web
- El subtítulo "Opiniones reales de nuestros usuarios en Google" está debajo del carrusel, discreto

### Estructura DOM del carrusel

```
.carrusel                  ← flex-row: [botón] [ventana] [botón]
  .carrusel-btn-izq        ← botón izquierdo (fuera del overflow)
  .carrusel-ventana        ← overflow:hidden — la "lupa" que enmarca las tarjetas
    .carrusel-pista        ← flex-row desplazado por transform translateX
      .tarjeta-resena × 10
  .carrusel-btn-der        ← botón derecho (fuera del overflow)
```

Los botones viven **fuera** del contenedor con `overflow:hidden`, por lo que no se cortan ni interfieren con el cálculo de ancho de las tarjetas.

### Estrellas

Las estrellas usan el carácter Unicode `★` (U+2605) con dos clases CSS:
- `.estrella.llena` → color `#f5a623` (naranja dorado), tamaño `1.35rem`
- `.estrella.vacia` → color `#d9d9d9` (gris claro), tamaño `1.35rem`

Siempre se renderizan 5 estrellas, con las vacías en gris para completar la puntuación. Esto es más consistente entre navegadores y sistemas operativos que el emoji ⭐.

### Reseñas incluidas

| Nombre | Estrellas |
|--------|-----------|
| Fabiola Martínez | ★★★★★ |
| Silvia Gaona | ★★★★★ |
| Francisco Manzano Obregón | ★★★★★ |
| Manuel Jiménez Ruiz | ★★★★★ |
| Andrea Ruiz Martín | ★★★★★ |
| piranha94 Galle | ★★★★★ |
| CRV | ★★★★★ |
| Fermín Aranda | ★★★★★ |
| Natalia Navas | ★★★★☆ |
| Cristina Gago | ★★★★★ |

### Diseño de las tarjetas

- **Fondo sección**: blanco (`var(--blanco)`) — eliminada la bandeja gris de fondo
- **Cabecera**: avatar pegado a la izquierda, nombre + estrellas a la derecha en fila (`display:flex`, `align-items:center`)
- **Estrellas**: `1.35rem`, color naranja dorado para rellenas, gris para vacías
- **Texto**: cursiva, color gris medio, alineado a la izquierda
- **Sombra**: suave `0 4px 20px rgba(0,0,0,0.07)`
- **Ancho**: calculado en píxeles por JS en base al ancho real de `.carrusel-ventana`
- **box-sizing**: `border-box` — el ancho asignado por JS incluye padding y border

### Detalles técnicos del JS

- `applyLayout()` se ejecuta dentro de `requestAnimationFrame` para asegurar que `ventana.offsetWidth` tenga el valor real del DOM pintado
- `goTo(index)` calcula `step = cardWidth + GAP` y desplaza la pista con `translateX`
- `GAP = 24` (px) coincide con `gap: 24px` del CSS — sin dependencia de rem
- `resize` usa `setTimeout(applyLayout, 100)` como debounce para no recalcular en cada pixel
- La transition del `transform` se gestiona por JS: se desactiva para resets instantáneos y se restaura en el siguiente `requestAnimationFrame`

### Para modificar reseñas

1. Edita las tarjetas `<article class="tarjeta-resena">` en `index.html`
2. Cambia el nombre en `<h3>`, las estrellas añadiendo/quitando `<span class="estrella llena">★</span>` o `<span class="estrella vacia">★</span>`, y el texto en `.resena-texto`
3. Actualiza el atributo `aria-label` del `.resena-estrellas` acorde (ej. `"4 de 5 estrellas"`)
4. Para cambiar las fotos de perfil, sustituye `imagenes/user.png` por la imagen descargada de Google Maps

### Nota sobre fotos

Google no expone URLs estables de fotos de perfil de reseñas sin API key. Actualmente se usa `imagenes/user.png` como avatar genérico. Para usar fotos reales, descárgalas manualmente de Google Maps y reemplaza el atributo `src` en cada tarjeta.