
## Programación lógica

La programación lógica es un paradigma de programación que se basa en la lógica matemática para resolver problemas. Se centra en la descripción de relaciones entre hechos y reglas lógicas, en lugar de instrucciones secuenciales como en la programación imperativa. En Clojure, este paradigma se implementa a través del lenguaje de programación lógica miniKanren.

### Palabras clave y definiciones

- Paradigma de programación: Un enfoque o modelo de programación que define cómo se estructura y se resuelven problemas en un lenguaje de programación.
- Lógica matemática: Un sistema formal que utiliza símbolos y reglas para representar y manipular proposiciones lógicas.
- MiniKanren: Un lenguaje de programación lógica basado en el cálculo de relaciones que se ejecuta sobre Clojure.

### Preguntas de repaso
- ¿Qué es la programación lógica y en qué se diferencia de la programación imperativa?
- ¿Cuáles son las palabras clave y su definición en el contexto de la programación lógica?
- ¿Qué es miniKanren y cómo se relaciona con Clojure?

### Ejemplos de código en Clojure
Para ilustrar el uso de la programación lógica en Clojure, a continuación se presenta un ejemplo simple de un programa miniKanren que encuentra todas las posibles soluciones para una ecuación de la forma "a + b = c":

```clojure
(require '[clojure.core.logic :as l])

(l/run* [q]
  (l/== q [a b c])
  (l/== a 2)
  (l/== b 3)
  (l/== c (+ a b)))
```

En este código, primero se importa la biblioteca `clojure.core.logic` que contiene las funciones necesarias para trabajar con miniKanren. Luego, se define una variable `q` que representa una lista de tres elementos, `a`, `b` y `c`. A continuación, se establecen las restricciones para `a`, `b` y `c`, donde `a` tiene el valor de 2, `b` tiene el valor de 3 y `c` es igual a `a + b`. La función `l/run*` se encarga de encontrar todas las posibles soluciones para `q` que cumplan con las restricciones establecidas.

### Ejercicios prácticos
1. Escribe un programa miniKanren en Clojure que encuentre todas las posibles soluciones para la ecuación "a * b = 24", donde `a` y `b` son números enteros.
2. Utilizando el mismo programa, modifica las restricciones para que se encuentren todas las parejas de números enteros que sumen un número dado por el usuario.

### Consejos y mejores prácticas
- Al trabajar con miniKanren en Clojure, es importante tener en cuenta que no se está escribiendo código imperativo, sino que se están estableciendo relaciones entre los diferentes elementos.
- Es importante entender cómo se resuelve el cálculo de relaciones en miniKanren para poder escribir programas eficientes y sin errores.
- Una buena práctica es empezar con problemas sencillos y progresivamente ir aumentando la complejidad. Esto ayudará a entender mejor el paradigma de la programación lógica y sus aplicaciones en Clojure.


**<- Lección anterior**: [Protocolos y registros](protocolos_y_registros.md)

**Siguiente lección ->**: [Arquitecturas y patrones de diseño](arquitecturas_y_patrones_de_diseno.md)
