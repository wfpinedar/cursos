
# Recursividad

## Descripción del módulo:

La recursividad es un concepto fundamental en la programación funcional y es especialmente importante en Elixir, ya que este lenguaje se basa en el paradigma funcional. En este módulo, aprenderemos qué es la recursividad, cómo funciona y cómo se implementa en Elixir. También veremos algunos ejemplos de código y ejercicios prácticos para afianzar los conocimientos adquiridos.

## Explicación teórica:

La recursividad es una técnica de programación en la que una función se llama a sí misma para resolver un problema. Esto permite resolver problemas más complejos dividiéndolos en problemas más pequeños y más simples. La recursividad es similar a un bucle, pero en lugar de repetir el mismo código una y otra vez, se llama a la función recursiva hasta que se alcanza un caso base que detiene la recursividad.

La recursividad tiene dos componentes importantes: el caso base y el caso recursivo. El caso base es la condición que detiene la recursividad, mientras que el caso recursivo es la llamada a la función recursiva para resolver el problema en términos más pequeños.

## Palabras clave y su definición:

- Recursividad: técnica de programación en la que una función se llama a sí misma para resolver un problema.
- Caso base: condición que detiene la recursividad.
- Caso recursivo: llamada a la función recursiva para resolver el problema en términos más pequeños.

## Preguntas de repaso:

1. ¿Qué es la recursividad?
2. ¿Cuáles son los dos componentes importantes de la recursividad?
3. ¿Qué es el caso base?
4. ¿Qué es el caso recursivo?

## Ejemplos de código en Elixir:

### Ejemplo 1: Factorial

El factorial de un número n se define como n! = n * (n-1) * (n-2) * ... * 1. Veamos cómo se puede implementar esta función de forma recursiva en Elixir:

```elixir
def factorial(n) do
  if n == 1 do
    1
  else
    n * factorial(n-1)
  end
end
```

### Ejemplo 2: Fibonacci

La secuencia de Fibonacci es una serie de números en la que cada número es la suma de los dos anteriores. Por ejemplo, los primeros 10 números de la secuencia son: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34. Veamos cómo se puede implementar esta función de forma recursiva en Elixir:

```elixir
def fibonacci(n) do
  if n == 0 or n == 1 do
    n
  else
    fibonacci(n-1) + fibonacci(n-2)
  end
end
```

## Ejercicios prácticos con instrucciones claras:

1. Escribe una función recursiva para calcular la suma de los primeros n números naturales.
2. Escribe una función recursiva para calcular el máximo común divisor (MCD) de dos números.
3. Escribe una función recursiva para invertir una lista.

## Consejos o mejores prácticas:

- Asegúrate de tener un caso base para detener la recursividad, de lo contrario, la función se llamará infinitamente.
- Utiliza la recursividad cuando sea la solución más simple y elegante para un problema.
- Evita la recursividad en casos en los que la iteración sea más eficiente, ya que la recursividad puede ser más costosa en términos de tiempo y memoria.

### Navegación de lecciones

**<- Lección anterior**: [Concurrencia](concurrencia.md)

**Siguiente lección ->**: [Módulos](modulos.md)

