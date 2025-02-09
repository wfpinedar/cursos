
# Desarrollo de aplicaciones concurrentes

## Explicación teórica

En Elixir, la concurrencia se refiere a la capacidad de ejecutar múltiples procesos al mismo tiempo. Esto es posible gracias al modelo de concurrencia de Elixir, basado en el modelo de actores. En este modelo, los procesos se comunican entre sí enviando y recibiendo mensajes, lo que permite una comunicación eficiente y segura entre procesos.

La concurrencia es esencial en el desarrollo de aplicaciones escalables y distribuidas, ya que permite aprovechar al máximo los recursos del sistema y mejorar el rendimiento de la aplicación. Además, en Elixir la concurrencia se logra de forma natural, ya que los procesos son ligeros y se crean y destruyen de manera eficiente.

Para desarrollar aplicaciones concurrentes en Elixir, es importante entender los diferentes patrones y técnicas que ofrece el lenguaje. Algunos de los más comunes son:

- Supervisor: se encarga de iniciar, supervisar y reiniciar procesos en caso de que falle.
- GenServer: se utiliza para crear procesos que mantienen un estado y pueden recibir y enviar mensajes.
- Task: permite ejecutar tareas en segundo plano de forma asíncrona.
- Agent: se utiliza para gestionar el estado de una sola entidad de forma concurrente.

## Palabras clave y su definición

- Concurrencia: capacidad de ejecutar múltiples procesos al mismo tiempo.
- Modelo de actores: modelo de concurrencia basado en el envío y recepción de mensajes entre procesos.
- Proceso: unidad de ejecución en Elixir.
- Mensaje: forma de comunicación entre procesos en el modelo de actores.
- Escalabilidad: capacidad de una aplicación de crecer y adaptarse a un aumento en la demanda de recursos.
- Distribución: capacidad de una aplicación de ejecutarse en múltiples nodos o máquinas.

## Preguntas de repaso

1. ¿Qué es la concurrencia y por qué es importante en el desarrollo de aplicaciones?
2. ¿Cómo se logra la concurrencia en Elixir?
3. ¿Cuáles son algunos de los patrones y técnicas que se utilizan en Elixir para desarrollar aplicaciones concurrentes?
4. ¿Qué es el modelo de actores y cómo se relaciona con la concurrencia en Elixir?
5. ¿Cuál es la diferencia entre escalabilidad y distribución en el contexto de aplicaciones concurrentes?

## Ejemplos de código en Elixir

1. Ejemplo de creación de un proceso con Supervisor:

```elixir
defmodule MiProceso do
  use GenServer

  # funciones de GenServer
end

defmodule MiSupervisor do
  use Supervisor

  def start_link do
    Supervisor.start_link(__MODULE__, [])
  end

  def init(_) do
    children = [
      worker(MiProceso, [])
    ]
    supervise(children, strategy: :one_for_one)
  end
end
```

2. Ejemplo de uso de GenServer para crear un proceso que mantiene un contador:

```elixir
defmodule Contador do
  use GenServer

  def start_link do
    GenServer.start_link(__MODULE__, 0)
  end

  def inc do
    GenServer.cast(__MODULE__, :inc)
  end

  def handle_cast(:inc, count) do
    {:noreply, count + 1}
  end
end
```

## Ejercicios prácticos con instrucciones claras

1. Crea un supervisor que supervise un proceso que mantenga una lista de nombres. El proceso debe tener las funciones `add/1` para agregar un nombre a la lista, `remove/1` para eliminar un nombre de la lista y `get_all/0` para obtener la lista completa.

2. Crea un GenServer que mantenga un contador y tenga las funciones `increment/0` para aumentar el contador en 1 y `get_count/0` para obtener el valor actual del contador.

3. Utiliza el módulo Task para ejecutar una función en segundo plano y obtener su resultado.

## Consejos o mejores prácticas

- Utiliza el modelo de actores de forma adecuada, enviando mensajes y evitando el uso de variables compartidas.
- Utiliza supervisores para gestionar la creación y reinicio de procesos en caso de fallos.
- Utiliza patrones como GenServer y Agent para gestionar el estado de forma concurrente.
- Evita bloquear procesos con operaciones costosas, como llamadas a la base de datos, y utiliza tareas en segundo plano si es necesario.

**<- Lección anterior**: [Composición de procesos](composicion_de_procesos.md)

**Siguiente lección ->**: [Desarrollo de aplicaciones de tiempo real](desarrollo_de_aplicaciones_de_tiempo_real.md)
