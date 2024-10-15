# Sistema de Gestión de Vacantes y Registro de Candidatos Multi-Tenant

## Tabla de Contenidos

- [Sistema de Gestión de Vacantes y Registro de Candidatos Multi-Tenant](#sistema-de-gestión-de-vacantes-y-registro-de-candidatos-multi-tenant)
  - [Tabla de Contenidos](#tabla-de-contenidos)
  - [Introducción](#introducción)
  - [Tecnologías Utilizadas](#tecnologías-utilizadas)
    - [Spring Boot](#spring-boot)
    - [Spring Security](#spring-security)
    - [Vaadin](#vaadin)
    - [Thymeleaf](#thymeleaf)
    - [Tailwind CSS](#tailwind-css)
    - [jQuery](#jquery)
    - [Base de Datos y Multi-Tenancy](#base-de-datos-y-multi-tenancy)
  - [Metodologías de Gestión de Proyectos](#metodologías-de-gestión-de-proyectos)
    - [Kanban](#kanban)
    - [Estimación de Tareas con PERT](#estimación-de-tareas-con-pert)
    - [Técnicas de Priorización](#técnicas-de-priorización)
      - [Matriz de Eisenhower](#matriz-de-eisenhower)
      - [Método MoSCoW](#método-moscow)
    - [Evaluación de Complejidad con WSJF](#evaluación-de-complejidad-con-wsjf)
  - [Requisitos del Producto Mínimo Viable (MVP)](#requisitos-del-producto-mínimo-viable-mvp)
    - [Must Have (Debe Tener)](#must-have-debe-tener)
    - [Should Have (Debería Tener)](#should-have-debería-tener)
    - [Could Have (Podría Tener)](#could-have-podría-tener)
    - [Won't Have (No Tendrá)](#wont-have-no-tendrá)
  - [Estructura del Equipo](#estructura-del-equipo)
  - [Conclusión](#conclusión)
  - [Recursos Adicionales](#recursos-adicionales)
  - [Enlaces de interés](#enlaces-de-interés)
  - [Contacto](#contacto)

## Introducción

Este proyecto tiene como objetivo desarrollar un **sistema multi-tenant de gestión de vacantes y registro de candidatos** mediante la migración de una aplicación existente en Grails a una arquitectura moderna utilizando Spring Boot. El nuevo sistema está diseñado para:

- Proporcionar un **backend API REST** robusto con Spring Boot.
- Utilizar **Vaadin** para el frontend administrativo, permitiendo gestionar vacantes y candidatos de manera eficiente.
- Implementar **Thymeleaf**, **Tailwind CSS** y **jQuery** para el frontend público, facilitando la publicación de vacantes y el registro de candidatos.
- Soportar **multi-tenancy** discriminando inquilinos (tenants) basados en el dominio o subdominio, permitiendo personalización y branding específicos para cada cliente.

El proyecto busca simplificar el mantenimiento consolidando múltiples instancias independientes en un sistema único y escalable. Será desarrollado por un equipo de **dos programadores**.

## Tecnologías Utilizadas

### Spring Boot

**Spring Boot** sirve como la base del backend API REST. Fue elegido por su simplicidad, potentes características y amplio soporte comunitario.

- **Auto-configuración**: Minimiza el código de configuración.
- **Servidores integrados**: Incluye Tomcat, Jetty o Undertow embebidos.
- **Características listas para producción**: Métricas, comprobaciones de salud y configuración externalizada.
- **Soporte para Microservicios**: Ideal para aplicaciones escalables.

### Spring Security

**Spring Security** se utiliza para autenticación y autorización, asegurando un control de acceso seguro en toda la aplicación.

- **Mecanismos de Autenticación**: Soporta HTTP Basic, OAuth2, JWT, etc.
- **Control de Acceso Basado en Roles**: Gestión de usuarios, roles y privilegios.
- **Integración con Spring Boot**: Se integra perfectamente con el contexto de la aplicación.

### Vaadin

**Vaadin** fue seleccionado para el frontend administrativo debido a su capacidad para crear interfaces de usuario ricas e interactivas utilizando Java.

- **UI Basada en Componentes**: Ofrece un conjunto completo de componentes de interfaz.
- **Arquitectura del Lado del Servidor**: Simplifica el desarrollo al ejecutar la lógica de UI en el servidor.
- **Temas y Estilos**: Permite personalizar temas por inquilino.

### Thymeleaf

**Thymeleaf** se utiliza para el frontend público para renderizar vistas HTML del lado del servidor, proporcionando un motor de plantillas natural que se integra bien con Spring Boot.

- **Plantillas Naturales**: Las plantillas son HTML5 válido, facilitando el diseño.
- **Contenido Dinámico**: Soporta renderización de datos dinámicos.
- **Soporte de Internacionalización**: Facilita el soporte multilingüe.

### Tailwind CSS

**Tailwind CSS** es un framework CSS de utilidad que ayuda a diseñar interfaces modernas y responsivas de manera eficiente.

- **Clases de Utilidad**: Proporciona clases de utilidad de bajo nivel para desarrollo rápido de UI.
- **Diseño Responsivo**: Soporte integrado para diferentes dispositivos.
- **Personalización**: Altamente configurable para adaptar el branding del cliente.

### jQuery

**jQuery** mejora la interactividad en el frontend público, simplificando la manipulación del DOM y las solicitudes AJAX.

- **JavaScript Simplificado**: Manejo de eventos y animaciones más sencillo.
- **Compatibilidad entre Navegadores**: Abstrae las diferencias entre navegadores.
- **Ecosistema Rico**: Amplia gama de plugins disponibles.

### Base de Datos y Multi-Tenancy

La aplicación utilizará una única base de datos con discriminación de inquilinos mediante un campo llamado `account` en cada entidad.

- **Identificación de Dominio/Subdominio**: Determina el inquilino basado en el dominio o subdominio entrante.
- **Aislamiento de Datos**: Garantiza que cada inquilino acceda solo a sus datos.
- **Personalización**: Carga dinámicamente configuraciones y branding específicos del cliente.

## Metodologías de Gestión de Proyectos

### Kanban

Adoptamos la metodología **Kanban** para organizar el proyecto, enfocándonos en visualizar el trabajo, limitar el trabajo en progreso y maximizar la eficiencia.

- **Flujo de Trabajo Visual**: Las tareas se muestran en un tablero Kanban.
- **Entrega Continua**: Fomenta lanzamientos regulares.
- **Flexibilidad**: Adaptable a cambios de prioridades.

### Estimación de Tareas con PERT

Utilizamos la **Técnica de Revisión y Evaluación de Programas (PERT)** para estimar el tiempo de las tareas, considerando la incertidumbre.

- **Tiempo Optimista (O)**: Mejor escenario posible.
- **Tiempo Más Probable (M)**: Duración más probable.
- **Tiempo Pesimista (P)**: Peor escenario posible.
- **Tiempo Estimado (TE)**: Calculado como `(O + 4M + P) / 6`.

### Técnicas de Priorización

#### Matriz de Eisenhower

Las tareas se priorizan según su urgencia e importancia:

- **Urgente e Importante**: Hacer inmediatamente.
- **Importante, No Urgente**: Programar para más tarde.
- **Urgente, No Importante**: Delegar si es posible.
- **No Urgente, No Importante**: Considerar eliminar.

#### Método MoSCoW

Define requisitos basados en prioridad:

- **Must Have (Debe Tener)**: Esencial para el MVP.
- **Should Have (Debería Tener)**: Importante pero no crítico.
- **Could Have (Podría Tener)**: Deseable si el tiempo lo permite.
- **Won't Have (No Tendrá)**: Excluido del alcance actual.

### Evaluación de Complejidad con WSJF

El **Weighted Shortest Job First (WSJF)** ayuda a priorizar tareas calculando la relación costo-beneficio.

- **Costo del Retardo (CoD)**: Combina valor de negocio, criticidad temporal y reducción de riesgos.
- **Tamaño del Trabajo**: Representa el esfuerzo requerido.
- **Puntaje WSJF**: Calculado como `CoD / Tamaño del Trabajo`.

## Requisitos del Producto Mínimo Viable (MVP)

El MVP se enfoca en entregar funcionalidades centrales necesarias para la operación del sistema.

### Must Have (Debe Tener)

- **Autenticación y Autorización de Usuarios**: Inicio de sesión seguro, gestión de roles y privilegios.
- **Infraestructura Multi-Tenant**: Detección de inquilinos y aislamiento de datos basado en dominio/subdominio.
- **Interfaz Administrativa con Vaadin**:
  - Gestión de vacantes.
  - Seguimiento de postulaciones de candidatos.
- **Interfaz Pública con Thymeleaf**:
  - Visualización de ofertas de trabajo.
  - Registro y envío de postulaciones de candidatos.
- **Diseño Responsivo**: Asegurar usabilidad en múltiples dispositivos.
- **Personalización Básica de Branding**: Logos y esquemas de color por inquilino.

### Should Have (Debería Tener)

- **Notificaciones por Email**: Correos automáticos para confirmación de postulaciones.
- **Opciones de Búsqueda y Filtro**: Permitir a candidatos buscar vacantes.
- **Soporte de Internacionalización**: Soporte para múltiples idiomas.

### Could Have (Podría Tener)

- **Panel de Análisis**: Información sobre métricas de postulaciones para administradores.
- **Integración con Redes Sociales**: Compartir vacantes en plataformas como LinkedIn.

### Won't Have (No Tendrá)

- **Herramientas Avanzadas de Reporte**: Informes detallados y exportaciones.
- **Funciones de Machine Learning**: Emparejamiento de candidatos impulsado por IA.

## Estructura del Equipo

El proyecto será desarrollado por **dos programadores**, cada uno enfocado en áreas específicas.

- **Programador 1**:
  - Desarrollo backend con Spring Boot y Spring Security.
  - Implementación de la lógica multi-tenant.
  - Integración de Vaadin para el panel administrativo.

- **Programador 2**:
  - Desarrollo frontend con Thymeleaf, Tailwind CSS y jQuery.
  - Diseño de interfaces públicas responsivas.
  - Implementación de características de registro de candidatos y aplicaciones de empleo.

## Conclusión

Al migrar de Grails a Spring Boot y adoptar una arquitectura multi-tenant, este proyecto busca crear un sistema escalable, mantenible y personalizable para gestionar ofertas de trabajo y aplicaciones de candidatos. Utilizando tecnologías modernas y metodologías efectivas de gestión de proyectos, estamos preparados para entregar un MVP robusto que sirva como base sólida para futuras mejoras.

---

**Nota**: Este proyecto sigue las mejores prácticas en desarrollo de software y gestión de proyectos, asegurando un producto de alta calidad que satisface las necesidades de administradores y candidatos.

---

## Recursos Adicionales

- [Documentación de Spring Boot](https://spring.io/projects/spring-boot)
- [Documentación de Vaadin](https://vaadin.com/docs)
- [Documentación de Thymeleaf](https://www.thymeleaf.org/documentation.html)
- [Documentación de Tailwind CSS](https://tailwindcss.com/docs)
- [Documentación de jQuery](https://api.jquery.com/)

---

## Enlaces de interés

- [Flujo de trabajo y metodologías de gestión de proyectos](flujo-de-trabajo.md)
- [Requisitos del Producto Mínimo Viable (MVP)](mvp.md)
- [Estructura del equipo y roles](equipo.md)
- [Recursos y enlaces útiles](recursos.md)
- [Checklist para el proyecto](checklist.md)
- [Proceso de desarrollo y buenas prácticas](proceso-desarrollo.md)

---

## Contacto

Para consultas o soporte, por favor contacta al equipo de desarrollo:

- **Email**: <lgzarturo@gmail.com>

---

**Importante**: Este documento está en constante actualización a medida que el proyecto avanza. Recomendamos revisarlo periódicamente para estar al tanto de los cambios y mejoras.
