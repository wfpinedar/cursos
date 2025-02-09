
# Supervisión avanzada de procesos

## Explicación teórica
En Elixir, los procesos son la unidad básica de concurrencia y son esenciales para crear sistemas distribuidos y tolerantes a fallos. Sin embargo, estos procesos pueden fallar y es importante tener un sistema de supervisión robusto para manejar estos errores de manera eficiente.

La supervisión en Elixir se basa en el modelo de "padre e hijo", donde un proceso supervisa a sus hijos y se encarga de reiniciarlos en caso de que fallen. Esto permite que el sistema sea capaz de recuperarse automáticamente de errores y continuar funcionando sin interrupciones.

## Palabras clave y su definición

- Proceso: Una unidad de concurrencia en Elixir que se ejecuta de manera independiente y puede comunicarse con otros procesos a través de mensajes.
- Supervisión: Un mecanismo que permite a un proceso supervisar y gestionar a sus hijos.
- Árbol de supervisión: Una jerarquía de procesos donde un proceso padre supervisa a sus hijos y estos, a su vez, pueden tener sus propios hijos.
- Reinicio de procesos: Un proceso que falla se reinicia automáticamente por su supervisor.
- Estrategia de reinicio: Determina cómo se manejan los errores en un proceso y cómo se debe reiniciar si falla.
- Registra de supervisión: Un proceso especial que se encarga de registrar y almacenar información sobre los procesos y su estado.

## Preguntas de repaso

1. ¿Qué es un proceso en Elixir?
2. ¿En qué se basa el modelo de supervisión en Elixir?
3. ¿Qué es un árbol de supervisión?
4. ¿Qué es una estrategia de reinicio?
5. ¿Cuál es el papel del registro de supervisión en un sistema de Elixir?

## Ejemplos de código en Elixir

### Crear un proceso supervisado
```
defmodule MiProceso do
  use GenServer

  def start_link(arg) do
    GenServer.start_link(__MODULE__, arg, name: :mi_proceso)
  end

  # Definir el comportamiento del proceso
  def init(arg) do
    {:ok, arg}
  end
end
```

### Crear un árbol de supervisión
```
defmodule MiÁrbolDeSupervisión do
  use Supervisor

  def start_link do
    Supervisor.start_link(__MODULE__, :ok)
  end

  # Definir los procesos supervisados
  def init(:ok) do
    children = [
      worker(MiProceso, [arg], id: :mi_proceso)
    ]
    supervise(children, strategy: :one_for_one)
  end
end
```

### Definir una estrategia de reinicio
```
defmodule MiProceso do
  use GenServer

  def start_link(arg) do
    GenServer.start_link(__MODULE__, arg, name: :mi_proceso, restart: :permanent)
  end

  # Definir el comportamiento del proceso
  def init(arg) do
    {:ok, arg}
  end

  # Definir la estrategia de reinicio
  def handle_info(:terminate, state) do
    {:restart, :temporary, state}
  end
end
```

## Ejercicios prácticos con instrucciones claras

1. Crea un proceso supervisado llamado `MiProceso` que imprima "Hola Mundo" cada 5 segundos.
2. Define un árbol de supervisión que supervise al proceso `MiProceso`.
3. Prueba el árbol de supervisión reiniciando el proceso `MiProceso` y asegúrate de que se reinicie correctamente.
4. Modifica la estrategia de reinicio del proceso `MiProceso` para que sea `:transient` y comprueba cómo se comporta el sistema al reiniciar el proceso.

## Consejos o mejores prácticas

- Es importante definir adecuadamente las estrategias de reinicio de los procesos, ya que esto afectará directamente a la recuperación del sistema en caso de errores.
- Utilizar adecuadamente los registros de supervisión puede facilitar la detección y resolución de errores en un sistema distribuido.
- Es importante tener en cuenta la estructura de un árbol de supervisión y asegurarse de que sea lo suficientemente robusto para manejar fallos en diferentes niveles del sistema.

**<- Lección anterior**: [Seguridad en aplicaciones Elixir](seguridad_en_aplicaciones_elixir.md)

**Siguiente lección ->**: [Desarrollo de sistemas distribuidos](desarrollo_de_sistemas_distribuidos.md)
