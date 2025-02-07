
# Colecciones en Clojure

Las colecciones son estructuras de datos fundamentales en Clojure que permiten almacenar y manipular múltiples valores de forma eficiente. Son inmutables, lo que significa que no se pueden modificar una vez creadas, pero se pueden crear nuevas colecciones a partir de las existentes mediante operaciones de transformación.

## Palabras clave y definiciones

- **Listas:** estructuras de datos secuenciales y ordenadas que pueden contener cualquier tipo de valor. Se crean con la función `list` o utilizando la sintaxis `'(elemento1 elemento2 ...)`.
- **Vectores:** estructuras de datos secuenciales y ordenadas que se pueden acceder eficientemente por índice. Se crean con la función `vector` o utilizando la sintaxis `[elemento1 elemento2 ...]`.
- **Conjuntos:** estructuras de datos no ordenadas que no permiten duplicados. Se crean con la función `set` o utilizando la sintaxis `#{elemento1 elemento2 ...}`.
- **Mapas:** estructuras de datos que asocian claves con valores. Se crean con la función `hash-map` o utilizando la sintaxis `{:clave1 valor1 :clave2 valor2 ...}`.

## Preguntas de repaso

1. ¿Qué son las colecciones en Clojure?
2. ¿Cuáles son las características de las colecciones en Clojure?
3. ¿Qué funciones se utilizan para crear listas, vectores, conjuntos y mapas?
4. ¿Cómo se puede acceder a un elemento de un vector en Clojure?
5. ¿Qué diferencia hay entre un conjunto y un mapa en Clojure?

## Ejemplos de código

### Creación de listas

```clojure
(def lista1 (list 1 2 3)) ; utilizando la función list
(def lista2 '(4 5 6)) ; utilizando la sintaxis
```

### Creación de vectores

```clojure
(def vector1 (vector 1 2 3)) ; utilizando la función vector
(def vector2 [4 5 6]) ; utilizando la sintaxis
```

### Creación de conjuntos

```clojure
(def set1 (set [1 2 3])) ; utilizando la función set
(def set2 #{4 5 6}) ; utilizando la sintaxis
```

### Creación de mapas

```clojure
(def mapa1 (hash-map :nombre "Juan" :edad 30)) ; utilizando la función hash-map
(def mapa2 {:nombre "María" :edad 25}) ; utilizando la sintaxis
```

## Ejercicios prácticos

1. Crea una lista que contenga los números del 1 al 10.
2. Crea un vector con los días de la semana.
3. Crea un conjunto con los colores del arcoíris.
4. Crea un mapa que asocie nombres de frutas con su precio.
5. Utiliza la función `conj` para agregar un elemento a un conjunto existente.
6. Utiliza la función `assoc` para agregar una nueva clave y valor a un mapa existente.

## Consejos y mejores prácticas

- Utiliza listas para datos que se acceden secuencialmente y no necesitas acceder por índice.
- Utiliza vectores para datos que necesitas acceder por índice.
- Utiliza conjuntos para datos que no necesitan un orden específico y no permiten duplicados.
- Utiliza mapas para datos que necesitas asociar claves con valores.
- Utiliza la sintaxis abreviada siempre que sea posible para crear colecciones.
- Utiliza las funciones de transformación como `map`, `filter` y `reduce` para manipular colecciones de forma funcional.
- Evita modificar colecciones existentes, en su lugar crea nuevas colecciones a partir de ellas.


**<- Lección anterior**: [Funciones y recursión](funciones_y_recursion.md)

**Siguiente lección ->**: [Control de flujo y estructuras de control](control_de_flujo_y_estructuras_de_control.md)