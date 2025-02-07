
# Funciones y Recursión

## Teoría
En Clojure, las funciones son un elemento fundamental y poderoso de su lenguaje de programación funcional. Son bloques de código que pueden recibir datos, procesarlos y devolver un resultado. Las funciones en Clojure son objetos de primera clase, lo que significa que pueden ser asignadas a variables, pasadas como argumentos y devueltas como resultado de otras funciones.

En Clojure, una función es una expresión que toma uno o más argumentos y devuelve un resultado. Las funciones en Clojure son inmutables, lo que significa que una vez definidas, no pueden ser modificadas.

La recursión es una técnica de programación en la que una función se llama a sí misma para resolver un problema. En Clojure, la recursión se utiliza para iterar sobre estructuras de datos y realizar operaciones repetitivas.

## Palabras clave

- Función: Una expresión que toma uno o más argumentos y devuelve un resultado.
- Parámetros: Variables que se utilizan para recibir datos en una función.
- Retorno: El resultado que devuelve una función después de procesar los datos recibidos.
- Objetos de primera clase: Elementos que pueden ser asignados a variables, pasados como argumentos y devueltos como resultado de otras funciones.
- Recursión: Técnica de programación en la que una función se llama a sí misma para resolver un problema.
- Inmutabilidad: Característica de las funciones en Clojure que indica que no pueden ser modificadas una vez definidas.

## Preguntas de repaso

1. ¿Qué es una función en Clojure?
2. ¿Qué es la recursión y para qué se utiliza en Clojure?
3. ¿Cuál es la característica de las funciones en Clojure que las hace diferentes de otros lenguajes de programación?

## Ejemplos de código en Clojure

1. Definición de una función simple:

```clojure
(defn suma [a b]
  (+ a b))

; llamada a la función
(suma 5 3) ; resultado:8
```

```clojure
; Declaración de una función que devuelve el cuadrado de un número
(defn cuadrado [num]
  (* num num))

; Llamada a la función
(cuadrado 4) ; resultado: 16
```

2. Ejemplo de recursión para calcular el factorial de un número:

```clojure
(defn factorial [n]
  (if (= n 0)
    1
    (* n (factorial (- n 1)))))
```

## Ejercicios prácticos

1. Escribe una función en Clojure que calcule el área de un círculo, utilizando la fórmula `π * r^2` donde `r` es el radio.
2. Utiliza recursión para definir una función en Clojure que calcule la suma de los primeros `n` números naturales.
3. Escribe una función que determine si un número es par o impar y devuelva "par" o "impar" respectivamente.
4. Escribe una función que reciba una lista de palabras y devuelva una lista con las mismas palabras en mayúsculas.

## Consejos o mejores prácticas

- Utiliza nombres descriptivos para tus funciones.
- Evita la recursión infinita definiendo un caso base en tus funciones recursivas.
- Utiliza la función `recur` en lugar de la llamada a sí misma para optimizar el rendimiento de tus funciones recursivas.
- Aprovecha las funciones de orden superior para escribir código más conciso y legible.

### Navegación de lecciones

**<- Lección anterior**: [Sintaxis y estructuras de datos](sintaxis_y_estructuras_de_datos.md)

**Siguiente lección ->**: [Colecciones](colecciones.md)