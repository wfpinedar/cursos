
# Macros y metaprogramación

En Clojure, una macro es una función especial que toma código como entrada y devuelve código como salida. A diferencia de una función regular, una macro se ejecuta en tiempo de compilación en lugar de tiempo de ejecución, lo que permite generar código personalizado y optimizado para una determinada situación.

Las macros son una herramienta poderosa en Clojure que permite a los desarrolladores crear abstracciones y automatizar tareas repetitivas. Además, la metaprogramación, que es el proceso de escribir código que genera código, se vuelve posible gracias a las macros.

## Palabras clave

- Macros: Funciones especiales que se ejecutan en tiempo de compilación y devuelven código como salida.
- Metaprogramación: Proceso de escribir código que genera código.
- Abstracción: Técnica de programación que permite ocultar detalles complejos detrás de una interfaz simple y fácil de usar.
- Expansión: Proceso en el que una macro se ejecuta y devuelve código que reemplaza la llamada a la macro en tiempo de compilación.

## Preguntas de repaso

1. ¿Qué es una macro y cómo se diferencia de una función regular?
2. ¿Qué es la metaprogramación y cómo se relaciona con las macros?
3. ¿Cuál es la diferencia entre una macro y una abstracción?
4. ¿En qué momento se ejecuta una macro?
5. ¿Qué es la expansión de una macro y cuándo ocurre?

## Ejemplos de código en Clojure

Una macro en Clojure se define utilizando la palabra clave `defmacro` seguida del nombre de la macro y los parámetros que toma como entrada. Por ejemplo:

```clojure
(defmacro suma [a b]
  `(+ ~a ~b))
```

En este ejemplo, la macro `suma` toma dos parámetros `a` y `b` y devuelve una expresión que suma los dos valores. La expresión `(+ ~a ~b)` se llama una lista literal y se utiliza para construir una expresión que se evaluará en tiempo de compilación.

Para utilizar la macro, se llama a `suma` de la misma manera que una función regular, pero en este caso, el código devuelto por la macro se expandirá en tiempo de compilación. Por ejemplo:

```clojure
(suma 2 3) ; devuelve 5
```

## Ejercicios prácticos

### Ejercicio 1: Crear una macro para definir constantes

En este ejercicio, se te pedirá que crees una macro llamada `defconst` que tome dos parámetros: el nombre de la constante y su valor. La macro deberá definir una constante con el nombre y valor proporcionados. Por ejemplo:

```clojure
(defconst PI 3.14159)
```

Pasos a seguir:

1. Crea una macro llamada `defconst` que tome dos parámetros: `nombre` y `valor`.
2. Utiliza la lista literal para construir una expresión que defina la constante utilizando el nombre y valor proporcionados.
3. Expande la macro utilizando la función `def` para definir la constante.
4. Prueba tu macro utilizando diferentes valores y asegúrate de que se defina correctamente la constante.

### Ejercicio 2: Crear una macro para generar funciones

En este ejercicio, se te pedirá que crees una macro llamada `defn-super` que genere una función que siempre devuelve el número 10. Esta función se utilizará en situaciones en las que se requiere una función de prueba rápida o un valor de relleno. Por ejemplo:

```clojure
(defn-super sumar [a b] (+ a b)) ; devuelve siempre 10
```

Pasos a seguir:

1. Crea una macro llamada `defn-super` que tome como parámetros el nombre de la función y los parámetros de entrada.
2. Utiliza la lista literal para construir una expresión que defina la función y siempre devuelva el número 10.
3. Expande la macro utilizando la función `defn` para definir la función.
4. Prueba tu macro utilizando diferentes nombres de función y asegúrate de que siempre devuelva 10.

## Consejos y mejores prácticas

- Utiliza macros con moderación. Aunque son una herramienta poderosa, su uso excesivo puede dificultar la comprensión y el mantenimiento del código.
- Es importante documentar adecuadamente las macros para que otros desarrolladores puedan entender su funcionamiento y propósito.
- Al utilizar la metaprogramación, asegúrate de que el código generado sea válido y seguro para su ejecución.

**<- Lección anterior**: [Estructuras de datos avanzadas](estructuras_de_datos_avanzadas.md)

**Siguiente lección ->**: [Transducers y reducers](transducers_y_reducers.md)
