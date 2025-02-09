
# Desarrollo de sistemas distribuidos

En esta lección, exploraremos el desarrollo de sistemas distribuidos utilizando Elixir. Un sistema distribuido es aquel en el que un conjunto de computadoras independientes se comunican entre sí para lograr un objetivo común. Elixir, un lenguaje de programación funcional basado en Erlang, es ideal para el desarrollo de sistemas distribuidos debido a sus características como la concurrencia, tolerancia a fallos y manejo de procesos.

## Teoría

Un sistema distribuido se compone de múltiples nodos conectados a través de una red de comunicación. Estos nodos pueden ser servidores, computadoras personales, dispositivos móviles, entre otros. Los sistemas distribuidos permiten el procesamiento paralelo y la escalabilidad, lo que los hace ideales para aplicaciones de alta demanda.

En Elixir, los nodos se comunican a través de Erlang Distribution, un protocolo de comunicación que permite la comunicación entre nodos en diferentes máquinas. Al utilizar este protocolo, los nodos pueden enviar mensajes entre sí y compartir recursos como procesos y datos.

Otra herramienta importante en el desarrollo de sistemas distribuidos en Elixir es RabbitMQ, un sistema de mensajería y colas que permite la comunicación asíncrona entre nodos. Esto es útil para el manejo de tareas en segundo plano y la coordinación de tareas entre diferentes nodos.

## Palabras clave

- Sistemas distribuidos: conjunto de computadoras independientes conectadas a través de una red para lograr un objetivo común.
- Elixir: lenguaje de programación funcional basado en Erlang.
- Erlang Distribution: protocolo de comunicación utilizado por Elixir para la comunicación entre nodos en diferentes máquinas.
- RabbitMQ: sistema de mensajería y colas utilizado para la comunicación asíncrona entre nodos.

## Preguntas de repaso

1. ¿Qué es un sistema distribuido?
2. ¿Por qué Elixir es adecuado para el desarrollo de sistemas distribuidos?
3. ¿Qué es Erlang Distribution y cómo se utiliza en Elixir?
4. ¿Cuál es la función de RabbitMQ en el desarrollo de sistemas distribuidos?
5. ¿Cuáles son las ventajas de utilizar sistemas distribuidos en aplicaciones de alta demanda?

## Ejemplos de código

### Comunicación entre nodos en Elixir

Para que dos nodos se comuniquen entre sí, primero deben conocerse y estar conectados a través de Erlang Distribution.

```
# Nodo A
iex --sname node_a

# Nodo B
iex --sname node_b

# En el nodo A
Node.connect(:"node_b@your_computer_name")

# En el nodo B
Node.connect(:"node_a@your_computer_name")
```

Una vez que los nodos están conectados, pueden enviar mensajes entre sí utilizando el módulo `Node`.

```
# En el nodo A
Node.send(:"node_b@your_computer_name", "Hola desde el nodo A")

# En el nodo B
Node.recv(:"node_a@your_computer_name")
```

### Comunicación asíncrona con RabbitMQ

Para utilizar RabbitMQ en un proyecto de Elixir, primero se debe agregar la dependencia a `mix.exs`.

```
defp deps do
  [
    {:amqp, "~> 1.0"}
  ]
end
```

Luego, se debe iniciar un proceso de conexión a RabbitMQ y crear una cola para recibir mensajes.

```
# Proceso de conexión
{:ok, connection} = AMQP.Connection.open

# Creación de una cola
{:ok, channel} = AMQP.Channel.open(connection)
{:ok, queue} = AMQP.Queue.declare(channel, "nombre_de_la_cola")
```

Para enviar un mensaje a través de RabbitMQ, se debe publicar en la cola previamente creada.

```
AMQP.Basic.publish(channel, "", "nombre_de_la_cola", "Mensaje de prueba")
```

Para recibir mensajes, se debe suscribir a la cola y especificar una función de manejo de mensajes.

```
AMQP.Basic.consume(channel, "nombre_de_la_cola", fn(msg) -> IO.puts(msg.body) end)
```

## Ejercicios prácticos

1. Configura dos nodos en tu máquina y realiza una comunicación entre ellos utilizando Erlang Distribution.
2. Crea un proyecto en Elixir que utilice RabbitMQ para la comunicación asíncrona entre dos nodos.
3. Implementa un sistema distribuido en Elixir que realice una tarea en paralelo utilizando múltiples nodos.

## Consejos y mejores prácticas

- Al trabajar con sistemas distribuidos, es importante tener en cuenta la tolerancia a fallos y el manejo de errores.
- Utiliza patrones como el modelo de actores y la supervisión de procesos para construir sistemas distribuidos robustos.
- Siempre documenta y prueba tu código para asegurarte de que los nodos se comuniquen correctamente y manejen los errores de manera adecuada.
- Considera el uso de librerías y herramientas como Phoenix y GenStage para simplificar y mejorar el desarrollo de sistemas distribuidos en Elixir.


**<- Lección anterior**: [Supervisión avanzada de procesos](supervision_avanzada_de_procesos.md)

