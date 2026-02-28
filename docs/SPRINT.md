# Sprint Inicial - Proyecto GlobalFin Bank

Este documento sintetiza la estrategia propuesta para el **Sprint Inicial** enfocado en modernizar las interfaces de GlobalFin y cumplir con los requisitos del caso práctico.

## 1. Concepción de la GUI y Enfoque UX

1. **Wireframes Low‑Fi**
   - Crear bocetos en blanco y negro que reflejen el modelo mental del usuario.
   - Herramientas sugeridas: Figma (web).
   - Priorizar la colocación de botones, tablas y flujos de navegación.
   - Beneficio: corregir errores de flujo sin escribir código.

2. **Diseño Visual (Hi‑Fi)**
   - Aplicar colores corporativos, tipografías y normas de accesibilidad (a11y).
   - Definir jerarquía visual y consistencia para el dashboard interno.
   - Resultado esperado: reducción de carga cognitiva y mejora de la productividad.

## 2. Selección Tecnológica

- **Dashboard B2B (Escritorio)**
  - Requisitos: tablas de gran volumen, atajos de teclado, separación entre vista y lógica.
  - Opciones: JavaFX vs .NET MAUI.  
    • JavaFX ofrece una arquitectura MVC clara y una buena presencia en plataformas Windows/Linux.

- **App Móvil B2C (Clientes)**
  - Requisitos: UX fluido, microinteracciones, lanzamiento rápido a tiendas.
  - Opciones: React Native vs Flutter.  
    • Compartir código para iOS/Android; elegir según experiencia del equipo.

- **Nota**: Desmitificar el uso de JavaFX Mobile; para B2C es mejor Flutter o React Native.

## 3. Entorno de Desarrollo y Prototipado Funcional

- **IDE**: IntelliJ IDEA Community Edition.
- **Instalación rápida** (Linux/development container):
  ```bash
  flatpak install flathub com.jetbrains.IntelliJ-IDEA-Community
  ```
  - Crear la primera ventana funcional de GlobalFin como prototipo (por ejemplo, un formulario de inicio de sesión o dashboard vacío).

## 4. Consultoría: Resolución de Mitos del CEO

- **Valor del prototipado**: iterar bocetos ahorra semanas de refactor en la fase de código.
- **Caso Slack**: un buen diseño de UI/tablas mejora la productividad y el ROI.
- **Tecnología única**: explicar por qué JavaFX Mobile no es adecuada para un B2C móvil y recomendar soluciones cross‑platform modernas.

---

Este Sprint documenta los pasos iniciales y puede ampliarse con más artefactos (wireframes, diagramas, prototipos) a medida que avanzamos.