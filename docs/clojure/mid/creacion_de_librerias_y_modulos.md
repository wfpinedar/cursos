
# Creación de librerías y módulos en Clojure

## Explicación teórica

Clojure es un lenguaje funcional y dinámico que se ejecuta sobre la plataforma de Java. Una de las ventajas de Clojure es su capacidad para trabajar con módulos y librerías, lo que permite reutilizar código en diferentes proyectos y facilita la colaboración en equipo. Los módulos y librerías son componentes esenciales en el desarrollo de software, ya que nos permiten dividir nuestro código en piezas más pequeñas y manejables, lo que a su vez mejora la legibilidad y mantenibilidad del mismo.

### Módulos en Clojure

Un módulo en Clojure es un conjunto de funciones, variables y/o datos relacionados que se agrupan en un archivo con extensión .clj o .cljc. Estos módulos pueden ser utilizados para dividir un proyecto en diferentes partes funcionales, o para encapsular una funcionalidad específica que pueda ser utilizada en diferentes proyectos.

### Librerías en Clojure

Las librerías en Clojure son módulos que se pueden compartir y reutilizar en diferentes proyectos. Estas librerías pueden ser publicadas en repositorios públicos para que otros desarrolladores puedan utilizarlas en sus proyectos. Las librerías pueden ser agregadas a un proyecto de Clojure mediante un gestor de dependencias, como Leiningen o Boot.

## Palabras clave y su definición

- **Módulo:** conjunto de funciones, variables y/o datos relacionados que se agrupan en un archivo con extensión .clj o .cljc.
- **Librería:** módulo que se puede compartir y reutilizar en diferentes proyectos.
- **Gestor de dependencias:** herramienta que permite administrar las dependencias de un proyecto y agregar librerías externas.

## Preguntas de repaso

1. ¿Qué es un módulo en Clojure?
2. ¿Cuál es la diferencia entre un módulo y una librería?
3. ¿Cómo se pueden agregar librerías a un proyecto de Clojure?
4. ¿Qué es un gestor de dependencias?

## Ejemplos de código en Clojure

```clojure
;; Ejemplo de un módulo en Clojure
(ns mi-modulo
  (:require
    [otro-modulo :refer [funcion-1 funcion-2]]))

(defn funcion-3
  [parametro]
  (str "Hola " parametro))

(def data [1 2 3])

(defn funcion-4 []
  (map funcion-1 data))

;; Ejemplo de una librería en Clojure
(ns mi-libreria
  (:require
    [otra-libreria :as ol]))

(defn funcion-5
  [parametro]
  (ol/funcion-6 parametro))

(defn funcion-6
  [parametro]
  (str "Hola " parametro))
```

## Ejercicios prácticos con instrucciones claras

1. Crea un módulo en Clojure con una función que reciba un número como parámetro y devuelva su cuadrado.
2. Crea una librería en Clojure con una función que reciba una cadena de texto como parámetro y devuelva la misma cadena en mayúsculas.
3. Agrega la librería creada en el ejercicio 2 a un proyecto de Clojure y utiliza la función en tu código.

## Consejos o mejores prácticas

- Utiliza nombres descriptivos y significativos para tus módulos y funciones.
- Divide tu código en módulos pequeños y bien definidos para facilitar su mantenimiento.
- Publica tus librerías en repositorios públicos para que otros desarrolladores puedan utilizarlas.
- Utiliza un gestor de dependencias para administrar las librerías externas en tus proyectos.

**<- Lección anterior**: [Despliegue y gestión de aplicaciones](despliegue_y_gestion_de_aplicaciones.md)
