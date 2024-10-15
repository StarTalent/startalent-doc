# Proceso de desarrollo y buenas prácticas

## 1. **Sobre JPA y Spring Data JPA**

**JPA (Java Persistence API):**
JPA es una especificación que permite manejar el mapeo entre las clases de una aplicación Java y las tablas de una base de datos relacional. Con JPA, se pueden persistir, actualizar, borrar y consultar datos de forma sencilla, abstrayendo la interacción directa con SQL.

JPA define cómo interactuar con bases de datos relacionales desde aplicaciones Java. Permite mapear entidades Java a tablas de bases de datos, facilitando las operaciones de CRUD (Crear, Leer, Actualizar, Eliminar) a través de una abstracción sobre SQL.

**Spring Data JPA:**
Es un proyecto de Spring que facilita aún más el uso de JPA, permitiendo crear consultas y gestionar el acceso a la base de datos con el mínimo esfuerzo. Spring Data JPA genera implementaciones automáticamente basadas en convenciones de nombres y simplifica las consultas mediante métodos personalizados.

Spring Data JPA nos permite centrarnos más en el modelo de negocio, ya que genera gran parte del código necesario para gestionar persistencia automáticamente. Esto reduce la cantidad de código repetitivo y mejora la productividad del desarrollador.

Ejemplo básico de un repositorio usando Spring Data JPA:

```java
public interface UsuarioRepository extends JpaRepository<Usuario, Long> {
    List<Usuario> findByNombre(String nombre);
}
```

## 2. **Importancia de las relaciones entre entidades y su reflejo en la base de datos**

Es fundamental comprender que en las bases de datos relacionales, los datos se distribuyen en diferentes tablas, pero en la lógica del negocio, es común que las entidades estén relacionadas. JPA permite definir estas relaciones con anotaciones como `@OneToMany`, `@ManyToOne`, `@OneToOne`, y `@ManyToMany`, reflejando cómo están conectadas las entidades en la base de datos.

**Relaciones más comunes:**

- **@OneToMany y @ManyToOne:** Sirven para modelar relaciones de uno a muchos (ej. un cliente tiene muchas órdenes).

Ejemplo:

```java
@Entity
public class Cliente {
    @OneToMany(mappedBy = "cliente")
    private List<Orden> ordenes;
}

@Entity
public class Orden {
    @ManyToOne
    @JoinColumn(name = "cliente_id")
    private Cliente cliente;
}
```

Esto crea una relación donde cada orden está vinculada a un cliente y, en la base de datos, suele implicar el uso de una clave foránea (`cliente_id`).

### Tipos de relaciones

- **One-to-One** (*@OneToOne*): Una entidad tiene una relación uno a uno con otra entidad. Ejemplo: Una persona tiene un pasaporte. En la base de datos, esto se reflejaría con una clave foránea en una de las tablas.
- **One-to-Many** (*@OneToMany*): Una entidad está relacionada con muchas instancias de otra entidad. Ejemplo: Un autor puede tener muchos libros. Esto se refleja como una clave foránea en la tabla que contiene "muchos" registros.
- **Many-to-One** (*@ManyToOne*): Es la inversa de @OneToMany, donde muchas entidades están asociadas a una única entidad. Esto se traduce en una columna en la tabla "muchos" que contiene la clave foránea de la entidad única.
- **Many-to-Many** (*@ManyToMany*): Muchas entidades están relacionadas con muchas otras entidades. En la base de datos, esto se refleja mediante una tabla intermedia que contiene las claves foráneas de ambas entidades.

Es importante asegurarse de usar las anotaciones correctas para mantener la integridad referencial y optimizar las consultas en las bases de datos.

## 3. **Escribir pruebas unitarias para las entidades y repositorios**

Para garantizar que las entidades y repositorios funcionan correctamente, es crucial escribir pruebas unitarias. Esto permite verificar que las operaciones CRUD básicas se comportan como se espera, además de las relaciones y las consultas personalizadas.

Es importante saber usar herramientas como **JUnit5** y **Mockito** para mockear dependencias y aislar las pruebas de lógica de negocio y persistencia.

**Ejemplo de prueba unitaria básica para un repositorio:**

```java
@SpringBootTest
public class UsuarioRepositoryTests {

    @Autowired
    private UsuarioRepository usuarioRepository;

    @Test
    public void testGuardarUsuario() {
        Usuario usuario = new Usuario();
        usuario.setNombre("Arturo");
        usuario = usuarioRepository.save(usuario);

        assertNotNull(usuario.getId());
        assertEquals("Arturo", usuario.getNombre());
    }

    @Test
    public void testFindByNombre() {
        List<Usuario> usuarios = usuarioRepository.findByNombre("Arturo");
        assertFalse(usuarios.isEmpty());
    }
}
```

Esto asegura que el repositorio puede guardar correctamente un usuario y que la búsqueda por nombre funciona como se espera.

## 4. **Revisión de código para asegurar que se siguen las mejores prácticas**

Una vez que se ha completado la tarea, es crucial solicitar una revisión del código para asegurarte de que sigue las mejores prácticas. Durante la revisión, presta atención a los siguientes puntos:

- **Consistencia en las anotaciones JPA:** Revisa que las relaciones entre entidades estén bien definidas y no haya problemas de rendimiento, como el uso incorrecto de `FetchType.EAGER` cuando debería ser `LAZY`.
- **Nombres de métodos en los repositorios:** Los métodos en los repositorios deben ser descriptivos y fáciles de entender. Además, las consultas generadas automáticamente deben tener un rendimiento aceptable y utilizar índices cuando sea necesario.
- **Pruebas unitarias completas:** Asegúrate de que las pruebas cubren los casos más importantes, como la inserción, actualización, eliminación y consulta de entidades, además de validar correctamente las relaciones.
- **Validación de errores y excepciones:** Revisa que el manejo de excepciones esté bien implementado para evitar que el sistema falle en producción.
