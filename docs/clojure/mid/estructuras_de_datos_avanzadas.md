
# Estructuras de datos avanzadas en Clojure

## Explicación teórica
Clojure es un lenguaje de programación funcional que se basa en la idea de que los datos y las funciones son tratados de la misma manera. Esto significa que las estructuras de datos son fundamentales en Clojure, ya que permiten almacenar y manipular información de manera eficiente.

Las estructuras de datos en Clojure son inmutables, lo que significa que no se pueden modificar una vez que han sido creadas. En lugar de eso, se crean nuevas versiones de la estructura de datos, lo que garantiza una mayor seguridad y consistencia en el código.

En este módulo, nos enfocaremos en las estructuras de datos más avanzadas en Clojure, que incluyen conjuntos, árboles y secuencias infinitas. Estas estructuras de datos tienen características únicas y proporcionan formas más eficientes de almacenar y manipular información en programas complejos.

## Palabras clave y su definición
- Conjuntos: una estructura de datos que almacena elementos de forma desordenada y no permite elementos duplicados.
- Árboles: una estructura de datos jerárquica que consta de nodos conectados por relaciones padre-hijo.
- Secuencias infinitas: una estructura de datos que permite la generación de una secuencia de elementos de forma infinita.

## Preguntas de repaso
1. ¿Qué significa que las estructuras de datos en Clojure sean inmutables?
2. ¿Cuál es la diferencia entre una estructura de datos ordenada y una desordenada?
3. ¿Qué es un árbol binario?
4. ¿Cuál es la ventaja de usar secuencias infinitas en programas complejos?

## Ejemplos de código en Clojure
### Conjuntos
```clojure
(def conjunto (hash-set 1 2 3 4 5)) ; creación de un conjunto con elementos
(conjunto 2) ; acceso al elemento "2"
(conjunto 6) ; el resultado es nil ya que no existe el elemento "6" en el conjunto
(conjunto 3 4 5) ; creación de un nuevo conjunto con elementos del conjunto original
```

### Árboles
```clojure
(def árbol {:raíz "A"
            :hijo-izquierdo {:raíz "B"
                             :hijo-izquierdo {:raíz "D"}
                             :hijo-derecho {:raíz "E"}}
            :hijo-derecho {:raíz "C"
                           :hijo-izquierdo {:raíz "F"}}) ; creación de un árbol
(get-in árbol [:hijo-izquierdo :hijo-izquierdo :raíz]) ; acceso al elemento "D"
(assoc-in árbol [:hijo-derecho :hijo-derecho] {:raíz "G"}) ; actualización del árbol con un nuevo elemento
```

### Secuencias infinitas
```clojure
(def numeros (iterate inc 1)) ; creación de una secuencia infinita de números
(take 10 numeros) ; toma los primeros 10 elementos de la secuencia
(filter even? numeros) ; filtro para obtener solo los números pares de la secuencia
(take 5 (drop 10 numeros)) ; toma los primeros 5 elementos después de los primeros 10 de la secuencia
```

## Ejercicios prácticos
1. Crea un conjunto con los números del 1 al 10 y comprueba si el número 8 está incluido en él.
2. Crea un árbol binario con letras del alfabeto y accede al último elemento.
3. Crea una secuencia infinita de números pares y calcula la suma de los primeros 20 elementos.

## Consejos o mejores prácticas
- Utiliza conjuntos cuando necesites almacenar elementos de forma desordenada y evitar duplicados.
- Utiliza árboles cuando necesites almacenar datos jerárquicamente.
- Utiliza secuencias infinitas cuando necesites trabajar con una gran cantidad de datos de forma eficiente.
- Siempre utiliza funciones de alto orden como `map`, `filter` y `reduce` para manipular estructuras de datos en lugar de recorrerlas manualmente.


**Siguiente lección ->**: [Funciones de orden superior](funciones_de_orden_superior.md)