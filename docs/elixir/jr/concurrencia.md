
# Concurrencia en Elixir

La concurrencia en Elixir se refiere a la capacidad de manejar múltiples procesos de forma eficiente. Esto significa que varios procesos pueden ejecutarse simultáneamente y compartir recursos de manera segura y controlada. Esto es posible gracias al modelo de concurrencia basado en el actor que utiliza Elixir, donde cada proceso se comporta como un actor independiente que se comunica con otros procesos a través de mensajes.

## Explicación teórica

La concurrencia en Elixir se basa en el concepto de procesos livianos, también conocidos como procesos de Erlang (el lenguaje en el que se basa Elixir). Estos procesos son diferentes a los procesos del sistema operativo, ya que son creados y administrados por la máquina virtual de Elixir y pueden tener un tamaño de memoria mucho más pequeño. Esto permite a Elixir crear y manejar miles de procesos en una sola máquina virtual, lo que lo hace ideal para aplicaciones que requieren una alta concurrencia.

Los procesos en Elixir se comunican entre sí enviando mensajes, que son en realidad datos inmutables. Esto significa que no se pueden modificar, por lo que no hay problemas de concurrencia al compartir datos entre procesos. Además, Elixir utiliza un mecanismo de paso de mensajes asíncrono, lo que significa que un proceso puede enviar un mensaje a otro proceso y seguir ejecutando su propio código sin tener que esperar una respuesta. Esto permite una comunicación eficiente entre procesos sin bloquear la ejecución.

Otra característica importante de la concurrencia en Elixir es la capacidad de manejar errores de forma controlada. Cada proceso tiene su propio manejo de errores, lo que significa que un proceso puede fallar sin afectar a otros procesos en ejecución. Además, Elixir proporciona mecanismos para supervisar y reiniciar procesos en caso de errores, lo que aumenta la tolerancia a fallos de las aplicaciones.

## Palabras clave y su definición

- Concurrency: El manejo de múltiples procesos que se ejecutan simultáneamente y comparten recursos de forma controlada.
- Process: Un proceso en Elixir es una unidad de ejecución liviana que se comunica con otros procesos a través de mensajes.
- Actor model: Un modelo de concurrencia donde cada proceso se comporta como un actor independiente que se comunica a través de mensajes.
- Message passing: El mecanismo utilizado por Elixir para que los procesos se comuniquen entre sí enviando mensajes.
- Immutable data: Datos que no pueden ser modificados después de su creación, lo que garantiza una comunicación segura entre procesos.
- Asynchronous: Un tipo de comunicación en la que un proceso puede enviar un mensaje y continuar ejecutando su propio código sin tener que esperar una respuesta.
- Error handling: El manejo de errores en los procesos, que se hace de forma individual para cada proceso en Elixir.
- Supervision: Un mecanismo en Elixir para monitorear y reiniciar procesos en caso de errores.

## Preguntas de repaso

1. ¿Qué es la concurrencia en Elixir?
2. ¿En qué se diferencia un proceso en Elixir de un proceso del sistema operativo?
3. ¿Cómo se comunican los procesos en Elixir?
4. ¿Qué es el modelo de actores?
5. ¿Qué es el mecanismo de paso de mensajes asíncrono?
6. ¿Cómo maneja Elixir los errores en los procesos?
7. ¿Qué es la supervisión en Elixir?
8. ¿Por qué es importante que los datos sean inmutables en un entorno de concurrencia?

## Ejemplos de código en Elixir

### Crear un proceso en Elixir

```
pid = spawn(fn -> "Hola, soy un proceso!" end)
```

Este código creará un nuevo proceso que imprimirá "Hola, soy un proceso!" cuando se le envíe un mensaje.

### Enviar y recibir mensajes entre procesos

```
pid = spawn(fn -> receive do
  mensaje -> IO.puts("He recibido un mensaje: #{mensaje}")
end end)

send(pid, "Hola desde el proceso padre!")
```

Este código creará un proceso que espera recibir un mensaje y luego imprimirá ese mensaje. Luego, el proceso padre enviará un mensaje al proceso recién creado.

## Ejercicios prácticos con instrucciones claras

1. Crea una función en Elixir que genere un número aleatorio y lo envíe como mensaje a otro proceso. El otro proceso debe imprimir el número recibido.
2. Crea dos procesos en Elixir y haz que se comuniquen entre sí enviando mensajes. El primer proceso debe imprimir "Hola" y el segundo proceso debe responder con "Hola de vuelta".
3. Crea una función en Elixir que calcule el factorial de un número y lo envíe como mensaje a otro proceso. El otro proceso debe imprimir el resultado recibido.

## Consejos o mejores prácticas

- Utiliza procesos en lugar de hilos para lograr una concurrencia más eficiente y segura en Elixir.
- Utiliza el modelo de actores para manejar los procesos de forma independiente y asegurar una comunicación segura entre ellos.
- Utiliza el mecanismo de supervisión para manejar errores en los procesos y aumentar la tolerancia a fallos de las aplicaciones.
- Utiliza datos inmutables en la comunicación entre procesos para evitar problemas de concurrencia.
- Evita bloquear la ejecución de procesos con llamadas síncronas, utiliza el paso de mensajes asíncrono siempre que sea posible.

### Navegación de lecciones

**<- Lección anterior**: [Procesos](procesos.md)

**Siguiente lección ->**: [Recursividad](recursividad.md)

