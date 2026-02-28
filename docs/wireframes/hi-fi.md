# Wireframes Hi‑Fi — Especificación visual y de interacción

## Propósito
Documento de especificación Hi‑Fi: tokens visuales, componentes, interacciones, accesibilidad y checklist de entrega para desarrollo.

## Sistema de diseño mínimo

### Paleta de colores (tokens)
- `--color-primary`: #C6FF3B (Lime / acento principal)
- `--color-accent-1`: #8A62FF (Morado)
- `--color-accent-2`: #FF5C8A (Rosa)
- `--color-accent-3`: #FFC857 (Amarillo)
- `--color-accent-4`: #3BD3C2 (Cian/Teal)
- `--bg-900`: #0F1417 (Fondo principal)
- `--bg-800`: #1A1E22 (Fondo secundario / header)
- `--panel`: #1F2326 (Paneles)
- `--surface`: #26292C (Surface cards)
- `--text-primary`: #EAF2F8 (Texto claro)
- `--muted`: #98A0A6 (Texto débil)

> Contrast notes: Asegurar contraste >= 4.5:1 para texto normal y >= 3:1 para texto grande; usar `--text-primary` sobre `--bg-900` o `--panel`.

### Tipografía
- Fuente sugerida: Inter (fallback: system-ui, -apple-system, Roboto).
- Escala recomendada:
  - H1: 28px / 36px line-height
  - H2: 20px / 28px
  - Body: 14px / 20px
  - Captions: 12px / 16px

### Espaciado y radii
- Espaciado base: 8px (scale: 4,8,16,24,32...)
- Border-radius estándar: 6px
- Elevaciones: sombra sutil para paneles: `0 1px 3px rgba(11,23,36,0.06)`

## Componentes clave (especificaciones)

### Botón primario
- Height: 40px; padding: 0 16px; border-radius: 6px; font-weight: 600.
- Estados: normal (`--color-primary`), hover (10% darker), pressed (scale 0.98), disabled (neutral-300, opacity 0.6).
- Microinteraction: transición `transform 120ms cubic-bezier(.2,.9,.3,1)`; ripple opcional.

### Input / Select
- Height: 40px; padding: 8px 12px; border: 1px solid `--neutral-300`.
- Estados: focus (outline 2px `--color-primary` with 12% alpha), error (border `--color-danger`).

### Tabla principal
- Row height: 40px; header height: 48px.
- Column padding: 12px.
- Alternancia de filas: `neutral-100` / `neutral-200` subtle.
- Acciones por fila: icon buttons con tooltip (hover) y foco keyboard.
- Soporte para selección múltiple y shortcuts (Shift/Ctrl).

### Panel de detalle
- Width: 320px; padding 16px; separación clara del contenido principal.
- Animación de entrada: slide-in desde la derecha 200ms ease-out.

## Interacciones y microinteracciones
- Duraciones: micro (120ms), normal (200ms), largo (320ms).
- Easing recomendado: `cubic-bezier(.2,.9,.3,1)` para clicks; `cubic-bezier(.16,.84,.24,1)` para entradas.
- Loading skeletons para tablas grandes: animación de shimmering 1.2s infinite.

## Accesibilidad (a11y)
- Contraste de texto mínimo 4.5:1.
- Todos los controles deben ser navegables con teclado y tener `aria-label` adecuados.
- Estados de carga y error deben anunciarse (aria-live) para lectores de pantalla.
- Evitar usar color como único indicador de estado (añadir iconos o texto).

## Activos y exportación
- Nombres de iconos: `ic-<nombre>-16|24|32.svg`.
- Imágenes: exportar a `assets/` en 1x y 2x; nombrado `screen-login@1x.png`, `screen-login@2x.png`.
- Tokens: exportar CSS variables y JSON para integrarlo en el repositorio.

## Handoff al equipo de desarrollo
- Entregar archivo Figma con:
  - Componentes diseñados y variantes (states).
  - Tokens exportados (color, tipo, espaciado).
  - Documento de especificaciones enlazado desde Figma.
- Checklist de merge:
  - [ ] Componentes en React/Flutter con props documentadas.
  - [ ] Tests visuales (snapshot) para tabla y botones.
  - [ ] Documentación de accesibilidad incluida.

## Checklist de entrega Hi‑Fi
- [ ] Paleta y tokens validados.
- [ ] Pantallas clave (Login, Dashboard, Transacciones) diseñadas a 1080px y responsive.
- [ ] Componentes con estados documentados.
- [ ] Prototipo clickable con flujos principales.
- [ ] Brief de animaciones y microinteracciones entregado.

---

Si quieres, puedo:
- Generar el archivo de tokens (`tokens.json` y `variables.css`).
- Crear un brief listo para importar en Figma con assets empaquetados.
- Implementar un componente React/Flutter de ejemplo (p. ej. `Table` o `Login`).
