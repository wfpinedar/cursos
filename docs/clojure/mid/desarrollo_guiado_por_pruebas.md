
# Desarrollo guiado por pruebas en Clojure

El desarrollo guiado por pruebas (TDD, por sus siglas en inglés) es una metodología de desarrollo de software que se basa en escribir las pruebas antes de escribir el código de la aplicación. Esta forma de trabajar asegura que el código esté bien probado y funcione correctamente antes de ser implementado, lo que reduce los errores y facilita la detección de posibles problemas.

En Clojure, existen varias herramientas disponibles para el desarrollo guiado por pruebas, entre las más populares se encuentran Clojure.test y Midje.

## Palabras clave y su definición

- Desarrollo guiado por pruebas (TDD): Metodología de desarrollo de software que se basa en escribir las pruebas antes de escribir el código de la aplicación.
- Clojure.test: Biblioteca de Clojure para escribir y ejecutar pruebas unitarias.
- Midje: Biblioteca de Clojure para escribir y ejecutar pruebas en un estilo de lenguaje natural.

## Preguntas de repaso

1. ¿Qué es el desarrollo guiado por pruebas y por qué es importante?
2. ¿Cuáles son las herramientas disponibles en Clojure para el desarrollo guiado por pruebas?
3. ¿Qué es Clojure.test y para qué se utiliza?
4. ¿Qué es Midje y qué ventajas ofrece en comparación con Clojure.test?

## Ejemplos de código en Clojure

### Clojure.test

```clojure
(ns ejemplo.test
  (:require [clojure.test :refer :all]))

(deftest suma-test
  (testing "Prueba de suma"
    (is (= 4 (+ 2 2)))))

(run-tests)
```

### Midje

```clojure
(ns ejemplo.test
  (:require [midje.sweet :refer :all]))

(fact "Prueba de suma"
  (+ 2 2) => 4)
```

## Ejercicios prácticos

1. Utilizando Clojure.test, escribe una prueba para la función "restar" que acepte dos parámetros y devuelva la resta de ambos.
2. Utilizando Midje, escribe una prueba para la función "multiplicar" que acepte dos parámetros y devuelva la multiplicación de ambos.
3. Escribe una función en Clojure llamada "es-par" que acepte un número como parámetro y devuelva true si es par y false si es impar.
4. Escribe una prueba para la función "es-par" utilizando Midje.

## Consejos y mejores prácticas

- Escribir pruebas simples y específicas.
- Utilizar nombres descriptivos para las pruebas.
- Escribir las pruebas antes de escribir el código de la función.
- Utilizar herramientas de análisis de código estático, como Eastwood o Kibit, para mejorar la calidad del código.


**<- Lección anterior**: [Testing y depuración](testing_y_depuracion.md)

**Siguiente lección ->**: [Interoperabilidad con Java](interoperabilidad_con_java.md)
