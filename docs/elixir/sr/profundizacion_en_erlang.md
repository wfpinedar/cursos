
# Profundización en Erlang

En esta lección, profundizaremos en el lenguaje de programación Erlang y su relación con Elixir. Conocer en detalle Erlang es fundamental para comprender plenamente Elixir, ya que este último se basa en gran medida en el primero.

## Explicación teórica

Erlang es un lenguaje de programación funcional y concurrente, desarrollado en la década de 1980 por Ericsson para ser utilizado en sus sistemas de telecomunicaciones. Una de las características principales de Erlang es su capacidad para manejar procesos concurrentes de forma eficiente y segura, lo que lo hace ideal para aplicaciones en tiempo real y distribuidas.

Elixir, por otro lado, es un lenguaje de programación funcional que se ejecuta en la máquina virtual de Erlang (BEAM). Esto significa que el código escrito en Elixir se compila a bytecode y se ejecuta en la misma máquina virtual que los programas escritos en Erlang. Elixir aprovecha las características de concurrencia y tolerancia a fallos de Erlang y las hace accesibles a los desarrolladores a través de una sintaxis más amigable y moderna.

## Palabras clave y su definición

- Función: Un bloque de código que realiza una tarea específica y devuelve un valor.
- Patrón: Una expresión utilizada para hacer coincidir valores y estructuras de datos.
- Término: Cualquier valor en el lenguaje Erlang, incluyendo átomos, enteros, flotantes, strings, listas y tuplas.
- Proceso: Una unidad de ejecución concurrente en Erlang que se comunica con otros procesos a través de mensajes.
- Módulo: Una colección de funciones y datos relacionados en Erlang.
- OTP (Open Telecom Platform): Una colección de librerías y herramientas utilizadas para construir aplicaciones robustas y escalables en Erlang.

## Preguntas de repaso

1. ¿Qué es Erlang y cuál es su relación con Elixir?
2. ¿Qué característica principal de Erlang lo hace ideal para aplicaciones en tiempo real y distribuidas?
3. ¿En qué máquina virtual se ejecuta el código escrito en Elixir?
4. ¿Qué es un patrón en Erlang?
5. ¿Qué es OTP y para qué se utiliza en Erlang?

## Ejemplos de código en Elixir

```elixir
# Ejemplo de una función en Elixir
defmodule Calculator do
  def add(a, b) do
    a + b
  end
end

# Ejemplo de un patrón en Erlang
{ok, result} = Calculator.add(2, 3)

# Ejemplo de un proceso en Erlang
spawn(fn -> IO.puts("Hello from a process!") end)
```

## Ejercicios prácticos

1. Crea una función en Elixir que calcule el área de un círculo dado su radio.
2. Utiliza un patrón en Erlang para hacer coincidir una lista con los primeros tres elementos iguales.
3. Crea un proceso en Erlang que imprima "I'm alive!" cada 3 segundos.

## Consejos o mejores prácticas

- Estudia la sintaxis y características de Erlang para poder aprovechar al máximo las capacidades de Elixir.
- Utiliza patrones y funciones de forma eficiente para manejar la concurrencia en tus aplicaciones.
- Aprende y utiliza las librerías y herramientas de OTP para construir aplicaciones robustas y escalables en Erlang.


### Navegación de lecciones

**Siguiente lección ->**: [Arquitectura de sistemas Elixir](arquitectura_de_sistemas_elixir.md)
