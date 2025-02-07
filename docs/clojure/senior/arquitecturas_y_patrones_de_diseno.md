
# Arquitecturas y patrones de diseño en Clojure

## Explicación teórica

Clojure es un lenguaje de programación funcional que se basa en la filosofía de "programación orientada a datos". Esto significa que todas las operaciones se realizan sobre estructuras de datos inmutables, lo que lo hace ideal para construir aplicaciones altamente escalables y mantenibles.

Sin embargo, para construir aplicaciones complejas, es importante tener una comprensión clara de la arquitectura y los patrones de diseño en Clojure. Estos proporcionan una estructura y un enfoque para desarrollar aplicaciones que sean fáciles de entender, extender y mantener.

En Clojure, hay dos arquitecturas principales que se utilizan comúnmente: Datomic y Component.

### Datomic

Datomic es una base de datos distribuida y orientada a tiempo que se integra perfectamente con Clojure. Utiliza un modelo de datos inmutable y transaccional, lo que lo hace ideal para aplicaciones que requieren una alta consistencia y escalabilidad.

Una de las principales ventajas de Datomic es que permite realizar consultas en el tiempo, lo que significa que se pueden realizar consultas sobre cómo eran los datos en un momento específico en el pasado. Esto es especialmente útil en aplicaciones que manejan datos sensibles o críticos en el tiempo.

### Component

Component es un patrón de diseño que se utiliza para construir aplicaciones modulares y altamente extensibles en Clojure. Se basa en el principio de separar la lógica de la aplicación en componentes independientes y conectados.

Cada componente es una entidad inmutable que encapsula un estado y una lógica de negocio específicos. Estos componentes se conectan entre sí mediante un sistema de dependencias, lo que permite una fácil reutilización y extensión de la funcionalidad de la aplicación.

## Palabras clave y su definición

- Inmutabilidad: significa que los datos no pueden modificarse una vez que se han creado. En Clojure, todos los datos son inmutables por defecto, lo que garantiza una mayor consistencia y evita errores comunes en el manejo de datos.
- Transaccional: se refiere a una operación que se realiza de forma completa o no se realiza en absoluto. En Datomic, todas las transacciones se realizan de manera atómica, lo que significa que se ejecutan completamente o no se ejecutan en absoluto.
- Modularidad: es un enfoque de programación que consiste en dividir una aplicación en componentes independientes y conectados. Esta técnica facilita la reutilización y extensión de la funcionalidad de la aplicación.
- Dependencias: se refiere a la relación entre diferentes componentes en una aplicación. En Component, los componentes están conectados entre sí a través de un sistema de dependencias, lo que permite una fácil gestión y extensión de la aplicación.

## Preguntas de repaso

1. ¿Qué es Datomic y qué ventajas ofrece en el desarrollo de aplicaciones en Clojure?
2. ¿En qué se basa el patrón de diseño Component y qué beneficios ofrece en el desarrollo de aplicaciones en Clojure?
3. ¿Qué significa que los datos sean inmutables en Clojure?
4. ¿Cuál es la diferencia entre una operación transaccional y una no transaccional?
5. ¿Por qué es importante tener una arquitectura clara y bien definida en una aplicación en Clojure?

## Ejemplos de código en Clojure

### Datomic

```clojure
(require '[datomic.api :as d])
 
(def db-uri "datomic:mem://my-db")
 
(def schema [{:db/ident :person/name
              :db/valueType :db.type/string
              :db/cardinality :db.cardinality/one
              :db/unique :db.unique/identity}
             {:db/ident :person/age
              :db/valueType :db.type/long
              :db/cardinality :db.cardinality/one}
             {:db/ident :person/gender
              :db/valueType :db.type/string
              :db/cardinality :db.cardinality/one}
             {:db/ident :person/country
              :db/valueType :db.type/string
              :db/cardinality :db.cardinality/one}])
 
(d/create-database db-uri)
 
(def conn (d/connect db-uri))
 
(d/transact conn schema)
 
(def person1 {:db/id #db/id[:db.part/user]
              :person/name "John"
              :person/age 30
              :person/gender "Male"
              :person/country "USA"})
 
(def person2 {:db/id #db/id[:db.part/user]
              :person/name "Jane"
              :person/age 25
              :person/gender "Female"
              :person/country "Canada"})
 
(def tx (d/transact conn [person1 person2]))
 
(def all-persons (d/q '[:find ?name ?age ?gender ?country
                        :where [?person :person/name ?name]
                               [?person :person/age ?age]
                               [?person :person/gender ?gender]
                               [?person :person/country ?country]]
                     (d/db conn)))
 
(println all-persons)
; Output: [["John" 30 "Male" "USA"] ["Jane" 25 "Female" "Canada"]]
```

### Component

```clojure
(defrecord DatabaseComponent [host port]
  component/Lifecycle
  (start [component]
    (println (str "Starting database on " host ":" port))
    (assoc component :status :started))
  (stop [component]
    (println "Stopping database")
    (assoc component :status :stopped)))
 
(defrecord WebServerComponent [port]
  component/Lifecycle
  (start [component]
    (println (str "Starting web server on port " port))
    (assoc component :status :started))
  (stop [component]
    (println "Stopping web server")
    (assoc component :status :stopped)))
 
(defrecord ApplicationComponent [database web-server]
  component/Lifecycle
  (start [component]
    (let [db (component/start database)
          web-server (component/start web-server)]
      (println "Starting application")
      (assoc component :status :started)))
  (stop [component]
    (println "Stopping application")
    (assoc component :status :stopped)))
 
(def database (map->DatabaseComponent {:host "localhost" :port 3306}))
(def web-server (map->WebServerComponent {:port 8080}))
(def application (map->ApplicationComponent {:database database :web-server web-server}))
 
(component/start application)
; Output: Starting web server on port 8080
;         Starting database on localhost:3306
;         Starting application
 
(component/stop application)
; Output: Stopping application
;         Stopping web server
;         Stopping database
```

## Ejercicios prácticos con instrucciones claras

1. Crea un nuevo proyecto de Clojure y agrega las dependencias de Datomic y Component.
2. Define un schema para una base de datos de Datomic que tenga los atributos :book/title, :book/author y :book/price.
3. Crea una función que permita agregar un nuevo libro a la base de datos. La función debe recibir los parámetros title, author y price y transaccionarlos en la base de datos.
4. Crea una función que permita consultar todos los libros de la base de datos y devolverlos en una lista.
5. Define los componentes para una aplicación que utilice la base de datos de Datomic y el servidor web Jetty.
6. Implementa la lógica para iniciar y detener la aplicación de acuerdo con el patrón de diseño Component.
7. Agrega un nuevo endpoint en el servidor web que permita agregar un libro utilizando la función creada en el paso 3.
8. Ejecuta y prueba tu aplicación para asegurarte de que todo funcione correctamente.

## Consejos o mejores prácticas

- Al utilizar Datomic, es importante tener una comprensión clara de la estructura de datos y cómo se relacionan entre sí. Esto facilitará la escritura de consultas efectivas y eficientes.
- Al utilizar Component, es importante definir componentes lo más pequeños y específicos posible. Esto facilitará la reutilización y extensión de la funcionalidad de la aplicación.
- Es importante seguir prácticas de programación funcional al trabajar con Clojure. Esto incluye evitar el uso de variables mutables y utilizar funciones puras siempre que sea posible.


**<- Lección anterior**: [Programación lógica](programacion_logica.md)

**Siguiente lección ->**: [Integración con otros lenguajes y plataformas](integracion_con_otros_lenguajes_y_plataformas.md)
