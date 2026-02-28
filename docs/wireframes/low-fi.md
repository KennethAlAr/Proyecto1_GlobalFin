# Wireframes Low‑Fi

## Propósito
Documento de referencia para los wireframes Low‑Fi: describir objetivos, puntos de validación y checklist para la revisión con stakeholders antes de pasar a Hi‑Fi.

## Archivos incluidos

- `docs/wireframes/login.svg` — pantalla de inicio de sesión.
- `docs/wireframes/dashboard.svg` — vista principal con menú lateral, área de resumen y tabla principal.
- `docs/wireframes/transactions.svg` — tabla de transacciones con filtros y listado de filas.

## Notas y objetivos por pantalla

### Login
- Objetivo: acceso rápido, recuperar credenciales.
- Elementos a validar:
  - Prioridad del campo `Email` → `Password` → `Iniciar sesión`.
  - Texto de ayuda y enlace "Olvidé mi contraseña" visible.
  - Flujo de errores (email inválido / password incorrecta).
  - Soporte para SSO (si aplica) y accesibilidad del foco del teclado.

### Dashboard
- Objetivo: ofrecer visión general y atajos a datos críticos.
- Elementos a validar:
  - Jerarquía visual entre el header, menú y área de contenido.
  - Colocación y visibilidad de filtros y búsqueda.
  - Panel de detalle contextualmente vinculado a la selección de la tabla.
  - Densidad de información en la tabla vs espacio para gráficos.

### Transacciones
- Objetivo: permitir búsqueda, filtrado y revisión de filas.
- Elementos a validar:
  - Columnas necesarias (ID, Fecha, Cliente, Monto, Estado).
  - Tipos de filtros (rango de fechas, selector de cliente, estado).
  - Acciones por fila (ver detalles, exportar, marcar como revisada).
  - Paginación vs scroll infinito (decidir por volumen de datos).

## Checklist de revisión (sesión de validación rápida — 30 min)
- [ ] ¿Las acciones primarias están en el lugar esperado?
- [ ] ¿Algún elemento confunde el flujo (p. ej. botones secundarios con peso visual igual)?
- [ ] ¿Faltan estados importantes (vacío, carga, error)?
- [ ] ¿Compatibilidad de atajos de teclado necesaria para usuarios power? (Sí/No)
- [ ] ¿Algún campo requiere validación adicional o ayuda contextual?

## Cómo usar estos SVG en Figma
1. Abrir Figma (web).
2. Crear un nuevo archivo y usar `File → Import` para subir los SVG.
3. Convertir elementos importados en vectores editables según sea necesario.
4. Iterar con stakeholders y anotar cambios (comentarios en Figma).

## Siguientes pasos tras validación Low‑Fi
- Generar tokens visuales (paleta, tipografías y espaciado).
- Diseñar pantallas Hi‑Fi en Figma basadas en decisiones tomadas aquí.
- Preparar prototipo interactivo de flujo crítico (login → dashboard → transacción).
