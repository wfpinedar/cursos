
Funciones

Las funciones son uno de los conceptos fundamentales en Elixir, ya que permiten encapsular lógica y reutilizarla en diferentes partes de un programa. Una función es un bloque de código que recibe argumentos y devuelve un resultado. En Elixir, se definen utilizando la palabra clave "def" seguida del nombre de la función y sus argumentos entre paréntesis. Luego, se utiliza la palabra clave "do" para indicar el inicio del cuerpo de la función, y el resultado se obtiene con la palabra clave "end".

Palabras clave y su definición:

1. def: palabra clave utilizada para definir una función en Elixir.
2. do: palabra clave utilizada para indicar el inicio del cuerpo de una función.
3. end: palabra clave utilizada para indicar el fin del cuerpo de una función.
4. función: bloque de código que recibe argumentos y devuelve un resultado.
5. argumentos: valores que se pasan a una función para ser procesados.
6. resultado: valor devuelto por una función después de procesar los argumentos.

Preguntas de repaso:

1. ¿Qué es una función en Elixir?
2. ¿Cómo se define una función en Elixir?
3. ¿Qué son los argumentos de una función?
4. ¿Qué es el resultado de una función?
5. ¿Cuáles son las palabras clave utilizadas para definir una función en Elixir?

Ejemplos de código en Elixir:

1. Definir una función que sume dos números:

```
def sumar(a, b) do
  a + b
end
```

2. Definir una función que multiplique un número por sí mismo:

```
def cuadrado(x) do
  x * x
end
```

Ejercicios prácticos:

1. Escribir una función que calcule el área de un círculo, utilizando la fórmula A = πr². La función debe recibir el radio como argumento y devolver el área como resultado.

```
def area_circulo(r) do
  3.14 * r * r
end
```

2. Escribir una función que convierta grados Celsius a Fahrenheit, utilizando la fórmula F = (C * 9/5) + 32. La función debe recibir la temperatura en grados Celsius como argumento y devolver la temperatura en grados Fahrenheit como resultado.

```
def celsius_a_fahrenheit(c) do
  (c * 9/5) + 32
end
```

Consejos o mejores prácticas:

1. Utilizar nombres descriptivos para las funciones, que indiquen claramente su propósito.
2. Evitar funciones con un número excesivo de argumentos, ya que dificultan la comprensión y el mantenimiento del código.
3. Utilizar patrones en los argumentos de las funciones para manejar diferentes casos y mejorar la legibilidad.
4. Utilizar comentarios para explicar el propósito y funcionamiento de una función.
5. Probar y depurar las funciones individualmente antes de integrarlas en el resto del programa.