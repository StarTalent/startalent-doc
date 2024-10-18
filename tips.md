# Algunos consejos

## Desarrollo con Spring Boot

Spring Boot es un marco de trabajo que simplifica el desarrollo de aplicaciones Java, proporcionando una configuración por defecto y herramientas para crear aplicaciones de forma rápida y sencilla. Aquí hay algunos consejos para desarrollar con Spring Boot:

- La nomenclatura de las entidades y repositorios en Spring Boot es importante para mantener la coherencia y facilitar la comprensión del código. Por ejemplo, si tienes una entidad `Usuario`, el repositorio correspondiente podría llamarse `UsuarioRepository`.
- El nombre de las tablas en la base de datos se puede personalizar utilizando la anotación `@Table(name = "nombre_tabla")`, se recomienda usar nombres en plural para las tablas (por ejemplo, `users` en lugar de `user`) y en singular para las entidades.
- Es importante no eliminar los imports no utilizados en tu código, ya que esto puede llevar a errores y dificultar la lectura del código. Puedes utilizar la función de eliminación de imports no utilizados en tu IDE para mantener tu código limpio. Además, puedes configurar tu IDE para que elimine automáticamente los imports no utilizados al guardar el archivo.
- Cuanto tienes que usar muchas veces en las entidades `created_at` y `updated_at`, puedes utilizar la anotación `@CreationTimestamp` y `@UpdateTimestamp` de Hibernate para que se actualicen automáticamente. Esto te ahorra tiempo y reduce la posibilidad de errores.
- Tener en consideración que es mejor opción implementar una clase base abstracta (*por ejemplo, BaseEntity*) que contenga campos comunes como id, createdAt, y updatedAt. Luego, hacer que todas las entidades hereden de esta clase base.
- Es importante considerar el uso de Lombok para reducir el código boilerplate (*getters, setters, constructores, etc.*). Aunque en las entidades no es recomendable usar Lombok (*debido a problemas de serialización*), en los DTOs y clases de servicio puede ser muy útil
- Se tiene que ir pensando en la capacidad de agregar índices a las columnas que se usarán frecuentemente en consultas (*por ejemplo, email en User, domain en Account*). Esto mejorará el rendimiento de las consultas y reducirá el tiempo de respuesta.
- Es importante desde un inicio implementar validaciones a nivel de entidad utilizando las anotaciones de Jakarta Bean Validation. Debido a que Spring Boot integra Hibernate Validator, puedes usar anotaciones como `@NotNull`, `@Size`, `@Email`, `@Pattern`, entre otras, para validar los campos de tus entidades y esto facilitará la validación de los datos en la capa de servicio.
- Es conveniente utilizar la anotación `@Transactional` en los métodos de servicio que realizan operaciones de lectura y escritura en la base de datos. Esto asegura que las operaciones se realicen de manera atómica y se gestionen correctamente las transacciones.
- Es muy importante asegurarse de que todas las relaciones estén correctamente mapeadas y que se utilice la estrategia de fetch adecuada (LAZY o EAGER) según las necesidades de la aplicación. El uso incorrecto de las relaciones y la estrategia de fetch puede llevar a problemas de rendimiento y a consultas innecesarias a la base de datos.
- Considera la posibilidad de que se use la propiedad `spring.jpa.open-in-view=false` desde un inicio para evitar problemas de rendimiento en la carga de entidades asociadas. Esto deshabilita la carga automática de entidades asociadas en las vistas, lo que puede causar consultas adicionales y ralentizar la aplicación. Se considera una buena práctica deshabilitar esta propiedad (*es un anti-patrón, por defecto está en `true`*) y cargar explícitamente las entidades asociadas cuando sea necesario.

> Un anti-patrón es una solución común a un problema recurrente que genera más problemas de los que resuelve. Es importante identificar y evitar los anti-patrones en el desarrollo de software para mantener la calidad y la eficiencia del código.

## Trabajo con IntelliJ IDEA

IntelliJ IDEA es uno de los IDE más populares para el desarrollo de aplicaciones Java. Aquí hay algunos consejos para trabajar de manera más eficiente con IntelliJ IDEA:

### TODO: Comentarios para los programadores

Cuando trabajas en un proyecto de desarrollo de software, es común encontrar áreas que necesitan atención o mejoras. Para ayudar a identificar estas áreas, puedes usar comentarios especiales en tu código. Aquí hay algunos ejemplos de comentarios que puedes utilizar:

- **[Configurar el editor](images/todo-settings.jpg)** para resaltar los comentarios `TODO` y `FIXME`.
- En IntelliJ IDEA, ve a `Preferences` > `Editor` > `TODO` y agrega los patrones `TODO` y `FIXME` que deseas resaltar.
- Puedes personalizar los colores y la severidad de los comentarios `TODO` y `FIXME` para que se destaquen en tu código.
- Al utilizar comentarios `TODO` y `FIXME`, asegúrate de que sean claros y específicos para que otros desarrolladores puedan entender rápidamente lo que se necesita hacer.
- En mi caso, suelo utilizar:
  - `// TODO: [Descripción de la tarea]` para marcar áreas que necesitan atención o mejoras.
  - `// FIXME: [Descripción del problema]` para señalar problemas que deben ser corregidos.
  - `// REVIEW: [Descripción de la revisión]` para indicar áreas que necesitan ser revisadas o discutidas.
  - `// WIP: [Descripción del trabajo en progreso]` para identificar áreas en las que se está trabajando actualmente.
- De esta manera, puedes mantener un registro de las tareas pendientes y colaborar de manera efectiva con otros miembros del equipo.
- Puedes **[filtrar los comentarios](images/todo-filters.jpg)** `TODO` y `REVIEW` en IntelliJ IDEA utilizando la barra de herramientas en la parte superior derecha del editor.
