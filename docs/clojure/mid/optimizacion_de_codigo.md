
# Optimización de código en Clojure

En Clojure, como en cualquier otro lenguaje de programación, es importante tener en cuenta la eficiencia y la optimización de nuestro código. Esto no solo nos ayuda a mejorar el rendimiento de nuestras aplicaciones, sino que también puede ahorrar recursos y tiempo de ejecución.

En este módulo, aprenderemos técnicas de optimización de código en Clojure, como lazy evaluation y memoization, para mejorar la eficiencia de nuestras aplicaciones.

## Palabras clave y definiciones

- Lazy evaluation: técnica de evaluación en la que los valores no se calculan hasta que son necesarios, lo que permite ahorrar recursos y mejorar el rendimiento.
- Memoization: técnica de almacenamiento en caché de resultados de funciones para evitar su cálculo repetitivo y mejorar el rendimiento.
- Recursión de cola: técnica de recursión en la que la llamada recursiva es la última operación realizada, lo que permite ahorrar memoria y evitar errores de desbordamiento de pila.

## Preguntas de repaso

1. ¿Qué es lazy evaluation y cómo puede ayudar a optimizar el código en Clojure?
2. ¿En qué consiste la técnica de memoization?
3. ¿Cuál es la diferencia entre recursión de cola y recursión normal?
4. ¿Cuáles son algunos de los beneficios de la optimización de código en Clojure?

## Ejemplos de código en Clojure

### Lazy evaluation

En este ejemplo, se utiliza la función `range` para generar una lista de números del 1 al 10. Sin embargo, gracias a la lazy evaluation, la lista no se generará hasta que se acceda a ella a través de la función `first`.

```
(first (range 1 11)) ; => 1
```

### Memoization

La función `memoize` nos permite almacenar en caché los resultados de una función para evitar su cálculo repetitivo. En este ejemplo, la función `fib` calcula los números de la secuencia de Fibonacci y la función `memoized-fib` utiliza memoization para mejorar su rendimiento.

```
(defn fib [n]
  (if (or (zero? n) (= n 1))
    n
    (+ (fib (- n 1)) (fib (- n 2)))))

(def memoized-fib (memoize fib))

(memoized-fib 10) ; => 55
```

### Recursión de cola

En este ejemplo, la función `sum` utiliza recursión de cola para sumar todos los números de una lista de forma eficiente, evitando errores de desbordamiento de pila.

```
(defn sum [lst acc]
  (if (empty? lst)
    acc
    (recur (rest lst) (+ acc (first lst)))))

(sum (range 1 100000) 0) ; => 4999950000
```

## Ejercicios prácticos

1. Escribe una función que genere una lista de números pares utilizando lazy evaluation.
2. Crea una función `factorial` que utilice memoization para mejorar su rendimiento.
3. Implementa una función que calcule el máximo común divisor de dos números utilizando recursión de cola.

## Consejos y mejores prácticas

- Utiliza lazy evaluation y memoization en funciones que realicen cálculos intensivos o que puedan ser llamadas varias veces con los mismos argumentos.
- Utiliza recursión de cola en lugar de recursión normal para evitar errores de desbordamiento de pila y mejorar el rendimiento.
- Realiza pruebas de rendimiento antes y después de aplicar técnicas de optimización de código para medir su impacto.
- No sacrifiques la legibilidad y la simplicidad del código por optimización excesiva. Es importante encontrar un equilibrio entre eficiencia y claridad del código.

**<- Lección anterior**: [Persistencia de datos](persistencia_de_datos.md)

**Siguiente lección ->**: [Optimización de rendimiento](optimizacion_de_rendimiento.md)