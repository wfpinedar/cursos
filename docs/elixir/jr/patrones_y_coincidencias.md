
# Patrones y coincidencias

## Descripción del módulo

En este módulo, aprenderás sobre los patrones y coincidencias en Elixir, y cómo se utilizan en la programación funcional. Los patrones y coincidencias son una parte fundamental de la sintaxis de Elixir y te permiten escribir código limpio y conciso, además de facilitar el manejo de datos y estructuras complejas.

## Explicación teórica

En Elixir, los patrones y coincidencias se utilizan para comparar valores y estructuras de datos, y ejecutar cierto código en función de si se cumple o no la coincidencia. Se basa en la idea de la descomposición de datos, donde una estructura de datos se puede descomponer en partes más pequeñas y se pueden realizar operaciones en cada una de ellas.

El patrón de coincidencia se escribe como una expresión regular y se utiliza en conjunto con la palabra clave `match`. Para que la coincidencia sea exitosa, los valores deben coincidir en cada parte del patrón.

## Palabras clave y su definición

- Patrón: una expresión regular utilizada para comparar valores y estructuras de datos.
- Coincidencia: la acción de comparar un valor con un patrón y determinar si hay una correspondencia.
- Descomposición de datos: el proceso de dividir una estructura de datos en partes más pequeñas.
- `match`: palabra clave utilizada para realizar una coincidencia entre un patrón y un valor.

## Preguntas de repaso

1. ¿Qué son los patrones y coincidencias en Elixir?
2. ¿Para qué se utilizan los patrones y coincidencias?
3. ¿Qué es la descomposición de datos?
4. ¿Cuál es la palabra clave utilizada para realizar una coincidencia en Elixir?

## Ejemplos de código en Elixir

### Ejemplo 1: Comparando valores simples

```elixir
value = 5
match value do
  5 -> "Cinco"
  _ -> "No es cinco"
end
# Output: "Cinco"
```

En este ejemplo, se asigna el valor `5` a la variable `value` y se realiza una coincidencia con el patrón `5`. Como el valor coincide con el patrón, se ejecuta el código correspondiente y se devuelve "Cinco". Si el valor fuera diferente de `5`, se ejecutaría el código en el `_` (comodín) y devolvería "No es cinco".

### Ejemplo 2: Descomposición de tuplas

```elixir
tuple = {:ok, "¡Éxito!"}
match tuple do
  {:ok, message} -> "Mensaje de éxito: #{message}"
  {:error, _} -> "Ha ocurrido un error"
end
# Output: "Mensaje de éxito: ¡Éxito!"
```

En este ejemplo, se tiene una tupla con dos elementos y se realiza una coincidencia con dos patrones diferentes. Si el primer elemento de la tupla es `:ok`, se asigna el segundo elemento a la variable `message` y se devuelve un mensaje de éxito. Si el primer elemento es `:error`, se ejecuta el código en el segundo patrón y se devuelve un mensaje de error.

## Ejercicios prácticos con instrucciones claras

1. Escribe un código que compare un número con los siguientes patrones:
    - Si el número es mayor que 10, devolver "Mayor que 10"
    - Si el número es menor que 5, devolver "Menor que 5"
    - Si el número es igual a 7, devolver "Número mágico"
    - Si no se cumple ninguna de las condiciones anteriores, devolver "Número desconocido"

2. Escribe un código que compare una lista con los siguientes patrones:
    - Si la lista tiene 3 elementos, devolver la palabra "Tres"
    - Si la lista tiene 5 elementos, devolver la palabra "Cinco"
    - Si la lista tiene 8 elementos, devolver la palabra "Ocho"
    - Si no se cumple ninguna de las condiciones anteriores, devolver "Número de elementos desconocido"

## Consejos o mejores prácticas

- Utiliza patrones y coincidencias en lugar de declaraciones `if/else` cuando sea posible, ya que es una forma más concisa y legible de escribir código.
- Practica la descomposición de datos y utiliza patrones más complejos para manejar estructuras de datos más grandes.
- Utiliza el comodín `_` cuando no necesites asignar un valor a una variable en un patrón de coincidencia.
- Aprovecha la capacidad de Elixir para realizar coincidencias en diferentes tipos de datos, como listas, mapas y tuplas. 

### Navegación de lecciones

**<- Lección anterior**: [Listas y tuplas](listas_y_tuplas.md)

**Siguiente lección ->**: [Procesos](procesos.md)
