
# Persistencia de datos en Clojure

## Explicación teórica
La persistencia de datos se refiere a la capacidad de un programa para almacenar y recuperar datos de manera permanente. En el caso de Clojure, esto se logra mediante el uso de bases de datos relacionales o no relacionales, como PostgreSQL, MongoDB o Redis, entre otros.

Clojure cuenta con una amplia variedad de librerías y herramientas para trabajar con bases de datos, lo que hace que sea una buena opción para desarrollar aplicaciones que requieran persistencia de datos.

## Palabras clave y su definición
- Bases de datos: Conjunto de datos estructurados y organizados de manera que sea fácil acceder a ellos y gestionarlos.
- Almacenamiento: Proceso de guardar datos en un medio de almacenamiento para su posterior recuperación.
- Persistencia: Capacidad de un programa para almacenar datos de manera permanente.
- Relacional: Tipo de base de datos que organiza los datos en tablas, con relaciones entre ellas.
- No relacionales: Tipo de base de datos que no utiliza tablas y no tiene relaciones entre los datos almacenados.
- Librerías: Conjunto de funciones y herramientas que facilitan el desarrollo de software.

## Preguntas de repaso
1. ¿Qué es la persistencia de datos?
2. ¿Qué tipos de bases de datos se pueden utilizar en Clojure?
3. ¿Qué es una librería en el contexto de Clojure?
4. ¿Cuál es la diferencia entre bases de datos relacionales y no relacionales?

## Ejemplos de código en Clojure
### Conexión a una base de datos PostgreSQL
```clojure
(require '[clojure.java.jdbc :as jdbc])

(def db {:classname "org.postgresql.Driver"
         :subprotocol "postgresql"
         :subname "//localhost:5432/mydatabase"
         :user "username"
         :password "password"})

(jdbc/query db ["SELECT * FROM users"])
```

### Creación de una nueva entrada en MongoDB
```clojure
(require '[monger.core :as mg])

(mg/insert! :users {:name "John" :age 25})
```

## Ejercicios prácticos
1. Crear una base de datos en PostgreSQL y conectarla desde Clojure.
2. Insertar un nuevo registro en una base de datos MongoDB utilizando Clojure.
3. Realizar una consulta a una base de datos no relacional y mostrar los resultados en la consola.

## Consejos o mejores prácticas
- Utilizar librerías de terceros para trabajar con bases de datos, como clojure.java.jdbc o monger.
- Utilizar transacciones para asegurar la integridad de los datos en la base de datos.
- Implementar un sistema de gestión de errores y excepciones al trabajar con bases de datos.
- Realizar pruebas unitarias para asegurar el correcto funcionamiento de las consultas y operaciones en la base de datos.


**<- Lección anterior**: [Interoperabilidad con Java](interoperabilidad_con_java.md)

**Siguiente lección ->**: [Optimización de código](optimizacion_de_codigo.md)


