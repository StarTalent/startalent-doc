# Documentación de la Organización del Proyecto y Flujo de Trabajo

## Resumen

En este documento se describe la organización del proyecto y el flujo de trabajo adoptado para nuestro proceso de desarrollo. Hemos personalizado la plantilla Kanban predeterminada de GitHub para que se alinee mejor con las necesidades de nuestro equipo, mejorar la visibilidad de las tareas y proporcionar un control más granular sobre el ciclo de vida del desarrollo. Además, los cambios nos permiten una mejor priorización, estimación y seguimiento del progreso, lo cual es crucial a medida que el proyecto crece y se involucran más desarrolladores.

---

## Fases del Tablero Kanban y Justificación

Hemos personalizado el tablero Kanban en fases distintas para proporcionar claridad y enfoque sobre el estado de las tareas a lo largo del ciclo de desarrollo. Cada fase tiene un color asociado y un límite para evitar cuellos de botella y mantener un flujo de trabajo manejable.

### 1. Backlog

**Color:** Verde
**Límite:** Sin límite

- **Descripción:** El backlog es una reserva de todas las tareas identificadas que aún no están priorizadas ni iniciadas.
- **Justificación:** Mantener el backlog sin límite permite registrar todas las ideas y características potenciales sin restringir el alcance del trabajo del equipo. Sin embargo, en equipo de deben revisar y priorizar regularmente los elementos para los siguientes pasos.

### 2. Ready

**Color:** Azul
**Límite:** 6 elementos

- **Descripción:** Esta fase contiene tareas que están completamente definidas y listas para ser asignadas a cada desarrollador. Todos los requisitos y dependencias han sido clarificados.
- **Justificación:** Limitar esta columna a 6 elementos asegura que solo un número razonable de tareas estén preparadas para el equipo, evitando que se acumulen demasiadas prioridades al mismo tiempo.

### 3. In Progress

**Color:** Amarillo
**Límite:** 4 elementos

- **Descripción:** Tareas en las que los programadores está trabajando activamente.
- **Justificación:** El límite de 4 elementos se establece considerando que contamos con dos desarrolladores. Esto asegura el enfoque en completar tareas en lugar de comenzar muchas tareas al mismo tiempo, lo que podría reducir la productividad e incrementar el cambio de contexto.

### 4. In Review

**Color:** Morado
**Límite:** 5 elementos

- **Descripción:** Tareas completadas que están siendo sometidas a revisión de código, pruebas o verificaciones de calidad.
- **Justificación:** Permitimos hasta 5 tareas en revisión para proporcionar flexibilidad en la revisión por pares sin causar retrasos o tiempos de espera para nuevas tareas. También asegura que varios elementos puedan ser revisados simultáneamente sin causar cuellos de botella.

### 5. Documentation

**Color:** Gris
**Límite:** 2 elementos

- **Descripción:** Tareas dedicadas a escribir o actualizar la documentación técnica, manuales de usuario o descripciones del proceso de desarrollo.
- **Justificación:** La documentación es importante para mantener la claridad, pero limitamos esta fase a 2 elementos para asegurar que no consuma demasiado tiempo. Los desarrolladores pueden alternar entre el desarrollo y la documentación según sea necesario.

### 6. Ready for Testing

**Color:** Naranja
**Límite:** 2 elementos

- **Descripción:** Tareas que han sido desarrolladas y están listas para ser probadas.
- **Justificación:** Las pruebas son una parte crítica del proceso de desarrollo, y tener un límite de 2 elementos asegura que el equipo pueda centrarse en validar minuciosamente cada tarea antes de moverlas a "In Review".

### 7. Done

**Color:** Rojo
**Límite:** Sin límite

- **Descripción:** Tareas que han sido completadas, revisadas y aceptadas.
- **Justificación:** Una vez que una tarea se completa, debe moverse a la fase de "Done" sin restricción, ya que esto marca el final del ciclo de vida de desarrollo para esa tarea.

### 8. On Hold

**Color:** Rosa
**Límite:** 2 elementos

- **Descripción:** Tareas que están temporalmente detenidas debido a bloqueadores, como la espera de dependencias externas o recursos.
- **Justificación:** Limitamos las tareas "En Espera" a 2 para asegurar que el equipo no sobrecargue esta fase, lo que podría indicar problemas en la priorización o planificación de las tareas. Identificar los bloqueos temprano ayuda a resolverlos de manera eficiente.

---

## Categorías de Tareas

Además de las fases, hemos categorizado las tareas para asegurar una mejor visibilidad y comprensión del trabajo que se está realizando. Cada categoría aborda un aspecto diferente del ciclo de vida del proyecto:

### 1. Nueva Funcionalidad

**Descripción:** Tareas relacionadas con el desarrollo de nuevas funcionalidades que introducen capacidades adicionales al producto.

### 2. Mejora

**Descripción:** Mejoras a funcionalidades existentes, optimizando el rendimiento, la experiencia del usuario o la calidad del código.

### 3. Bug

**Descripción:** Tareas enfocadas en la resolución de defectos, problemas o bugs identificados durante el desarrollo o la fase de pruebas.

### 4. Deuda Técnica

**Descripción:** Abordar problemas de código o arquitectura que se pospusieron previamente. Esto es necesario para asegurar la mantenibilidad a largo plazo del proyecto.

### 5. Documentación

**Descripción:** Tareas dedicadas a la creación o actualización de documentación técnica, manuales de usuario o documentos de proceso.

### 6. Hotfix

**Descripción:** Soluciones urgentes requeridas para bugs críticos en el entorno de producción que necesitan atención inmediata.

### 7. Investigación

**Descripción:** Tareas de investigación relacionadas con nuevas tecnologías, herramientas o soluciones que podrían implementarse en el proyecto.

### 8. Pruebas

**Descripción:** Tareas relacionadas con la validación de la funcionalidad, usabilidad y rendimiento de las nuevas o modificadas características del sistema. Esto incluye la redacción y ejecución de casos de prueba.

---

## Estimaciones y Gestión de Tareas

Para gestionar mejor la priorización y estimación de tareas, hemos implementado las siguientes estrategias:

1. **Niveles de Prioridad**
   Las tareas se asignan a un nivel de prioridad (P0, P1, P2, etc.) para indicar su importancia y urgencia:
   - **P0:** Crítico, requiere atención inmediata (por ejemplo, hotfixes).
   - **P1:** Alta prioridad, debe abordarse a continuación.
   - **P2:** Prioridad media, importante pero no urgente.
   - **P3:** Baja prioridad, puede posponerse si es necesario.
   - **P4:** Mínima prioridad, tareas de baja importancia o que no son críticas.

2. **Estimación de Esfuerzo**
   Estimamos el tiempo y la complejidad de las tareas utilizando puntos de historia y horas, lo que nos permite comparar el trabajo planificado con el tiempo real invertido.

3. **Evaluación de Riesgos**
   Introducimos un campo para evaluar el riesgo potencial de cada tarea (Alto, Medio, Bajo), ayudando a priorizar tareas que podrían causar problemas mayores si se retrasan.

---

## ¿Por Qué Estos Cambios?

Las modificaciones a la plantilla base de GitHub nos permiten:

- **Mejorar la Claridad del Flujo de Trabajo:** Al introducir fases y categorías específicas, aseguramos que cada tarea esté claramente definida y seguida a lo largo de cada etapa del desarrollo.
- **Evitar la Sobrecarga:** Establecer límites en cuántas tareas pueden estar en cada fase previene cuellos de botella y asegura que el equipo se enfoque en un número manejable de tareas en un momento dado.
- **Mejor Priorización:** Con las categorías y campos de prioridad, podemos enfocarnos mejor en el trabajo de mayor impacto mientras mantenemos visible la deuda técnica y las mejoras.
- **Estimación Estructurada:** Al rastrear las estimaciones y el esfuerzo real, obtenemos información sobre nuestra precisión de planificación y podemos ajustar futuros sprints de manera más efectiva.

---

## Conclusión

Esta documentación sirve como una guía sobre cómo hemos estructurado nuestro flujo de trabajo y la razón detrás de cada decisión. Con estos ajustes, esperamos mejorar la productividad, la visibilidad de las tareas y el control general del proceso de desarrollo.
