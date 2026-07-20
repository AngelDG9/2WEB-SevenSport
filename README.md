# 2WEB-SevenSport
Web Template for SevenSport by 2WEB

## Horarios — Panel glassmorphism en el Hero

La sección de horarios muestra los días y horas de apertura de Seven Sport en un panel con efecto glassmorphism integrado en el hero principal.

### Estructura

- **HTML** (`index.html`): Panel con `.horario-grid` — cada día es un `.horario-fila` con `.horario-dia` + `.horario-hora`
- **CSS** (`estilos/estilos.css`): Estilos de glassmorphism, grid de horarios, separador semana/fin de semana

### Diseño

- **Glassmorphism**: fondo `rgba(255,255,255,0.1)` + `backdrop-filter: blur(18px)` + borde blanco semitransparente
- **Rejilla día/hora**: cada fila es flex con `justify-content: space-between` — día a la izquierda, hora a la derecha
- **Separador visual**: línea sutil `rgba(255,255,255,0.15)` entre días laborables (L-V) y fin de semana (S-D)
- **Fin de semana destacado**: las horas del sábado y domingo usan `color: var(--naranja)` y `font-weight: 600`
- **Hover en filas**: fondo sutil `rgba(255,255,255,0.08)` al pasar el ratón
- **Hover en tarjeta**: `translateY(-4px)` + glow naranja suave
- **Ancho fijo**: `380px` en desktop, `100%` (max `420px`) en tablet/móvil

### Responsive

| Breakpoint | Comportamiento |
|---|---|
| ≥ 900px | Hero en fila: texto izquierda, tarjeta horarios derecha |
| ≤ 900px | Hero en columna: texto arriba, tarjeta centrada debajo (max 420px) |
| ≤ 650px | Padding reducido en la tarjeta |

### Para modificar horarios

1. Edita los `<span class="horario-hora">` en `index.html`
2. Para añadir/quitar días, duplica o elimina bloques `.horario-fila`
3. Usa la clase `.fin-de-semana` en las filas de sábado/domingo para el estilo naranja