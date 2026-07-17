# 2WEB-SevenSport
Web Template for SevenSport by 2WEB

## Reseñas de Google (Carrusel)

La sección de reseñas muestra 10 opiniones reales de clientes de Seven Sport extraídas de Google, implementadas como un carrusel automático.

### Estructura

- **HTML** (`index.html`): 10 tarjetas hardcodeadas dentro de un carrusel con flechas de navegación
- **CSS** (`estilos/estilos.css`): Estilos del carrusel al final del archivo, reutilizando la paleta de colores y patrones del resto de la web
- **JavaScript** (`index.html`, inline): Auto-scroll cada 5 segundos + navegación manual con flechas

### Funcionamiento

- Se muestran **3 reseñas** en desktop, **2 en tablet**, **1 en móvil**
- Las reseñas avanzan automáticamente cada 5 segundos con loop infinito
- Flechas ❮/❯ a los lados permiten navegación manual (resetean el timer)
- Hover en las tarjetas aplica el mismo efecto `translateY(-4px)` que el resto de la web

### Reseñas incluidas

| Nombre | Estrellas |
|--------|-----------|
| Fabiola Martínez | ⭐⭐⭐⭐⭐ |
| Silvia Gaona | ⭐⭐⭐⭐⭐ |
| Francisco Manzano Obregón | ⭐⭐⭐⭐⭐ |
| Manuel Jiménez Ruiz | ⭐⭐⭐⭐⭐ |
| Andrea Ruiz Martín | ⭐⭐⭐⭐⭐ |
| piranha94 Galle | ⭐⭐⭐⭐⭐ |
| CRV | ⭐⭐⭐⭐⭐ |
| Fermín Aranda | ⭐⭐⭐⭐⭐ |
| Natalia Navas | ⭐⭐⭐⭐ |
| Cristina Gago | ⭐⭐⭐⭐⭐ |

### Para modificar reseñas

1. Edita las tarjetas `<article class="tarjeta-resena">` en `index.html`
2. Cambia el nombre en `<h3>`, las estrellas en `.resena-estrellas` y el texto en `.resena-texto`
3. Para cambiar las fotos de perfil, sustituye `imagenes/user.png` por la imagen descargada de Google Maps

### Nota sobre fotos

Google no expone URLs estables de fotos de perfil de reseñas sin API key. Actualmente se usa `imagenes/user.png` como avatar genérico. Para usar fotos reales, descárgalas manualmente de Google Maps y reemplaza el atributo `src` en cada tarjeta.