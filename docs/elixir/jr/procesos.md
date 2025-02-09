
# Procesos

## Explicación teórica
Los procesos en Elixir son la unidad básica de concurrencia en el lenguaje. Se trata de un mecanismo ligero y eficiente para ejecutar código de manera paralela y así aprovechar al máximo los recursos del sistema. Cada proceso tiene su propio espacio de memoria y se comunican entre sí a través de mensajes, lo que permite una comunicación asincrónica y segura.

Para crear un proceso en Elixir, se utiliza la función `spawn/1` que recibe como argumento una función anónima o un módulo y una función. Esto crea un nuevo proceso que ejecuta el código especificado y devuelve un identificador único, llamado pid, que se utiliza para comunicarse con dicho proceso.

Los procesos en Elixir son supervisados por un supervisor, lo que significa que en caso de que un proceso falle, el supervisor puede reiniciar el proceso o tomar otra acción definida por el desarrollador.

## Palabras clave y su definición
- Proceso: Unidad básica de concurrencia en Elixir, que ejecuta código de manera paralela y se comunica con otros procesos a través de mensajes.
- Spawn: Función que crea un proceso y devuelve un identificador único.
- Pid: Identificador único de un proceso que se utiliza para comunicarse con él.
- Supervisión: Mecanismo que permite controlar y gestionar los procesos, reiniciándolos en caso de fallos.
- Mensajes: Medio de comunicación asincrónico y seguro entre procesos en Elixir.

## Preguntas de repaso
1. ¿Qué es un proceso en Elixir?
2. ¿Cómo se crea un proceso en Elixir?
3. ¿Qué es un pid y para qué se utiliza?
4. ¿Qué es la supervisión en Elixir?
5. ¿Cómo se comunican los procesos en Elixir?

## Ejemplos de código en Elixir
### Crear un proceso que imprime un mensaje
```elixir
pid = spawn(fn -> IO.puts("Hola, soy un proceso") end)
# Output: Hola, soy un proceso
```

### Comunicación entre dos procesos
```elixir
receive do
  msg -> IO.puts("Mensaje recibido: #{msg}")
end

pid = spawn(fn -> send(self(), "Hola desde el proceso hijo") end)
# Output: Mensaje recibido: Hola desde el proceso hijo
```

### Supervisión de procesos
```elixir
defmodule MiSupervisor do
  use Supervisor

  def start_link do
    Supervisor.start_link(__MODULE__, :ok)
  end

  def init(:ok) do
    children = [
      worker(MyProcess, []),
      worker(AnotherProcess, [])
    ]
    supervise(children, strategy: :one_for_one)
  end
end
```

## Ejercicios prácticos con instrucciones claras
1. Crea un proceso que calcule la suma de dos números ingresados por el usuario y devuelva el resultado.
2. Crea dos procesos que se comuniquen entre sí para imprimir un mensaje en mayúsculas y otro en minúsculas.
3. Implementa un supervisor que gestione tres procesos y en caso de fallo de uno de ellos, lo reinicie automáticamente.

## Consejos o mejores prácticas
- Utilizar procesos para tareas que se puedan ejecutar de manera independiente y que no requieran un alto nivel de sincronización.
- Usar la comunicación por mensajes para garantizar la seguridad y evitar los problemas de concurrencia.
- Utilizar supervisores para gestionar y controlar los procesos y asegurar la robustez del sistema.
- Evitar compartir datos mutables entre procesos para evitar problemas de concurrencia y asegurar la consistencia de los datos. En su lugar, utilizar estructuras de datos inmutables y la comunicación por mensajes.

### Navegación de lecciones

**<- Lección anterior**: [Patrones y coincidencias](patrones_y_coincidencias.md)

**Siguiente lección ->**: [Concurrencia](concurrencia.md)

