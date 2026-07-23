# 2WEB-SevenSport

**Web template para Seven Sport — gimnasio en Jerez de la Frontera, Cádiz.**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Leaflet](https://img.shields.io/badge/Leaflet-199900?style=flat&logo=leaflet&logoColor=white)

© 2026 2WEB Project

---

## Descripción

Seven Sport es la web de un gimnasio localizado en Jerez de la Frontera (Cádiz). El proyecto es una **página estática** compuesta por dos archivos HTML, un único archivo CSS global y JavaScript vanilla sin frameworks ni herramientas de build. Diseñada como single-page con navegación por anclas, incluye también un formulario de inscripción en una segunda página.

**Características principales:**

- Diseño responsive con menú hamburguesa para móvil
- Efecto glassmorphism en la tarjeta de horarios
- Carrusel automático de reseñas de Google
- Mapa interactivo con Leaflet.js y OpenStreetMap
- Formulario de inscripción con campos dinámicos
- Tienda online con 6 productos

---

## Estructura del proyecto

```
2WEB-SevenSport/
├── index.html                    → Página principal (todas las secciones)
├── cuestionario.html             → Formulario de inscripción
├── estilos/
│   └── estilos.css               → Estilos globales (1250+ líneas)
├── imagenes/
│   ├── logosv_final.png          → Logo de Seven Sport
│   ├── 7.png                     → Favicon
│   ├── giphy.gif                 → GIF animado de fondo del hero
│   ├── menu hamburguesa.png      → Icono del menú hamburguesa (móvil)
│   ├── pesas.jpg                 → Imagen: Entrenamiento Personal
│   ├── pesas2.jpg                → Imagen: Área de Pesas
│   ├── maquinas.jpg              → Imagen: Zona de Cardio
│   ├── 100-whey-gold-standard-5-lb-23kg.png  → Producto: Proteína Whey
│   ├── Platinum_Creatine_Muscletech_Grape_Freeze.png → Producto: Creatina
│   ├── 10614_211e5ee84f-13343-001-onesize-2-1350x0.png → Producto: BCAA
│   ├── 71wJNhcXinL._AC_UF8941000_QL80_.png  → Producto: Shaker
│   ├── camiseta.png              → Producto: Camiseta Deportiva
│   ├── guantes-de-gimnasia.png   → Producto: Guantes Fitness
│   ├── user.png                  → Avatar genérico para reseñas
│   ├── fb.png                    → Icono Facebook
│   ├── x.png                     → Icono Twitter/X
│   └── ig.png                    → Icono Instagram
└── README.md
```

---

## Tecnologías utilizadas

| Tecnología | Versión | Uso |
|---|---|---|
| **HTML5** | Semántico | Estructura de las dos páginas (`<header>`, `<section>`, `<article>`, `<nav>`, `<footer>`) |
| **CSS3** | — | Estilos globales: variables CSS, flexbox, grid, glassmorphism, `clamp()`, `min()`, `calc()`, responsive media queries |
| **JavaScript** | Vanilla (ES5 compatible) | Carrusel de reseñas, menú hamburguesa, mapa Leaflet |
| **Leaflet.js** | 1.9.4 | Mapa interactivo con OpenStreetMap y marker del gimnasio |
| **Google Fonts** | — | Tipografía Inter (cargada vía CSS `font-family`) |

> **Nota:** El proyecto no requiere npm, Node.js, ni ningún sistema de build. Solo abre `index.html` en un navegador.

---

## Secciones de la web

### Header / Navegación

- **Header sticky** con gradiente lineal (tonos rojo-naranja) que se mantiene fijo al hacer scroll
- Logo enlazado al inicio + nombre "Seven Sport" con eslogan
- **Menú hamburguesa** visible en pantallas ≤ 768px, con panel desplegable oscuro
- 7 enlaces de navegación: Inicio, Servicios, Tarifas, Tienda, FAQ, Políticas, ¡Únete ya!
- Los enlaces de "¡Únete ya!" llevan directamente al formulario de inscripción

### Hero / Inicio (`#inicio`)

- **GIF animado** de fondo (`giphy.gif`) con gradiente oscuro superpuesto
- Texto principal: titular, subtítulo y botón CTA "Únete hoy"
- **Tarjeta de horarios** con efecto glassmorphism:
  - Fondo semitransparente + `backdrop-filter: blur(18px)`
  - Horario de lunes a viernes: 7:00 – 23:00
  - Sábado: 9:00 – 14:00 / Domingo: 10:00 – 14:00
  - Separador visual entre días laborables y fin de semana
  - Fin de semana destacado en color naranja

### Servicios (`#servicios`)

Tres tarjetas en grid responsive:

| Servicio | Descripción |
|---|---|
| Entrenamiento Personal | Rutinas individuales con seguimiento profesional |
| Área de Pesas | Equipamiento completo para fuerza y resistencia |
| Zona de Cardio | Cintas, bicicletas y máquinas funcionales |

### Tarifas (`#tarifas`)

Dos planes en grid de 2 columnas:

| Plan | Precio | Incluye |
|---|---|---|
| **Mensualidad** | 22€ / mes | Acceso a todas las instalaciones |
| **Anual** | 264€ / año | Acceso completo + batidos de proteínas incluidos |

### Tienda (`#tienda`)

6 productos en grid responsive con imagen, descripción, precio y botón "Comprar":

| Producto | Precio |
|---|---|
| Proteína Whey | 39,99€ |
| Creatina Monohidrato | 24,99€ |
| BCAA 2:1:1 | 29,99€ |
| Shaker Seven Sport | 9,99€ |
| Camiseta Deportiva | 19,99€ |
| Guantes Fitness | 14,99€ |

### Reseñas de Google (`#resenas`)

- **Carrusel automático** con 10 opiniones reales de clientes
- Auto-scroll cada **8 segundos** con loop infinito
- Navegación manual con flechas izquierda/derecha
- **3 reseñas visibles** en desktop, **2 en tablet** (≤900px), **1 en móvil** (≤650px)
- Estrellas CSS con Unicode `★` (U+2605): naranja dorado para llenas, gris para vacías
- Avatar genérico (`user.png`) — Google no expone URLs estables de fotos sin API key

### Contacto (`#contacto`)

- **Información:** dirección (Bda El Rocío, Jerez), teléfono, email
- **Mapa interactivo** con Leaflet.js:
  - Coordenadas: `36.689681, -6.107342`
  - Tiles de OpenStreetMap
  - Marker con popup "¡Nuestro Gimnasio!"
- **Formulario de opiniones:** nombre, email, valoración (1-5), mensaje

### FAQ (`#faq`)

4 preguntas frecuentes en grid de 2 columnas (desktop):

1. ¿Cómo me inscribo en Seven Sport?
2. ¿Qué incluye la membresía?
3. ¿Puedo cambiar de plan más adelante?
4. ¿Cuáles son los horarios del gimnasio?

### Políticas (`#politicas`)

Dos tarjetas lado a lado:

- **Política de privacidad:** recopilación de datos, uso limitado, protección normativa
- **Términos de uso:** normas de seguridad, higiene, responsabilidad

### Redes sociales

Enlaces con iconos a las redes oficiales de Seven Sport:

- [Facebook](https://www.facebook.com/p/Seven-Sport-100051161697094/)
- [Twitter/X](https://x.com/SevenSport1)
- [Instagram](https://www.instagram.com/sevensportgym/)

### Footer

Crédito: `Seven Sport © 2026 · 2WEB Project`

---

## Cuestionario de inscripción

Página separada (`cuestionario.html`) con formulario completo:

| Campo | Tipo | Validación |
|---|---|---|
| Nombre completo | Texto | `required` |
| Edad | Número | `min="14"` `max="100"` `required` |
| Correo electrónico | Email | `required` |
| Teléfono | Tel | `required` |
| Objetivo | Radio buttons | 8 opciones (Perder peso, Ganar músculo, Mantenerse en forma, Aumentar fuerza, Mejorar resistencia, Preparar competición, Rehabilitación, Mejorar salud) |
| Nivel de experiencia | Select | Principiante / Intermedio / Avanzado |
| Barra de experiencia | Range (0-10) | Se muestra solo al seleccionar nivel |
| Días disponibles | Checkboxes | Lunes a Sábado |
| Horario preferido | Radio buttons | Mañana / Tarde |
| Lesiones/enfermedades | Textarea | Opcional |
| Comentarios | Textarea | Opcional |

**Funcionalidad JS:** la barra de valoración de experiencia se muestra/oculta dinámicamente al seleccionar un nivel en el desplegable.

---

## Diseño y estética

### Paleta de colores (CSS Variables)

```css
--naranja:    #f15a29;   /* Color principal, acentos, botones */
--gris-oscuro: #2b2b2b;  /* Texto principal */
--gris-claro:  #f4f4f4;  /* Fondo de página */
--gris-medio:  #7a7a7a;  /* Texto secundario */
--blanco:      #ffffff;  /* Fondo de tarjetas */
--sombra:      0 16px 40px rgba(0, 0, 0, 0.12);
```

### Efectos visuales

- **Glassmorphism:** tarjeta de horarios con `background: rgba(255,255,255,0.1)`, `backdrop-filter: blur(18px)` y borde semitransparente
- **Hover en tarjetas:** `translateY(-4px)` + sombra suave en todas las tarjetas
- **Gradientes:** header (lineal rojo-naranja), botones submit (135deg naranja), hero (overlay oscuro)
- **Transiciones:** `0.2s ease` en la mayoría de interacciones

### Componentes reutilizables

- `.contenedor` — ancho máximo 1120px centrado
- `.tarjeta` / `.tarjeta-servicio` / `.tarjeta-tarifa` / `.tarjeta-producto` — fondo blanco, border-radius 18px, sombra
- `.boton` / `.boton-principal` / `.boton-secundario` — botones redondeados (border-radius 999px)
- `.seccion` — padding vertical 4rem
- `.rejilla` / `.columna` — grid responsive con `repeat(auto-fit, minmax(280px, 1fr))`

---

## Responsive Design

### Breakpoints

| Breakpoint | Comportamiento |
|---|---|
| **≥ 900px** | Layout desktop: grid multi-columna, header en fila, nav horizontal |
| **≤ 900px** | Layout tablet: grids a 1 columna, header en columna, nav centrado |
| **≤ 768px** | **Menú hamburguesa**: nav oculto, botón hamburguesa visible, panel desplegable oscuro |
| **≤ 720px** | Formularios: radio/checkbox groups a 1 columna, padding reducido |
| **≤ 650px** | Hero: padding reducido, tarjeta horarios width 100% max 420px, carrusel 1 tarjeta visible |

### Comportamiento por sección

| Sección | Desktop | Tablet/Móvil |
|---|---|---|
| Header | Logo + nav en fila | Logo + hamburguesa, nav desplegable |
| Hero | Texto izquierda + tarjeta derecha | Texto arriba + tarjeta centrada abajo |
| Servicios | 3 columnas | 1 columna |
| Tarifas | 2 columnas | 1 columna |
| Tienda | 3 columnas | 1 columna |
| Reseñas | 3 tarjetas visibles | 2 (≤900px) / 1 (≤650px) |
| Contacto | Info + mapa izquierda, formulario derecha | Columna vertical |
| FAQ / Políticas | 2 columnas | 1 columna |

---

## Cómo ejecutar

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/AngelDG9/2WEB-SevenSport.git
   ```
2. Abrir `index.html` directamente en un navegador

> **No se necesita servidor local.** Los tiles de OpenStreetMap y el script de Leaflet se cargan vía CDN. El único requisito es conexión a internet para el mapa.

---

## Guía de modificación

### Horarios

1. Editar los `<span class="horario-hora">` en `index.html` (dentro de `#inicio`)
2. Para añadir/quitar días: duplicar o eliminar bloques `.horario-fila`
3. Usar la clase `.fin-de-semana` en filas de sábado/domingo para el estilo naranja

### Reseñas

1. Editar las tarjetas `<article class="tarjeta-resena">` en `index.html` (dentro de `#resenas`)
2. Cambiar nombre en `<h3>`, texto en `.resena-texto`
3. Modificar estrellas: añadir/quitando `<span class="estrella llena">★</span>` o `<span class="estrella vacia">★</span>`
4. Actualizar el `aria-label` de `.resena-estrellas` (ej. `"4 de 5 estrellas"`)

### Productos de la tienda

1. Editar `<article class="tarjeta tarjeta-producto">` en `index.html` (dentro de `#tienda`)
2. Cambiar imagen (`src`), nombre, descripción y precio (`.precio`)

### Estilos y colores

1. Modificar variables CSS en `:root` al inicio de `estilos/estilos.css`
2. Cambiar `--naranja` para un color de acento diferente
3. Ajustar `--sombra` para sombras más suaves o intensas

### Mapa

1. Coordenadas en `index.html`: cambiar `setView([lat, lng], zoom)` y `L.marker([lat, lng])`
2. Tile layer por defecto: OpenStreetMap (sin API key)

---

## Créditos y licencia

- **Desarrollado por:** [2WEB Project](https://github.com/AngelDG9) — © 2026
- **Datos de reseñas:** opiniones reales extraídas de Google Maps del perfil de Seven Sport
- **Imágenes de productos:** fuentes públicas
- **Mapa:** [OpenStreetMap](https://www.openstreetmap.org/) vía [Leaflet.js](https://leafletjs.com/) (licencia BSD-2-Clause)
- **Iconos redes sociales:** imágenes propias
