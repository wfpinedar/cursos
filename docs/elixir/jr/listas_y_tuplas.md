
# Listas y tuplas en Elixir

## Introducción

En Elixir, las listas y tuplas son dos de las estructuras de datos más utilizadas. Aunque pueden parecer similares, tienen diferentes características y se utilizan para diferentes propósitos. En esta lección, exploraremos en profundidad las listas y tuplas en Elixir, cómo se crean, modifican y utilizan en la programación.

## Listas

Las listas en Elixir son una colección ordenada de elementos del mismo tipo o de diferentes tipos. Se crean utilizando corchetes y separando los elementos con comas.

```elixir
list = [1, 2, 3, 4]
```

Las listas son estructuras de datos dinámicas, lo que significa que se pueden modificar agregando o eliminando elementos. Para agregar un elemento al final de la lista, se utiliza el operador `++`:

```elixir
list ++ [5]
```

Esto devolverá una nueva lista con el elemento agregado al final. Para eliminar un elemento de la lista, se utiliza el operador `--`:

```elixir
list -- [3]
```

Esto devolverá una nueva lista sin el elemento especificado. También se pueden agregar o eliminar múltiples elementos a la vez utilizando el mismo operador.

Otra característica importante de las listas en Elixir es que se pueden acceder a sus elementos mediante su índice, comenzando desde 0. Esto se hace utilizando el operador de acceso `[]` seguido del índice del elemento deseado:

```elixir
list = ["a", "b", "c", "d"]
list[2] # Devuelve "c"
```

## Tuplas

Las tuplas en Elixir son una colección ordenada de elementos del mismo tipo o de diferentes tipos, al igual que las listas. Sin embargo, a diferencia de las listas, las tuplas son estructuras de datos inmutables, lo que significa que no se pueden modificar una vez creadas. Se crean utilizando llaves y separando los elementos con comas.

```elixir
tuple = {:ok, "Hola", 1}
```

Aunque las tuplas no se pueden modificar, se pueden acceder a sus elementos de la misma manera que en las listas, utilizando el operador de acceso `[]` seguido del índice del elemento deseado:

```elixir
tuple = {:ok, "Hola", 1}
tuple[1] # Devuelve "Hola"
```

## Palabras clave

- Listas: colecciones ordenadas de elementos en Elixir que se pueden modificar.
- Tuplas: colecciones ordenadas de elementos en Elixir que no se pueden modificar.
- Dinámico: en el contexto de las estructuras de datos, se refiere a la capacidad de ser modificadas.
- Inmutable: en el contexto de las estructuras de datos, se refiere a la incapacidad de ser modificadas.

## Preguntas de repaso

1. ¿Cuál es la diferencia principal entre las listas y tuplas en Elixir?
2. ¿Cómo se crean las listas y tuplas en Elixir?
3. ¿Cómo se pueden modificar las listas en Elixir?
4. ¿Cómo se accede a los elementos de una tupla en Elixir?
5. ¿Cuál es la principal ventaja de utilizar una tupla en lugar de una lista?

## Ejemplos de código

### Creación de listas y tuplas

```elixir
list = [1, 2, 3, 4]
tuple = {:ok, "Hola", 1}
```

### Modificación de listas

```elixir
list ++ [5] # Devuelve [1, 2, 3, 4, 5]
list -- [3] # Devuelve [1, 2, 4]
```

### Acceso a elementos de una tupla

```elixir
tuple = {:ok, "Hola", 1}
tuple[1] # Devuelve "Hola"
```

## Ejercicios prácticos

1. Crea una lista con los números del 1 al 10 y agrega el número 11 al final.
2. Crea una tupla con tres elementos y modifica el segundo elemento para que sea "adiós" en lugar de "Hola".
3. Dado el siguiente código, ¿cuál es el resultado de `tuple[3]`?

```elixir
tuple = {:ok, "Hola", [1, 2, 3], true}
```

## Consejos y mejores prácticas

- Utiliza listas cuando necesites una estructura de datos que pueda ser modificada.
- Utiliza tuplas cuando necesites una estructura de datos inmutable para almacenar valores que no cambiarán.
- Si necesitas una estructura de datos que pueda ser modificada pero también necesitas acceder a sus elementos por índice, considera utilizar una lista y convertirla a una tupla cuando sea necesario acceder a sus elementos por índice.

### Navegación de lecciones

**<- Lección anterior**: [Sintaxis básica](sintaxis_basica.md)

**Siguiente lección ->**: [Patrones y coincidencias](patrones_y_coincidencias.md)

