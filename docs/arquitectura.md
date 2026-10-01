# Arquitectura del proyecto

## 1. Tipo de aplicación

UCB Campus es una **Single Page Interface (SPI) frontend** desarrollada con HTML, CSS y JavaScript Vanilla. La navegación se controla mediante el fragmento de URL (`location.hash`), por lo que las distintas vistas se renderizan sin solicitar páginas nuevas al servidor.

## 2. Capas

### Presentación — `index.html`

Contiene la estructura permanente de la aplicación: encabezado, navegación lateral, navegación móvil, área principal, diálogo reutilizable y contenedor de notificaciones visuales.

### Estilos — `css/styles.css`

Centraliza variables de diseño, componentes reutilizables, estados visuales y media queries. El diseño responde a escritorio, tablet y móvil.

### Lógica de aplicación — `js/app.js`

Gestiona:

- datos ficticios de asignaturas;
- estado temporal de la sesión;
- navegación por hash;
- generación de vistas;
- eventos de interfaz;
- validación de formularios y archivos;
- notificaciones;
- descargas de comprobantes de demostración;
- preferencias de apariencia.

### Persistencia

No existe base de datos. `localStorage` se utiliza únicamente para conservar la personalización visual de las asignaturas en el navegador. Los demás datos viven en memoria y se reinician al recargar.

## 3. Flujo de navegación

```text
Usuario
  ↓
index.html
  ↓
Cambio de hash (#inicio, #aulas, #horario...)
  ↓
router interno en app.js
  ↓
función de vista correspondiente
  ↓
renderizado en <main id="main">
  ↓
registro de eventos de la vista
```

## 4. Decisiones técnicas

### JavaScript Vanilla

No se utiliza React, Vue ni Angular porque el alcance actual no requiere un framework. Esto reduce dependencias, configuración y tamaño del proyecto, y permite concentrar la evaluación en fundamentos web.

### Sin backend

Las operaciones de pago, entrega de archivos, notas y asistencia son simulaciones locales. No existe comunicación con un servidor ni con sistemas institucionales.

### Hash routing

Se utiliza `location.hash` porque permite navegación interna y URLs representativas sin configurar rutas del lado del servidor.

## 5. Seguridad y alcance

El prototipo no debe recibir información personal real. No contiene credenciales, tokens ni claves privadas. Las funciones de pago y entrega no transmiten información fuera del navegador.

En una implementación real deberían añadirse autenticación, autorización por roles, validación del lado del servidor, protección CSRF/XSS según arquitectura, API segura, base de datos y almacenamiento controlado de archivos.

## 6. Escalabilidad futura

Si el proyecto aumenta considerablemente, `app.js` puede evolucionar hacia módulos separados por responsabilidad (`state`, `router`, `views`, `services`, `utils`). En el prototipo actual se mantiene un único archivo de aplicación para evitar complejidad innecesaria y conservar compatibilidad al abrir el proyecto directamente desde el sistema de archivos.
