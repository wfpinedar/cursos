
# Programación funcional

La programación funcional es un estilo de programación que se basa en el uso de funciones como bloques de construcción fundamentales en el desarrollo de software. En lugar de modificar datos, la programación funcional se enfoca en crear funciones que toman datos de entrada y producen una salida, sin efectos secundarios en otros datos o variables. Esta forma de programar se basa en los principios de la programación declarativa y en el uso de expresiones y funciones puras.

## Palabras clave
- Funciones puras: son funciones que siempre producen el mismo resultado para una misma entrada y no tienen efectos secundarios en otras variables o datos.
- Inmutabilidad: se refiere a la característica de los datos o variables que no pueden ser modificados después de su creación.
- Recursividad: es la técnica de llamar a una función a sí misma para resolver un problema de manera iterativa.
- Composición de funciones: es la combinación de dos o más funciones para obtener una nueva función.

## Preguntas de repaso
1. ¿Qué es la programación funcional?
2. ¿Cuáles son los principios de la programación funcional?
3. ¿Qué son las funciones puras?
4. ¿Qué es la inmutabilidad?
5. ¿Cuál es la técnica utilizada en la programación funcional para resolver problemas de manera iterativa?
6. ¿Qué es la composición de funciones?

## Ejemplos de código en Clojure
```clojure
; función pura
(defn suma [x y]
  (+ x y))

; inmutabilidad
(def lista [1 2 3]) ; lista original
; (conj lista 4) ; agregando un elemento a la lista original
(conj [1 2 3] 4) ; creando una nueva lista con el elemento agregado

; recursividad
(defn factorial [n]
  (if (<= n 1)
    1
    (* n (factorial (- n 1)))))

; composición de funciones
(defn duplicar [x]
  (* x 2))

(defn sumar-uno [x]
  (+ x 1))

(defn duplicar-y-sumar [x]
  (duplicar (sumar-uno x)))
```

## Ejercicios prácticos
1. Crea una función que tome un número como parámetro y devuelva su cuadrado.
2. Crear una función que calcule el área de un círculo.
3. Crea una función recursiva que calcule el factorial de un número.
4. Crea una función que tome una lista de números y devuelva una nueva lista con el doble de cada elemento.
5. Utiliza la composición de funciones para crear una función que tome una lista de números y devuelva una nueva lista con el doble de cada elemento y luego le sume 10 a cada uno.

## Consejos y mejores prácticas
- Utiliza funciones puras siempre que sea posible para evitar efectos secundarios y hacer que tu código sea más fácil de entender y depurar.
- Aprovecha la inmutabilidad de los datos en Clojure para evitar errores y mejorar la eficiencia de tu código.
- Utiliza la recursividad en lugar de bucles para resolver problemas de manera iterativa.
- Practica la composición de funciones para crear funciones más complejas a partir de funciones más simples.
- Evita la mutación de datos y variables en tu código, en su lugar, utiliza la función `let` para crear nuevas variables con valores modificados a partir de las originales.

### Navegación de lecciones

**<- Lección anterior**: [Control de flujo y estructuras de control](control_de_flujo_y_estructuras_de_control.md)

**Siguiente lección ->**: [Gestión de errores y depuración](gestion_de_errores_y_depuracion.md)