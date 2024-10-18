# Despliegue del sistema

## 1. **Introducción**

El despliegue de un sistema es una etapa crítica en el ciclo de vida de un proyecto de software. Implica la instalación y configuración de la aplicación en un entorno de producción, asegurando que esté disponible para su uso por parte de los usuarios finales. En este documento, se describen las mejores prácticas y recomendaciones para desplegar el sistema de forma segura y eficiente.

## 2. **Entorno de Producción**

### 2.1 Servidores y Hosting

El sistema se desplegará en un servidor dedicado con las siguientes características:

- **Procesador**: 4 núcleos.
- **Memoria RAM**: 8 GB.
- **Almacenamiento**: 100 GB SSD.
- **Servidor Web**: Nginx como servidor web principal.
- **Docker**: Contenedor Docker para aislar la aplicación y sus dependencias.

### 2.2 Base de Datos

La base de datos se alojará en un servicio Saas (Software as a Service) para garantizar la escalabilidad y disponibilidad del sistema. Se utilizará PostgreSQL como motor de base de datos.

El proveedor de la base de datos es [Neon DB](https://neon.tech), que ofrece una solución de base de datos gestionada con copias de seguridad automáticas y alta disponibilidad.
