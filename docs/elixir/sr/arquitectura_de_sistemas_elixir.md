
# Arquitectura de sistemas Elixir

La arquitectura de sistemas en Elixir se refiere al proceso de diseñar y construir sistemas complejos en este lenguaje de programación funcional. Esto incluye la elección de patrones y arquitecturas adecuadas para garantizar la escalabilidad, robustez y mantenibilidad del sistema. En esta lección, aprenderemos los conceptos básicos de la arquitectura de sistemas en Elixir y cómo aplicarlos en la práctica.

## Teoría

Elixir es un lenguaje de programación funcional que se ejecuta en la máquina virtual de Erlang (BEAM). Por lo tanto, hereda ciertas características de Erlang que lo hacen ideal para construir sistemas distribuidos y tolerantes a fallos. A continuación, se explican los conceptos clave de la arquitectura de sistemas Elixir:

- **Supervisión**: Elixir utiliza el modelo de supervisión para manejar la escalabilidad y tolerancia a fallos en el sistema. En lugar de intentar prevenir los fallos, Elixir asume que estos sucederán y proporciona herramientas para manejarlos de manera efectiva. Los supervisores son procesos que se encargan de monitorear y reiniciar otros procesos en caso de que falle alguno de ellos.
- **OTP**: OTP (Open Telecom Platform) es un conjunto de librerías y herramientas que vienen incluidas en Elixir y que proporcionan una base sólida para construir sistemas distribuidos y tolerantes a fallos. Incluye patrones y arquitecturas comunes, como el modelo de actores y el sistema de supervisión.
- **Modelo de actores**: Elixir se basa en el modelo de actores, donde cada proceso es un actor que se comunica con otros a través de mensajes. Esto permite una comunicación asíncrona y paralelismo en el sistema.
- **Arquitecturas de sistemas**: Elixir ofrece diferentes patrones y arquitecturas para diseñar sistemas complejos, como el modelo de actores puro, el modelo de actores supervisados, y el modelo de procesos de fondo (GenServer). La elección de la arquitectura adecuada dependerá de los requisitos y características del sistema a construir.

## Palabras clave y definiciones

- **Supervisión**: modelo utilizado en Elixir para manejar la escalabilidad y tolerancia a fallos en el sistema.
- **OTP**: conjunto de librerías y herramientas incluidas en Elixir para construir sistemas distribuidos y tolerantes a fallos.
- **Modelo de actores**: modelo de programación en el que cada proceso se comunica con otros a través de mensajes.
- **Arquitecturas de sistemas**: patrones y modelos utilizados para diseñar sistemas complejos en Elixir.

## Preguntas de repaso

1. ¿Qué es la supervisión en Elixir y para qué se utiliza?
2. ¿Qué es OTP y qué incluye?
3. ¿En qué se basa el modelo de actores en Elixir?
4. ¿Cuáles son algunas de las arquitecturas de sistemas disponibles en Elixir?

## Ejemplos de código

A continuación, se muestra un ejemplo de código en Elixir utilizando el modelo de actores y la supervisión:

```
# Definir un supervisor
defmodule Supervisor do
  use Supervisor

  # Definir la estrategia de reinicio en caso de fallos
  def start_link do
    Supervisor.start_link(__MODULE__, [], name: :supervisor)
  end

  # Definir los procesos a supervisar
  def init(_) do
    children = [
      supervisor(Task, [[name: :worker1], [name: :worker2]], restart: :temporary)
    ]
    supervise(children, strategy: :one_for_one)
  end
end

# Definir un proceso que se supervisará
defmodule Worker do
  def start_link(name) do
    Task.start_link(fn -> do_some_work(name) end)
  end

  defp do_some_work(name) do
    IO.puts "Trabajando en #{name}"
    :timer.sleep(1000)
    raise "Algo salió mal en #{name}"
  end
end

# Iniciar el supervisor y los procesos supervisados
Supervisor.start_link
Worker.start_link(:worker1)
Worker.start_link(:worker2)
```

En este ejemplo, se define un supervisor que se encarga de monitorear dos procesos llamados `worker1` y `worker2`. Si alguno de estos procesos falla, el supervisor los reiniciará automáticamente. Esto permite que el sistema siga funcionando a pesar de los fallos en los procesos individuales.

## Ejercicios prácticos

1. Crea un supervisor que se encargue de monitorear un proceso llamado `database` que se encarga de manejar la conexión con la base de datos.
2. Utiliza el modelo de actores para crear un sistema que administre una cola de tareas utilizando la librería `Task`.
3. Implementa una arquitectura basada en GenServer para crear un sistema de chat en tiempo real utilizando el módulo `GenServer` y la librería `Phoenix`.

## Consejos y mejores prácticas

- Utiliza el modelo de actores y la supervisión para garantizar la escalabilidad y tolerancia a fallos en el sistema.
- Aprovecha las herramientas y patrones proporcionados por OTP para construir sistemas distribuidos y tolerantes a fallos.
- Elige la arquitectura adecuada para cada sistema, teniendo en cuenta sus requisitos y características.

### Navegación de lecciones

**<- Lección anterior**: [Profundización en Erlang](profundizacion_en_erlang.md)

**Siguiente lección ->**: [Desarrollo de aplicaciones de alta concurrencia y alto rendimiento](optimizacion_de_aplicaciones_de_alto_rendimiento.md)

