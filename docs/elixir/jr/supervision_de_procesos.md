
# Supervisión de procesos

## Teoría

En Elixir, cada proceso es independiente y puede comunicarse con otros procesos mediante el envío de mensajes. Sin embargo, los procesos pueden fallar debido a errores en el código o en el sistema. Para mantener la estabilidad del sistema, Elixir cuenta con un sistema de supervisión de procesos que permite manejar los errores de forma eficiente.

La supervisión de procesos se basa en el principio de "let it crash", lo que significa que un proceso debe fallar de forma controlada y ser reiniciado por su supervisor en lugar de intentar atrapar todos los errores y seguir ejecutando. Esto permite que el sistema se recupere de forma más rápida y evita que los errores se propaguen a otros procesos.

Cada proceso en Elixir es supervisado por un supervisor, que es un proceso especial que se encarga de iniciar, reiniciar y detener otros procesos. Los supervisores se organizan en una jerarquía, donde un supervisor puede tener a su cargo otros supervisores y procesos. Esto permite una mayor granularidad en el manejo de errores y una mejor escalabilidad del sistema.

En caso de que un proceso falle, su supervisor puede tomar diferentes acciones dependiendo del tipo de error y su gravedad. Por ejemplo, puede reiniciar el proceso, detenerlo completamente o incluso reiniciar todo el árbol de procesos que está supervisando.

## Palabras clave y definiciones

- Proceso: Es una unidad de ejecución independiente en Elixir, que puede comunicarse con otros procesos mediante el envío de mensajes.
- Supervisión: Es el proceso de monitorear y manejar los errores en un sistema de procesos.
- Supervisor: Es un proceso especial encargado de iniciar, reiniciar y detener otros procesos.
- Jerarquía de supervisión: Es la estructura en la que los supervisores se organizan, permitiendo una mejor escalabilidad y manejo de errores.
- Let it crash: Es el principio en el que se basa la supervisión de procesos en Elixir, que consiste en dejar que un proceso falle de forma controlada y ser reiniciado por su supervisor.

## Preguntas de repaso

1. ¿Qué es la supervisión de procesos en Elixir?
2. ¿Por qué se utiliza el principio de "let it crash" en la supervisión de procesos?
3. ¿Cómo se organizan los supervisores en Elixir?
4. ¿Qué acciones puede tomar un supervisor en caso de que un proceso falle?
5. ¿Cuál es la función de un supervisor en el sistema de supervisión de procesos?

## Ejemplos de código

### Definición de un supervisor

```
defmodule MiApp.Supervisor do
  use Supervisor

  def start_link do
    Supervisor.start_link(__MODULE__, [])
  end

  def init(_) do
    children = [
      worker(MiApp.Worker, []) # Se agrega un proceso "worker" al supervisor
    ]
    supervise(children, strategy: :one_for_one) # Se define la estrategia de supervisión
  end
end
```

### Definición de un proceso supervisado

```
defmodule MiApp.Worker do
  use GenServer

  def start_link do
    GenServer.start_link(__MODULE__, [], name: __MODULE__)
  end

  def init(_) do
    # Código de inicialización del proceso
    {:ok, []}
  end

  def handle_cast(:error, state) do
    # Código para manejar un error en el proceso
    {:noreply, state}
  end
end
```

## Ejercicios prácticos

1. Crea un supervisor que supervise un proceso y un supervisor secundario. Define una estrategia de supervisión adecuada para esta estructura.
2. Crea un proceso que reciba un mensaje y lo imprima por pantalla. Luego, utiliza el supervisor creado en el ejercicio anterior para manejar un posible error en el proceso.
3. Modifica el código del supervisor para que, en caso de que el proceso falle, se reinicie automáticamente.

## Consejos y mejores prácticas

- Utiliza una jerarquía de supervisión bien definida y evita tener un supervisor para todos los procesos de la aplicación.
- Define una estrategia de supervisión adecuada para cada supervisor, teniendo en cuenta la gravedad de los posibles errores.
- Utiliza el módulo `Supervisor` de Elixir para crear y manejar supervisores de forma sencilla.
- No intentes atrapar todos los errores en cada proceso, deja que el sistema de supervisión se encargue de manejarlos de forma eficiente.

### Navegación de lecciones

**<- Lección anterior**: [Despliegue de aplicaciones Elixir](despliegue_de_aplicaciones_elixir.md)

