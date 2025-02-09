
# Composición de procesos

## Explicación teórica
En Elixir, los procesos son unidades de ejecución concurrentes y ligeros que se comunican entre sí a través de mensajes. La composición de procesos se refiere a la habilidad de crear sistemas escalables y distribuidos al combinar múltiples procesos para trabajar juntos de manera eficiente.

La composición de procesos se basa en el modelo de "supervisión" de Elixir, donde un proceso principal supervisa a otros procesos secundarios y se encarga de reiniciarlos en caso de fallos. Este modelo permite que los sistemas sean resistentes a fallos y puedan recuperarse de manera automática sin afectar la funcionalidad general. Además, al tener múltiples procesos trabajando juntos, se pueden aprovechar mejor los recursos del sistema y balancear la carga de trabajo.

## Palabras clave y su definición
- Procesos: unidades de ejecución concurrentes y ligeros en Elixir.
- Supervisión: modelo en el que un proceso principal supervisa a otros procesos y se encarga de reiniciarlos en caso de fallos.
- Composición: combinación de múltiples procesos para crear sistemas escalables y distribuidos.
- Mensajes: medio de comunicación entre procesos en Elixir.

## Preguntas de repaso
1. ¿Qué es la composición de procesos en Elixir?
2. ¿En qué se basa el modelo de supervisión de Elixir?
3. ¿Qué beneficios ofrece la composición de procesos en términos de escalabilidad y distribución?
4. ¿Qué es un mensaje en Elixir y cómo se utiliza para la comunicación entre procesos?

## Ejemplos de código en Elixir
```
# Definir un módulo que tenga un proceso principal y dos procesos secundarios
defmodule Ejemplo do

  # Proceso principal
  defp proceso_principal do
    # Iniciar los procesos secundarios
    spawn_link(fn -> proceso_secundario1() end)
    spawn_link(fn -> proceso_secundario2() end)
  end

  # Proceso secundario 1
  defp proceso_secundario1 do
    # Realizar una tarea específica
    IO.puts "Proceso secundario 1 en ejecución"
  end

  # Proceso secundario 2
  defp proceso_secundario2 do
    # Realizar otra tarea específica
    IO.puts "Proceso secundario 2 en ejecución"
  end

end

# Iniciar el proceso principal
spawn_link(fn -> Ejemplo.proceso_principal() end)
```

## Ejercicios prácticos con instrucciones claras
1. Crea un módulo que tenga un proceso principal y tres procesos secundarios. El proceso principal debe iniciar los procesos secundarios y enviarles un mensaje para que realicen una tarea específica. Luego, el proceso principal debe esperar a que los procesos secundarios le envíen una respuesta y mostrarla por pantalla.
2. Modifica el módulo anterior para que los procesos secundarios se comuniquen entre sí enviando mensajes. El proceso principal debe iniciar los procesos secundarios y esperar a que se comuniquen entre sí antes de mostrar la respuesta final.
3. Crea un módulo que tenga un proceso principal que se encargue de supervisar a otros procesos secundarios. Los procesos secundarios deben ejecutar tareas diferentes y enviar un mensaje al proceso principal en caso de fallo. El proceso principal debe reiniciar automáticamente los procesos secundarios en caso de fallos y mostrar un mensaje de error si ocurren demasiados fallos en un período de tiempo.

## Consejos o mejores prácticas
- Utiliza la composición de procesos para crear sistemas escalables y distribuidos en lugar de tener un único proceso que realice todas las tareas.
- Utiliza el modelo de supervisión para garantizar que los procesos se reinicien en caso de fallos y para tener sistemas resistentes a fallas.
- Utiliza mensajes para la comunicación entre procesos y asegúrate de que los procesos estén diseñados para manejar diferentes tipos de mensajes.
- Utiliza la función `spawn_link` para iniciar procesos secundarios y mantenerlos vinculados al proceso principal.
- Utiliza el módulo `GenServer` para crear procesos que actúen como servidores y manejen peticiones de manera eficiente.

**<- Lección anterior**: [Programación funcional avanzada](programacion_funcional_avanzada.md)

**Siguiente lección ->**: [Desarrollo de aplicaciones concurrentes](desarrollo_de_aplicaciones_concurrentes.md)
