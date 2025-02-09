
# Programación funcional avanzada

En este módulo, profundizaremos en los conceptos de la programación funcional en Elixir. La programación funcional es un paradigma de programación que se basa en el uso de funciones puras, es decir, funciones que no tienen efectos secundarios y siempre devuelven el mismo resultado para los mismos argumentos. En Elixir, la programación funcional es una parte fundamental de su diseño y permite escribir código más conciso, mantenible y escalable.

## Funciones de orden superior

Las funciones de orden superior son aquellas que pueden tomar otras funciones como argumentos o retornar funciones como resultado. En Elixir, esto se logra gracias a que las funciones son "ciudadanos de primera clase", lo que significa que pueden ser tratadas como cualquier otro valor. Algunas de las funciones de orden superior más comunes en Elixir son `Enum.map`, `Enum.filter` y `Enum.reduce`, que permiten aplicar una función a cada elemento de una lista, filtrar elementos basado en una condición y reducir una lista en un solo valor, respectivamente.

## Funciones anónimas

Las funciones anónimas son funciones que no tienen un nombre definido y se pueden crear en tiempo de ejecución. En Elixir, se denotan con una sintaxis especial que utiliza el operador `&` seguido de una lista de argumentos y una expresión. Por ejemplo, `&(&1 * 2)` representa una función anónima que multiplica su primer argumento por 2. Las funciones anónimas son muy útiles en combinación con las funciones de orden superior, ya que permiten definir una función "ad hoc" para su uso en una operación específica.

## Módulos de funciones

Los módulos de funciones son una forma de agrupar funciones relacionadas en un mismo archivo. En Elixir, un módulo de funciones se define con la palabra clave `defmodule` seguida del nombre del módulo y su contenido se delimita por la palabra clave `do` y `end`. Dentro de un módulo de funciones, se pueden definir tanto funciones públicas como privadas. Las funciones públicas se pueden llamar desde fuera del módulo, mientras que las privadas solo se pueden llamar desde dentro del módulo.

## Palabras clave y su definición

- Programación funcional: paradigma de programación basado en el uso de funciones puras.
- Función pura: función que no tiene efectos secundarios y siempre devuelve el mismo resultado para los mismos argumentos.
- Función de orden superior: función que puede tomar otras funciones como argumentos o retornar funciones como resultado.
- Función anónima: función sin un nombre definido que se puede crear en tiempo de ejecución.
- Módulo de funciones: agrupación de funciones relacionadas en un mismo archivo.

## Preguntas de repaso

1. ¿Qué es la programación funcional y por qué es importante en Elixir?
2. ¿Qué son las funciones de orden superior y cuáles son algunos ejemplos en Elixir?
3. ¿Cómo se denotan las funciones anónimas en Elixir?
4. ¿Qué ventajas tienen los módulos de funciones en Elixir?

## Ejemplos de código en Elixir

### Función de orden superior

```elixir
# Función que toma una función como argumento y la aplica a cada elemento de una lista
lista = [1, 2, 3, 4]
doble = fn x -> x * 2 end
Enum.map(lista, doble) # output: [2, 4, 6, 8]
```

### Función anónima

```elixir
# Función que calcula el área de un círculo utilizando una función anónima
area_circulo = fn r -> &math.pi * r ^ 2 end
area_circulo.(2) # output: 12.566370614359172
```

### Módulo de funciones

```elixir
# Módulo que contiene funciones para trabajar con números
defmodule MiModulo do
  # Función pública para sumar dos números
  def sumar(a, b) do
    a + b
  end

  # Función privada para calcular el cuadrado de un número
  defp cuadrado(x) do
    x * x
  end
end

MiModulo.sumar(2, 3) # output: 5
MiModulo.cuadrado(4) # error: función privada no accesible desde fuera del módulo
```

## Ejercicios prácticos

1. Crea una función de orden superior que tome una lista de números y devuelva una lista con los números pares.
2. Define una función anónima que multiplique su argumento por 10 y aplícala a una lista de números.
3. Crea un módulo de funciones con una función pública para calcular el área de un triángulo y una función privada para calcular su perímetro.

## Consejos o mejores prácticas

- Utiliza funciones puras en la mayor medida posible para escribir código más fácil de entender y depurar.
- Utiliza funciones de orden superior para evitar repeticiones de código y hacerlo más modular.
- Utiliza funciones anónimas cuando necesites definir una función temporal o ad hoc.
- Agrupa funciones relacionadas en módulos para facilitar su organización y reutilización.

### Navegación de lecciones

No hay lección anterior

**Siguiente lección ->**: [Composición de procesos](composicion_de_procesos.md)


