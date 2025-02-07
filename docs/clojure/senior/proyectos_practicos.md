
# Proyectos prácticos

Este módulo se enfoca en la aplicación práctica de los conocimientos adquiridos en Clojure. A través de la realización de proyectos, podrás consolidar y mejorar tus habilidades en este lenguaje de programación funcional.

## Explicación teórica

Los proyectos prácticos son una forma efectiva de poner en práctica los conceptos aprendidos en Clojure y mejorar tus habilidades de programación. Al trabajar en proyectos, podrás enfrentarte a problemas reales y encontrar soluciones utilizando las características y herramientas de Clojure.

Además, los proyectos prácticos te ayudarán a entender mejor la sintaxis y la estructura del lenguaje, así como también a familiarizarte con las librerías y frameworks disponibles.

## Palabras clave y su definición

- Proyectos prácticos: Son actividades de programación en las que se aplican los conocimientos adquiridos en Clojure para resolver problemas reales o crear aplicaciones útiles.
- Lenguaje de programación funcional: Un paradigma de programación en el que los programas se construyen a partir de funciones, evitando el uso de estados y mutabilidad.
- Sintaxis: Reglas y estructuras utilizadas para escribir código en un lenguaje de programación.
- Librerías: Conjunto de funciones y herramientas que se pueden utilizar para realizar tareas específicas en un lenguaje de programación.
- Frameworks: Conjunto de librerías y herramientas que proporcionan una base para desarrollar aplicaciones de manera más eficiente.

## Preguntas de repaso

1. ¿Por qué es importante realizar proyectos prácticos en Clojure?
2. ¿Qué es un lenguaje de programación funcional?
3. ¿Cuál es la diferencia entre una librería y un framework en Clojure?
4. ¿Qué son las librerías y frameworks más utilizadas en Clojure?
5. ¿Cómo pueden los proyectos prácticos ayudarte a mejorar tus habilidades en este lenguaje?

## Ejemplos de código en Clojure

### Ejemplo 1: Función que calcula el factorial de un número

```clojure
(defn factorial [n]
  (if (<= n 1)
    1
    (* n (factorial (- n 1)))))
```

### Ejemplo 2: Función que ordena una lista de números de menor a mayor

```clojure
(defn ordenar [lst]
  (if (empty? lst)
    lst
    (let [pivot (first lst)
          smaller (filter #(< % pivot) (rest lst))
          greater (filter #(> % pivot) (rest lst))]
      (concat (ordenar smaller) (list pivot) (ordenar greater)))))
```

## Ejercicios prácticos

1. Crea una función en Clojure que reciba una lista de números y devuelva la suma de todos ellos.
2. Escribe una función que reciba una lista de palabras y devuelva una nueva lista con las palabras en mayúsculas.
3. Crea un programa en Clojure que permita al usuario ingresar un número y luego imprima todos los números pares menores o iguales a ese número.
4. Utilizando la librería `clojure.string`, desarrolla una función que reciba una cadena de texto y devuelva la misma cadena pero con todas las vocales reemplazadas por asteriscos.
5. Crea un pequeño juego en Clojure en el que el usuario deba adivinar un número aleatorio generado por el programa. El juego debe indicar si el número ingresado es mayor o menor al número a adivinar, y terminar cuando el usuario adivine el número correcto.

## Consejos o mejores prácticas

- Comienza con proyectos sencillos y ve aumentando la complejidad a medida que adquieras más habilidades en Clojure.
- Utiliza las librerías y frameworks disponibles para ahorrar tiempo y mejorar la eficiencia en tus proyectos.
- No tengas miedo de experimentar y probar nuevas formas de resolver problemas en Clojure.
- Busca proyectos de código abierto en Clojure y contribuye con tu conocimiento y habilidades en la comunidad.
- Siempre revisa y refactoriza tu código para hacerlo más legible y eficiente.

**<- Lección anterior**: [Integración con otros lenguajes y plataformas](integracion_con_otros_lenguajes_y_plataformas.md)

**Siguiente lección ->**: [Desarrollo en equipo y buenas prácticas](desarrollo_en_equipo_y_buenas_practicas.md)
