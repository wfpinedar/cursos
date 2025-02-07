
# Programación funcional avanzada

## Explicación teórica

La programación funcional es un paradigma de programación que se basa en el uso de funciones como elementos fundamentales del código. En Clojure, un lenguaje de programación funcional basado en lenguaje Lisp, se pueden utilizar funciones de orden superior, recursividad y composición de funciones para crear programas más eficientes y elegantes.

Las funciones de orden superior son aquellas que pueden tomar otras funciones como argumentos y devolver funciones como resultado. Son una herramienta poderosa en la programación funcional, ya que permiten crear funciones más genéricas y reutilizables. Algunos ejemplos de funciones de orden superior en Clojure son `map`, `filter` y `reduce`.

La recursividad es una técnica en la que una función se llama a sí misma hasta que se cumple una condición de salida. En Clojure, se puede utilizar la recursividad para resolver problemas de manera elegante y eficiente, especialmente aquellos que involucran estructuras de datos recursivas como listas y árboles.

La composición de funciones es otra técnica importante en la programación funcional que consiste en combinar varias funciones para crear una nueva función. Esto permite construir programas de manera modular y componer funciones más complejas a partir de funciones más simples.

## Palabras clave y su definición
- Programación funcional: paradigma de programación basado en el uso de funciones como elementos fundamentales del código.
- Funciones de orden superior: funciones que pueden tomar otras funciones como argumentos y devolver funciones como resultado.
- Recursividad: técnica en la que una función se llama a sí misma hasta que se cumple una condición de salida.
- Composición de funciones: técnica en la que se combinan varias funciones para crear una nueva función.

## Preguntas de repaso
1. ¿Qué es la programación funcional y cuál es su principal característica?
2. ¿Qué son las funciones de orden superior y por qué son útiles?
3. ¿En qué consiste la recursividad y en qué situaciones se puede utilizar?
4. ¿Qué es la composición de funciones y cuál es su ventaja en la programación funcional?

## Ejemplos de código en Clojure
```clojure
; Ejemplo de función de orden superior
(defn sum [a b]
  (+ a b))

(defn operate [f a b]
  (f a b))

(operate sum 5 3) ; devuelve 8

; Ejemplo de recursividad
(defn factorial [n]
  (if (< n 2)
    1
    (* n (factorial (- n 1)))))

(factorial 5) ; devuelve 120

; Ejemplo de composición de funciones
(defn add [x]
  (+ x 1))

(defn multiply [x]
  (* x 2))

(defn add-and-multiply [x]
  (-> x
      add
      multiply))

(add-and-multiply 5) ; devuelve 12
```

## Ejercicios prácticos
1. Crea una función de orden superior que tome una lista de números y devuelva una lista con los números pares.
2. Utiliza la recursividad para calcular la suma de los números de una lista.
3. Crea una función que combine dos listas en una sola utilizando composición de funciones.

## Consejos o mejores prácticas
- Utiliza funciones de orden superior para crear funciones más genéricas y reutilizables.
- Ten cuidado con la recursividad infinita, asegúrate siempre de tener una condición de salida.
- Utiliza la composición de funciones para crear programas modulares y fáciles de mantener.

**<- Lección anterior**: [Funciones de orden superior](funciones_de_orden_superior.md)

**Siguiente lección ->**: [Programación concurrente y paralela](programacion_concurrente_y_paralela.md)
