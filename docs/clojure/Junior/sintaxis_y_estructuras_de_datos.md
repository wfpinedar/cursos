
# Sintaxis y estructuras de datos en Clojure

## Explicación teórica
Clojure es un lenguaje de programación funcional que se basa en la sintaxis de Lisp. Esto significa que su sintaxis es simple y consiste en listas de datos que se pueden manipular y evaluar utilizando funciones. En Clojure, todo es una lista, incluso las estructuras de datos más complejas, como los mapas y vectores. Esto permite una gran flexibilidad y expresividad en la escritura de código.

Las estructuras de datos en Clojure son inmutables, lo que significa que no se pueden cambiar una vez que se han creado. En lugar de eso, se crean nuevas versiones de la estructura de datos al aplicar funciones a ellas. Esto ayuda a prevenir errores y hace que el código sea más seguro y fácil de entender.

### Estructura de un programa en Clojure
Un programa en Clojure está compuesto por una serie de expresiones, que pueden ser datos, operaciones o estructuras de control. Estas expresiones están organizadas en una lista, que se llama "forma". La forma se evalúa y devuelve un resultado.

Para definir una forma en Clojure, utilizamos paréntesis y separamos cada elemento con un espacio. Por ejemplo: `(def x 10)` define una forma llamada "x" con el valor de 10.

## Palabras clave y su definición
- Lista: una estructura de datos en Clojure que contiene una secuencia de elementos ordenados.
- Vector: similar a una lista, pero se accede a los elementos mediante índices numéricos.
- Mapa: una estructura de datos que contiene pares clave-valor, similar a un diccionario en otros lenguajes de programación.
- Sintaxis: conjunto de reglas para escribir código en un lenguaje de programación.
- Forma: lista de expresiones que se evalúan y devuelven un resultado.
- Inmutable: una propiedad de las estructuras de datos en Clojure que significa que no se pueden cambiar una vez creadas.
- Función: una secuencia de instrucciones que realizan una tarea específica y pueden ser aplicadas a estructuras de datos.

## Preguntas de repaso
1. ¿Qué es la sintaxis en Clojure?
2. ¿Qué significa que las estructuras de datos en Clojure sean inmutables?
3. ¿Qué son las funciones en Clojure?
4. ¿Cómo se accede a los elementos en un vector?
5. ¿Cómo se accede a los valores en un mapa?
6. ¿Qué es una forma en Clojure?

### Tipos de datos
Clojure cuenta con varios tipos de datos, entre ellos:
- Números: enteros, decimales y fracciones.
- Strings: cadenas de texto.
- Booleanos: verdadero o falso.
- Listas: colección ordenada de elementos.
- Vectores: colección ordenada de elementos, pero de acceso más rápido que las listas.
- Mapas: colección de pares clave-valor.
- Sets: colección de elementos únicos.

### Operadores
En Clojure, podemos utilizar operadores para realizar operaciones matemáticas, comparaciones y otras tareas. Algunos de los operadores más comunes son:
- Aritméticos: `+`, `-`, `*`, `/`
- Comparación: `=`, `<`, `>`, `<=`, `>=`
- Lógicos: `and`, `or`, `not`

### Estructuras de control
Las estructuras de control nos permiten controlar el flujo de nuestro código. Algunas de las más utilizadas en Clojure son:
- `if`: evalúa una expresión y, si es verdadera, ejecuta un bloque de código. Si es falsa, ejecuta otro bloque de código.
- `when`: similar a `if`, pero solo ejecuta un bloque de código si la expresión es verdadera.
- `cond`: evalúa una serie de expresiones y ejecuta el bloque de código de la primera que sea verdadera.
- `loop`: ejecuta un bloque de código varias veces hasta que se cumpla una condición.
- `recur`: permite que una función se llame a sí misma de forma recursiva.

## Ejemplos de código en Clojure
### Crear una lista
```clojure
(def lista-numeros [1 2 3 4 5])
```

### Crear un vector
```clojure
(def vector-nombres ["Ana" "Juan" "María"])
```

### Crear un mapa
```clojure
(def mapa-edades {:Ana 26 :Juan 30 :María 28})
```

### Acceder a elementos en un vector
```clojure
(nth vector-nombres 1) ; devuelve "Juan"
```

### Acceder a valores en un mapa
```clojure
(get mapa-edades :María) ; devuelve 28
```

## Ejercicios prácticos
1. Crea una lista con tus colores favoritos y muestra el primer y último elemento.
2. Crea un vector con los nombres de tus amigos y agrega tu nombre al final.
3. Crea un mapa con las edades de tus familiares y muestra la edad de tu hermano/a.
4. Crea una función que tome una lista de números y devuelva la suma de todos ellos.
5. Crea una función que tome un mapa con nombres y edades y devuelva una lista de nombres ordenados alfabéticamente.

## Consejos o mejores prácticas
- Utiliza nombres significativos para tus variables y estructuras de datos. Esto hará que tu código sea más fácil de entender y mantener.
- Aprovecha la inmutabilidad de las estructuras de datos en Clojure y evita modificarlas directamente.
- Utiliza las funciones integradas en Clojure para manipular tus estructuras de datos en lugar de escribir tu propio código.
- Practica la escritura de código funcional en lugar de imperativo, ya que es la forma más común de programar en Clojure.
- Aprende sobre las funciones de orden superior, como `map` y `filter`, para escribir código más conciso y elegante.


### Navegación de lecciones

**<- Lección anterior**: [Instalación y configuración](instalacion_y_configuracion.md)

**Siguiente lección ->**: [Funciones y recursión](funciones_y_recursion.md)

