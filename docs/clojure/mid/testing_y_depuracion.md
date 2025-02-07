
# Testing y depuración en Clojure

## Explicación teórica
Clojure es un lenguaje de programación funcional que se ejecuta en la máquina virtual de Java (JVM). La programación funcional se basa en funciones puras, que no tienen efectos secundarios y siempre producen el mismo resultado para los mismos valores de entrada. Esto hace que el código en Clojure sea más fácil de probar y depurar.

El testing y la depuración son procesos importantes en el desarrollo de software, ya que permiten detectar y corregir errores en el código. En Clojure, existen varias técnicas y herramientas que facilitan estas tareas.

## Palabras clave y su definición
- Testing: proceso de verificar que el código funcione correctamente y cumpla con los requisitos establecidos.
- Depuración: proceso de identificar y corregir errores en el código.
- Pruebas unitarias: pruebas que se realizan a nivel de funciones o pequeñas secciones de código.
- Pruebas de integración: pruebas que se realizan a nivel de sistema, verificando la interacción entre diferentes partes del código.
- REPL: Read-Evaluate-Print Loop, una herramienta que permite ejecutar código y ver los resultados en tiempo real.
- TDD: Test Driven Development, una metodología de desarrollo en la que se escriben las pruebas antes de escribir el código.

## Preguntas de repaso
1. ¿Qué es el testing y por qué es importante?
2. ¿Qué es la depuración y por qué es importante?
3. ¿Cuál es la diferencia entre pruebas unitarias y pruebas de integración?
4. ¿Qué es el REPL y para qué se utiliza?
5. ¿Qué es TDD y cómo puede ayudar en el desarrollo de software?

## Ejemplos de código en Clojure
### Pruebas unitarias
```clojure
(defn sum [a b]
  (+ a b))

(deftest test-sum
  (is (= (sum 2 3) 5))
  (is (= (sum -1 4) 3)))
```

### Pruebas de integración
```clojure
(defn get-user [id]
  (db/get-user-by-id id))

(deftest test-get-user
  (is (= (get-user 1) {:name "John", :age 30}))
  (is (= (get-user 2) {:name "Jane", :age 25})))
```

## Ejercicios prácticos con instrucciones claras
1. Crea una función en Clojure que calcule el área de un círculo, dado su radio.
2. Escribe pruebas unitarias para la función anterior.
3. Crea una función en Clojure que reciba una lista de números y devuelva la suma de los números pares.
4. Escribe pruebas de integración para la función anterior, utilizando una lista de números de prueba.

## Consejos o mejores prácticas
- Utilizar la herramienta REPL para probar y depurar código en tiempo real.
- Escribir pruebas unitarias y de integración para asegurar que el código funcione correctamente.
- Utilizar TDD para escribir las pruebas antes de escribir el código, esto ayuda a identificar posibles errores antes de que sean implementados.
- Utilizar herramientas como `clojure.test` para facilitar la escritura de pruebas.
- Utilizar `assert` y `is` para verificar que los resultados obtenidos sean los esperados.
- Escribir pruebas para casos de prueba extremos o límites, para asegurar que el código maneje correctamente estos casos.

**<- Lección anterior**: [Programación concurrente y paralela](programacion_concurrente_y_paralela.md)

**Siguiente lección ->**: [Desarrollo guiado por pruebas](desarrollo_guiado_por_pruebas.md)
