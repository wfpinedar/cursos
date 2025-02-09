
# Módulos

En Elixir, un módulo es una unidad de código que agrupa una serie de funciones relacionadas. Los módulos son una forma de organizar y estructurar el código en Elixir, lo que permite una mejor modularidad, reutilización y mantenibilidad del mismo.

## Palabras clave y su definición

- `defmodule`: se utiliza para definir un nuevo módulo en Elixir.
- `do`: indica el inicio del cuerpo del módulo.
- `end`: indica el final del cuerpo del módulo.
- `def`: se utiliza para definir una función dentro de un módulo.
- `defp`: similar a `def`, pero define una función privada que solo puede ser utilizada dentro del módulo.
- `import`: importa funciones de otros módulos para ser utilizadas en el módulo actual.
- `use`: se utiliza para importar y ejecutar código de otros módulos.
- `alias`: permite crear un alias para un módulo, lo que facilita su uso en el código.

## Preguntas de repaso

1. ¿Qué es un módulo en Elixir?
2. ¿Cuál es la palabra clave utilizada para definir un nuevo módulo?
3. ¿Qué función se utiliza para definir una función dentro de un módulo?
4. ¿Cuál es la diferencia entre `def` y `defp`?
5. ¿Cómo se pueden importar funciones de otros módulos en Elixir?

## Ejemplos de código en Elixir

Definición de un módulo con una función pública y una privada:

```elixir
defmodule Calculadora do
  def suma(a, b) do
    a + b
  end

  defp resta(a, b) do
    a - b
  end
end
```

Importación de un módulo en otro:

```elixir
defmodule Ejemplo do
  import Calculadora

  def promedio(a, b) do
    suma(a, b) / 2
  end
end
```

Alias de un módulo:

```elixir
defmodule Ejemplo do
  alias Calculadora, as: Calc

  def promedio(a, b) do
    Calc.suma(a, b) / 2
  end
end
```

## Ejercicios prácticos

1. Crea un módulo llamado `Conversion` que contenga dos funciones: `fahrenheit_to_celsius` y `celsius_to_fahrenheit`, que conviertan entre estas dos unidades de temperatura.
2. Importa el módulo `Conversion` en otro módulo y utiliza sus funciones para imprimir la conversión de 32°F a °C y de 100°C a °F.

## Consejos o mejores prácticas

- Utilizar los módulos para agrupar funciones relacionadas y mantener un código más organizado y legible.
- Utilizar nombres descriptivos para los módulos y sus funciones.
- Evitar la definición de funciones con el mismo nombre en diferentes módulos, ya que puede causar conflictos.
- Utilizar la función `defp` para definir funciones que solo serán utilizadas dentro del módulo.
- Utilizar la importación selectiva de funciones con la palabra clave `only` para evitar importar todas las funciones de un módulo.
- Utilizar la función `use` para importar y ejecutar código de otros módulos, por ejemplo, para definir comportamientos y macros.
- Utilizar un alias para un módulo largo o de uso frecuente para un código más conciso y legible.

### Navegación de lecciones

**<- Lección anterior**: [Recursividad](recursividad.md)

**Siguiente lección ->**: [Módulos de la librería estándar de Elixir](modulos_de_la_libreria_estandar_de_elixir.md)

