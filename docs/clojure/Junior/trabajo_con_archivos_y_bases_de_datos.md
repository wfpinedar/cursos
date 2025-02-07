
# Trabajo con archivos y bases de datos en Clojure

## Explicación teórica
Clojure ofrece varias herramientas para trabajar con archivos y bases de datos en una aplicación. Estas herramientas son esenciales para almacenar y recuperar información de manera eficiente. Algunas de las características más importantes de Clojure para el manejo de archivos y bases de datos son:

- Inmutabilidad: en Clojure, los datos son inmutables por defecto, lo que significa que no se pueden modificar después de ser creados. Esto es útil para garantizar la integridad de los datos almacenados en archivos y bases de datos.

- Funciones de alto orden: Clojure permite el uso de funciones de alto orden, lo que significa que las funciones pueden ser tratadas como datos y pasadas como argumentos a otras funciones. Esto facilita la manipulación y transformación de datos almacenados en archivos y bases de datos.

- Estructuras de datos persistentes: Clojure ofrece estructuras de datos persistentes, que son versiones inmutables de estructuras de datos tradicionales. Estas estructuras son eficientes para la manipulación y almacenamiento de grandes cantidades de datos, lo que las hace ideales para trabajar con archivos y bases de datos.

## Palabras clave y su definición
- `with-open`: es una macro que permite abrir y cerrar automáticamente un archivo o una conexión de base de datos. Esto garantiza que los recursos sean liberados correctamente después de su uso.

- `slurp`: es una función que lee todo el contenido de un archivo y lo devuelve como una cadena de texto.

- `spit`: es una función que escribe una cadena de texto en un archivo.

- `jdbc`: es una biblioteca de Clojure que permite la conexión y ejecución de consultas en bases de datos relacionales.

- `defdb`: es una macro que define una conexión de base de datos y la registra bajo un nombre en un ámbito específico.

## Preguntas de repaso
1. ¿Qué significa que los datos sean inmutables en Clojure?
2. ¿Qué es una función de alto orden y cómo se utiliza en Clojure?
3. ¿Cuáles son las ventajas de usar estructuras de datos persistentes en Clojure?
4. ¿Qué es la macro `with-open` y cómo se utiliza?
5. ¿Qué función se utiliza para leer el contenido de un archivo en Clojure?
6. ¿Qué biblioteca de Clojure se utiliza para trabajar con bases de datos relacionales?
7. ¿Cómo se define una conexión de base de datos en Clojure?
8. ¿Cuál es la función utilizada para escribir en un archivo en Clojure?

## Ejemplos de código en Clojure
### Leer el contenido de un archivo y mostrarlo en la consola
```clojure
(with-open [file (clojure.java.io/reader "archivo.txt")]
  (println (slurp file)))
```

### Escribir en un archivo
```clojure
(spit "archivo.txt" "Este es un ejemplo de texto que se escribirá en el archivo.")
```

### Conexión y consulta a una base de datos utilizando la biblioteca `jdbc`
```clojure
(require '[jdbc.core :as jdbc])

(defdb db (jdbc/db-spec "jdbc:postgresql://localhost:5432/mi_base_de_datos"
                        "usuario" "contraseña"))

(jdbc/execute! db ["INSERT INTO usuarios (nombre, edad) VALUES (?, ?)" "Juan" 30])

(def usuarios (jdbc/query db ["SELECT * FROM usuarios"]))

(println usuarios)
```

## Ejercicios prácticos
1. Crea un programa que lea el contenido de un archivo y lo muestre en la consola.
2. Escribe una función que tome una lista de nombres y los escriba en un archivo, cada nombre en una línea diferente.
3. Modifica el código del ejemplo de conexión y consulta a una base de datos para que muestre únicamente los usuarios mayores de 18 años.

## Consejos o mejores prácticas
- Utiliza la macro `with-open` para asegurarte de que los recursos sean liberados correctamente después de su uso.
- Utiliza estructuras de datos persistentes para un mejor rendimiento al trabajar con grandes cantidades de datos.
- Utiliza funciones de alto orden para manipular y transformar datos almacenados en archivos y bases de datos de manera eficiente.
- Utiliza nombres descriptivos para las conexiones de base de datos y registra estas conexiones en un ámbito específico para facilitar su uso en diferentes partes de la aplicación.

### Navegación de lecciones

**<- Lección anterior**: [Módulos y namespaces](modulos_y_namespaces.md)

**Siguiente lección ->**: [Creación de aplicaciones web con Clojure](creacion_de_aplicaciones_web_con_clojure.md)
