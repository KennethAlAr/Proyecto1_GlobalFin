# Justificación de la Tecnología y Estrategia UI/UX
**Proyecto:** Aura - GlobalFin Bank

---

## 1. Justificación de la Tecnología para el Dashboard de Empleados

Para el desarrollo del Dashboard interno de empleados, que operará en un entorno B2B para sistemas Windows y macOS, la tecnología elegida es **JavaFX** por delante de .NET MAUI.

| Criterio de Evaluación | JavaFX (La elección recomendada) | .NET MAUI (La alternativa) |
| :--- | :--- | :--- |
| **Enfoque del Framework** | Orientado 100% a aplicaciones de Escritorio. | Orientado a ser multiplataforma ("Mobile-first" adaptado a escritorio). |
| **Separación Vista / Lógica** | Excelente. Usa FXML para maquetar, CSS para los estilos visuales, y Java para la lógica. | Muy buena. Usa XAML para la interfaz y C# para la lógica, pero no usa CSS estándar. |
| **Rendimiento con Datos Masivos** | Sobresaliente. Su componente TableView está optimizado para renderizar miles de filas financieras sin bloquear la interfaz. | Bueno, pero al ser una capa de abstracción sobre varios sistemas, puede sufrir ralentizaciones con tablas de datos extremas. |
| **Atajos de Teclado** | Manejo nativo y muy granular de eventos de teclado, esencial para este proyecto. | Funcional, pero su implementación en escritorio a veces hereda limitaciones de su enfoque móvil. |
| **Contexto del Equipo** | Curva de aprendizaje y tiempo de desarrollo mínimos, ya que el equipo lo conoce. | Requeriría que todo el equipo backend/frontend aprendiera C# y el ecosistema de Microsoft. |

**Conclusión:** La elección se basa en el perfil de los analistas financieros, que necesitan extrema rapidez, manejar enormes cantidades de datos en tablas y utilizar atajos de teclado constantemente. JavaFX es maduro, puramente orientado a escritorio y su `TableView` está altamente optimizado. Además, permite una separación estricta mediante FXML y CSS, y aprovecha los conocimientos previos del equipo, evitando retrasos en la formación.

---

## 2. Justificación de la Tecnología para la App Móvil B2C

Para la aplicación móvil de clientes (entorno B2C para iOS y Android), la tecnología seleccionada es **Flutter**, descartando React Native.

| Criterio de Evaluación | Flutter (La elección recomendada) | React Native (La alternativa) |
| :--- | :--- | :--- |
| **Rendimiento de Renderizado** | Sobresaliente. Usa su propio motor gráfico para dibujar cada píxel. Garantiza 60/120 fps. | Bueno. Usa un "puente" de JavaScript para invocar componentes nativos, pudiendo sufrir tirones. |
| **Ecosistema y Componentes** | Excelente. Catálogo gigantesco de widgets propios (Material/Cupertino) listos y estables. | Dependiente. Núcleo minimalista; depende de librerías de terceros que pueden dar problemas. |
| **Time-to-Market** | Rapidísimo. Un solo código garantiza funcionamiento exacto en iOS y Android. | Rápido. Comparte código, pero a veces requiere programar excepciones específicas por sistema. |
| **Accesibilidad (a11y)** | Accesibilidad y contraste integrados en el núcleo de sus widgets por defecto. | Buenas APIs, pero personalizar componentes complejos requiere más esfuerzo. |

**Conclusión:** El proyecto exige una interfaz muy personalizada y microinteracciones suaves. Flutter brilla al usar su propio motor gráfico, garantizando fluidez. Asegura consistencia visual en ambos sistemas operativos (iOS/Android) con un único código, acelerando el *time-to-market*. Su ecosistema maduro facilita cumplir con los requisitos de accesibilidad demandados por usuarios de todas las edades.

---

## 3. Resolución de Mitos (Respuestas al CEO)

### Sobre la Fase Low-Fi
> **Asunto:** Re: Optimización de tiempos y Fase Low-Fi

Comprendo la urgencia por avanzar, pero saltarnos la fase de Wireframes Low-Fi tendría el efecto contrario al deseado. El objetivo de estos bocetos no es hacer "dibujitos", sino plasmar el "modelo mental" del usuario; entender cómo esperan encontrar la información antes de escribir código. Si programamos directamente en el IDE y erramos en el flujo, el coste de refactorizar (backend y frontend) será de semanas. Corregir un boceto tiene un coste casi nulo. Además, esto nos permite aplicar la separación de capas: definimos la vista (UI) sin interferir en la lógica de negocio.

### Sobre el Impacto de la UI
> **Asunto:** Re: Impacto del Dashboard interno en el ROI

El sistema Back-end es el motor, pero la GUI es el volante. Un buen diseño no es cosmética, es productividad. En el "Caso Slack", revolucionaron su sector creando una interfaz que reducía la fricción. Actualmente, los empleados pierden horas por una mala jerarquía visual. Si mejoramos la jerarquía, la consistencia y optimizamos la navegación por teclado, reduciremos su carga cognitiva. Encontrarán datos más rápido y cometerán menos errores, lo que impacta positivamente en el ROI al ahorrar miles de horas laborables.

### Sobre la Tecnología Única
> **Asunto:** Re: Estrategia tecnológica para la App Móvil B2C

La idea de que "una tecnología sirve para siempre" es un mito que compromete el producto. JavaFX es excelente para B2B de escritorio, pero el entorno móvil B2C tiene reglas distintas. Los clientes exigen apps ligeras, nativas y con microinteracciones fluidas. Flutter está diseñado para este ecosistema, ofreciendo un rendimiento superior en móviles. Forzar JavaFX en móviles resultaría en una app pesada y anticuada, alejando a los clientes ganados con la fusión.

---

## 4. Justificación UI/UX y Wireframes

### Dashboard de Empleados (B2B)
* **Jerarquía Visual:** Estructura en disposición de "F" (menú lateral y cabecera superior) para reducir la carga cognitiva.
* **Navegación por Teclado:** Atajos visibles (ej. Ctrl+F, Alt+1) en botones y menús, vital para analistas financieros.
* **Gestión de Datos:** Área principal dedicada a una gran tabla para manejar información masiva de un vistazo.
* **Wireframe Low-Fi:** Tonos neutros. Menú vertical izquierdo (Inicio, Operaciones, Clientes, Informes), cabecera con buscador. Tres tarjetas de resumen superior y una gran tabla de datos central con paginación inferior. Estilo minimalista.

### App Móvil de Clientes (B2C)
* **Accesibilidad (a11y):** Tarjetas grandes y tipografía clara para destacar información clave (saldo) sin esfuerzo, ideal para todas las edades.
* **Ley de Fitts (Ergonomía):** Barra de navegación inferior y acciones rápidas en la "zona del pulgar" para uso con una sola mano.
* **Wireframe Low-Fi:** Pantalla de smartphone. Cabecera con saludo/menú. Bloque central grande para el saldo. Cuadrícula de tres botones circulares para "Acciones Rápidas". Lista inferior esquemática para últimos movimientos y una *Bottom Navigation Bar* con tres iconos. Diseño espaciado.