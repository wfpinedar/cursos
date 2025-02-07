
# Funciones de orden superior en Clojure

## Explicación teórica

Las funciones de orden superior son aquellas que reciben como argumento o devuelven como resultado otras funciones. Esto permite una mayor flexibilidad en la programación y una forma más elegante y legible de escribir código.

En Clojure, las funciones son ciudadanos de primera clase, lo que significa que pueden ser tratadas como cualquier otro valor. Por lo tanto, las funciones de orden superior son una parte fundamental del lenguaje.

## Palabras clave y su definición

- Función de orden superior: función que recibe como argumento o devuelve como resultado otra función.
- Función anónima: función sin nombre que puede ser asignada a una variable o pasada como argumento a otra función.
- Map: función de orden superior que aplica una función a cada elemento de una colección y devuelve una nueva colección con los resultados.
- Filter: función de orden superior que filtra una colección según una condición dada y devuelve una nueva colección con los elementos que cumplen dicha condición.
- Reduce: función de orden superior que combina todos los elementos de una colección en un único valor, utilizando una función de combinación.

## Preguntas de repaso

1. ¿Qué son las funciones de orden superior?
2. ¿Por qué son importantes en Clojure?
3. ¿Qué es una función anónima?
4. ¿Cuál es la diferencia entre map, filter y reduce?
5. ¿Cómo se pueden utilizar las funciones de orden superior para escribir código más legible y elegante?

## Ejemplos de código en Clojure

### Función anónima

```clojure
;; Función anónima que suma dos números
(fn [x y] (+ x y))

;; Asignar la función a una variable
(defn suma [x y] (+ x y))

;; Pasar la función como argumento a otra función
(map (fn [x] (+ x 1)) [1 2 3 4]) ;; devuelve [2 3 4 5]
```

### Map

```clojure
;; Aplicar una función a cada elemento de una colección
(map #(* % 2) [1 2 3 4]) ;; devuelve [2 4 6 8]
```

### Filter

```clojure
;; Filtrar una colección según una condición
(filter even? [1 2 3 4]) ;; devuelve [2 4]
```

### Reduce

```clojure
;; Combinar todos los elementos de una colección en un único valor
(reduce + [1 2 3 4]) ;; devuelve 10
```

## Ejercicios prácticos con instrucciones claras

1. Escribe una función de orden superior que tome una colección de números y devuelva una nueva colección con el cuadrado de cada número.
2. Utiliza la función filter para obtener solo los números pares de una colección de números.
3. Escribe una función de orden superior que tome una colección de cadenas y devuelva una nueva colección con la primera letra de cada cadena en mayúscula.

## Consejos o mejores prácticas

- Utiliza funciones anónimas cuando necesites una función rápida y sencilla.
- Utiliza map, filter y reduce en lugar de bucles for o while cuando sea posible, ya que son más eficientes y expresivos.
- Utiliza nombres descriptivos para tus funciones de orden superior para hacer tu código más legible y comprensible.


**<- Lección anterior**: [Estructuras de datos avanzadas](estructuras_de_datos_avanzadas.md)

**Siguiente lección ->**: [Programación funcional avanzada](programacion_funcional_avanzada.md)
