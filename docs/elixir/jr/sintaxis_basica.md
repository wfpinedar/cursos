
## Sintaxis básica

En esta lección, aprenderemos la sintaxis básica de Elixir, un lenguaje de programación funcional y concurrente que se ejecuta en la máquina virtual de Erlang. Elixir es conocido por su sintaxis clara y concisa, lo que lo hace fácil de aprender y leer.

### Tipos de datos

En Elixir, existen varios tipos de datos básicos, incluyendo enteros, decimales, booleanos, átomos, cadenas de texto y listas. Los enteros pueden ser positivos o negativos y no tienen un límite de tamaño. Los decimales se representan con un punto decimal y pueden ser de doble precisión. Los booleanos pueden tener dos valores: `true` o `false`. Los átomos son constantes que representan un valor único, como un identificador o una etiqueta. Las cadenas de texto se representan entre comillas dobles y pueden contener cualquier carácter. Las listas son colecciones ordenadas de elementos, que pueden ser de cualquier tipo de datos.

### Operadores

Elixir tiene los operadores básicos de suma `+`, resta `-`, multiplicación `*`, división `/` y módulo `%`. También cuenta con los operadores de comparación `==`, `!=`, `<`, `>`, `<=` y `>=` para comparar valores. Además, existen operadores lógicos como `and`, `or` y `not` para evaluar expresiones booleanas.

### Estructuras de control

Las estructuras de control en Elixir incluyen condicionales, bucles y funciones. Los condicionales se utilizan para ejecutar un bloque de código si se cumple una determinada condición, y se pueden anidar utilizando la palabra clave `else`. Los bucles se utilizan para repetir un bloque de código hasta que se cumpla una condición, y pueden ser de tipo `while` o `for`. Las funciones son bloques de código que se pueden llamar en cualquier momento y pueden tener parámetros y valores de retorno.

### Palabras clave

- `def`: define una función.
- `do`: indica el inicio de un bloque de código.
- `end`: indica el final de un bloque de código.
- `if`: inicia una estructura condicional.
- `else`: indica un bloque de código alternativo en una estructura condicional.
- `while`: inicia un bucle que se repetirá mientras se cumpla una condición.
- `for`: inicia un bucle que se repetirá por cada elemento de una lista.
- `and`: operador lógico que evalúa si ambas expresiones son verdaderas.
- `or`: operador lógico que evalúa si al menos una de las expresiones es verdadera.
- `not`: operador lógico que niega una expresión.

### Preguntas de repaso

1. ¿Cuáles son los tipos de datos básicos en Elixir?
2. ¿Cómo se representan los decimales en Elixir?
3. ¿Qué palabra clave se utiliza para definir una función?
4. ¿Qué operador se utiliza para comparar valores?
5. ¿Qué estructura de control se utiliza para repetir un bloque de código mientras se cumpla una condición?

### Ejemplos de código

```
# Definición de una función que suma dos números
def sum(a, b) do
  a + b
end

# Uso de la función
result = sum(5, 3)
IO.puts("El resultado es #{result}")
# Salida: El resultado es 8

# Estructura condicional
if age >= 18 do
  IO.puts("Eres mayor de edad")
else
  IO.puts("Eres menor de edad")
end

# Bucle while
i = 1
while i <= 5 do
  IO.puts("Contador: #{i}")
  i = i + 1
end
# Salida:
# Contador: 1
# Contador: 2
# Contador: 3
# Contador: 4
# Contador: 5

# Bucle for
for num <- [1, 2, 3] do
  IO.puts("Número: #{num}")
end
# Salida:
# Número: 1
# Número: 2
# Número: 3
```

### Ejercicios prácticos

1. Escribe una función que calcule el área de un triángulo (base x altura / 2).
2. Utiliza un bucle for para imprimir los números del 1 al 10.
3. Escribe una función que verifique si un número es par o impar.

### Consejos

- Utiliza nombres de variables y funciones descriptivos para que sea más fácil entender tu código.
- Aprovecha la concisión de la sintaxis de Elixir para escribir código más legible y mantenible.
- Practica la resolución de problemas utilizando estructuras de control y funciones en Elixir para familiarizarte con su uso.

### Navegación de lecciones

**<- Lección anterior**: [Introducción a Elixir](introduccion_a_elixir.md)

**Siguiente lección ->**: [Listas y tuplas](listas_y_tuplas.md)

