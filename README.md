# UCB Campus — Prototipo Frontend

Prototipo académico de una interfaz universitaria que centraliza consultas y flujos inspirados en SIANN y LMS. El proyecto permite explorar aulas, horario, notas, pagos, tareas, notificaciones, perfil y una vista docente usando únicamente datos ficticios.

> **Importante:** este repositorio es una demostración académica. No se conecta a SIANN, LMS, bancos, bases de datos ni servicios institucionales reales.

## Objetivo

Demostrar una propuesta de experiencia de usuario para un campus universitario, priorizando navegación clara, diseño responsive, accesibilidad básica y estados comprensibles para estudiantes y docentes.

## Tecnologías

- HTML5 semántico
- CSS3 responsive
- JavaScript Vanilla (ES6+)
- Web Storage (`localStorage`) para preferencias visuales locales
- Hash routing para navegación sin backend

## Funcionalidades

- Inicio con accesos rápidos y pendientes.
- Aulas virtuales y detalle de asignaturas.
- Horario semanal.
- Consulta simulada de notas.
- Flujo de pagos de demostración.
- Entrega local simulada de archivos con validaciones.
- Notificaciones de actividades y pagos pendientes.
- Perfil editable con datos ficticios.
- Vista docente para asistencia, notas y personalización de asignaturas.
- Diseño adaptable para escritorio y dispositivos móviles.
- Consideraciones de accesibilidad: foco visible, enlace para saltar al contenido, etiquetas y atributos ARIA.

## Estructura

```text
ucb-campus/
├── index.html
├── README.md
├── .gitignore
├── css/
│   └── styles.css
├── js/
│   └── app.js
└── docs/
    └── arquitectura.md
```

La estructura es deliberadamente simple: el proyecto es un prototipo frontend pequeño y no necesita un framework ni un proceso de compilación para cumplir su objetivo.

## Ejecución

### Opción 1 — directa

Abre `index.html` en un navegador moderno.

### Opción 2 — servidor local

Puedes usar la extensión **Live Server** de VS Code o cualquier servidor HTTP local. No se requieren dependencias.

## Arquitectura

El proyecto sigue una arquitectura frontend simple por capas:

1. **Presentación:** `index.html` define la estructura base.
2. **Estilos:** `css/styles.css` contiene sistema visual, componentes y reglas responsive.
3. **Aplicación:** `js/app.js` contiene estado local, navegación, renderizado, validaciones e interacciones.
4. **Persistencia local:** `localStorage` conserva únicamente la apariencia personalizada de las asignaturas.

Consulta [`docs/arquitectura.md`](docs/arquitectura.md) para más detalles.

## Buenas prácticas aplicadas

- Separación de HTML, CSS y JavaScript.
- Uso de `'use strict'`.
- Escape de contenido dinámico antes de insertarlo en HTML cuando corresponde.
- Validación de archivos y notas antes de modificar el estado de la interfaz.
- Estados de demostración claramente identificados.
- Diseño mobile-first/responsive mediante media queries.
- Uso de variables CSS para mantener consistencia visual.
- Navegación accesible mediante teclado y foco visible.
- No se almacenan credenciales ni datos sensibles.
- No se incluyen secretos, tokens o claves de API.

## Limitaciones

Al ser un proyecto exclusivamente frontend:

- Los datos se reinician al recargar la página, excepto las preferencias visuales guardadas en `localStorage`.
- Las entregas no suben archivos a un servidor.
- Los pagos no realizan transacciones reales.
- No existe autenticación real.
- No existe una base de datos.
- No existe integración real con SIANN o LMS.

Estas limitaciones son intencionales y forman parte del alcance del prototipo.

## Posibles mejoras futuras

Si el proyecto evolucionara a un sistema real, el siguiente paso sería incorporar una API backend, autenticación, persistencia en base de datos, almacenamiento seguro de archivos, autorización por roles e integración con servicios institucionales.

## Autoría

Proyecto académico desarrollado con fines educativos.
