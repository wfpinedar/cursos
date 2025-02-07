
# Control de flujo y estructuras de control

## Explicación teórica

El control de flujo en un programa se refiere a la capacidad de dirigir la ejecución del código en diferentes direcciones, dependiendo de ciertas condiciones o situaciones. En Clojure, existen diversas estructuras de control que nos permiten controlar el flujo de ejecución, como if, while y for.

La estructura de control "if" nos permite ejecutar un bloque de código si se cumple una determinada condición. En caso de que no se cumpla, se puede incluir un bloque "else" con un código alternativo. Esta estructura se utiliza para tomar decisiones en el programa, por ejemplo, si una variable es mayor o menor que un valor determinado.

La estructura de control "while" nos permite ejecutar un bloque de código mientras se cumpla una condición específica. Esto nos permite repetir una acción hasta que se alcance un resultado deseado.

La estructura de control "for" se utiliza para iterar sobre una colección de datos, ejecutando un bloque de código para cada elemento de la colección. Esto nos permite trabajar con listas, vectores, mapas y otros tipos de datos de manera más eficiente.

## Palabras clave y su definición

- if: Estructura de control que permite ejecutar un bloque de código si se cumple una determinada condición.
- else: Palabra clave utilizada en conjunción con "if", que permite incluir un bloque de código alternativo en caso de que no se cumpla la condición.
- while: Estructura de control que permite ejecutar un bloque de código mientras se cumpla una condición específica.
- for: Estructura de control utilizada para iterar sobre una colección de datos y ejecutar un bloque de código para cada elemento de la colección.

## Preguntas de repaso

1. ¿Qué es el control de flujo en un programa?
2. ¿Qué estructura de control se utiliza para tomar decisiones en un programa?
3. ¿Cuál es la diferencia entre "if" y "while" en Clojure?
4. ¿Qué es lo que hace la estructura de control "for"?
5. ¿Cuál es la palabra clave utilizada en conjunción con "if" para incluir un bloque de código alternativo?

## Ejemplos de código en Clojure

```clojure
;; Ejemplo de estructura "if"
(def edad 25)
(if (< edad 18)
  (println "Eres menor de edad")
  (println "Eres mayor de edad"))

;; Ejemplo de estructura "while"
(def contador 0)
(while (< contador 5)
  (println contador)
  (def contador (inc contador)))

;; Ejemplo de estructura "for"
(def numeros [1 2 3 4 5])
(for [num numeros]
  (println (* num 2)))
```

## Ejercicios prácticos con instrucciones claras

1. Utilizando la estructura "if", crea una función que reciba como parámetro el número de un mes y devuelva el nombre del mes correspondiente. Si el número no está entre 1 y 12, mostrar un mensaje de error.
2. Utilizando la estructura "while", crea una función que reciba como parámetro un número y muestre por pantalla todos los números pares desde 0 hasta ese número.
3. Utilizando la estructura "for", crea una función que reciba como parámetro una lista de palabras y devuelva una lista con las mismas palabras en mayúsculas.

## Consejos o mejores prácticas

- Utilizar correctamente las estructuras de control para mejorar la eficiencia y legibilidad del código.
- Evitar anidar demasiadas estructuras de control, ya que puede hacer el código difícil de entender y mantener.
- Utilizar nombres descriptivos para las variables y parámetros en las estructuras de control, para que sea más fácil de entender su función en el código.

### Navegación de lecciones

**<- Lección anterior**: [Colecciones](colecciones.md)

**Siguiente lección ->**: [Programación funcional](programacion_funcional.md)