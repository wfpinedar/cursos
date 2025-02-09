
# Despliegue de aplicaciones Elixir

## Explicación teórica

El despliegue de aplicaciones Elixir se refiere al proceso de llevar una aplicación desarrollada en este lenguaje a un entorno de producción, donde los usuarios pueden acceder y utilizarla. Este proceso es crucial para cualquier proyecto en Elixir, ya que permite que la aplicación sea utilizada de manera eficiente y confiable.

Existen diferentes opciones para desplegar aplicaciones Elixir en producción, y la elección dependerá de las necesidades y requerimientos del proyecto en particular. Algunas de las opciones más comunes son el uso de contenedores y servicios de hosting.

Los contenedores son una forma de empaquetar una aplicación junto con todas sus dependencias en un entorno aislado y portátil. Esto permite que la aplicación se ejecute de manera consistente en diferentes sistemas operativos y plataformas. Algunas herramientas populares para el despliegue de aplicaciones Elixir en contenedores son Docker y Kubernetes.

Por otro lado, los servicios de hosting son plataformas que ofrecen entornos de producción listos para ejecutar aplicaciones Elixir. Estos servicios se encargan de la configuración y mantenimiento de los servidores, permitiendo que los desarrolladores se enfoquen en la creación y mejora de la aplicación. Algunos ejemplos de servicios de hosting para aplicaciones Elixir son Heroku, Gigalixir y Fly.io.

En ambos casos, es importante tener en cuenta aspectos como la escalabilidad, el rendimiento y la seguridad al elegir una opción de despliegue para una aplicación Elixir.

## Palabras clave y su definición

- Despliegue: proceso de llevar una aplicación a un entorno de producción.
- Contenedor: tecnología de virtualización que permite empaquetar una aplicación junto con sus dependencias en un entorno aislado y portátil.
- Servicio de hosting: plataforma que ofrece entornos de producción listos para ejecutar aplicaciones.
- Escalabilidad: capacidad de una aplicación para manejar un aumento en la cantidad de usuarios o tráfico.
- Rendimiento: medida de la eficiencia y velocidad de una aplicación.
- Seguridad: conjunto de medidas tomadas para proteger una aplicación contra posibles ataques o vulnerabilidades.

## Preguntas de repaso

1. ¿Qué es el despliegue de aplicaciones Elixir?
2. ¿Cuáles son algunas opciones comunes para desplegar aplicaciones Elixir en producción?
3. ¿Qué es un contenedor y cómo ayuda en el despliegue de aplicaciones Elixir?
4. ¿Qué son los servicios de hosting y cuál es su ventaja en el despliegue de aplicaciones Elixir?
5. ¿Qué aspectos se deben tener en cuenta al elegir una opción de despliegue para una aplicación Elixir?

## Ejemplos de código en Elixir

### Crear una aplicación Elixir

```
mix new my_app
```

### Configurar una aplicación para ser desplegada en Heroku

1. Agregar las dependencias necesarias en el archivo mix.exs:

```
defp deps do
  [
    {:plug_cowboy, "~> 2.0"},
    {:phoenix, "~> 1.5.0"},
    {:phoenix_ecto, "~> 4.1"},
    {:ecto_sql, "~> 3.0"},
    {:postgrex, ">= 0.0.0"},
    {:distillery, "~> 2.0"},
    {:phoenix_live_reload, "~> 1.2", only: :dev}
  ]
end
```

2. Crear un archivo Procfile para especificar cómo se debe iniciar la aplicación:

```
web: MIX_ENV=prod mix release --no-tar --no-silent
```

3. Crear un archivo config/prod.exs para configurar la base de datos y otras variables de entorno:

```
config :my_app, MyApp.Repo,
  adapter: Ecto.Adapters.Postgres,
  username: System.get_env("DB_USERNAME"),
  password: System.get_env("DB_PASSWORD"),
  database: System.get_env("DB_NAME"),
  hostname: System.get_env("DB_HOSTNAME"),
  pool_size: 10
```

4. Generar una migración para crear la base de datos:

```
mix ecto.gen.migration create_table
```

5. Configurar la aplicación para utilizar Distillery en el archivo config/config.exs:

```
config :my_app, MyApp.Release,
  migration_commands: &[
     "ecto.migrate"
  ],
  start_commands: &[
    "ecto.migrate",
    "phx.server"
  ]
```

6. Generar un release de la aplicación:

```
MIX_ENV=prod mix release
```

7. Crear una aplicación en Heroku y configurar las variables de entorno necesarias (DB_USERNAME, DB_PASSWORD, DB_NAME, DB_HOSTNAME).

8. Subir la aplicación a Heroku:

```
heroku create
git push heroku master
```

## Ejercicios prácticos con instrucciones claras

1. Crea una aplicación Elixir utilizando el comando `mix new`.
2. Configura la aplicación para ser desplegada en Heroku siguiendo los pasos mencionados en el ejemplo de código.
3. Genera un release de la aplicación y sube la aplicación a Heroku.
4. Crea un contenedor para la aplicación utilizando Docker.
5. Configura un servicio de hosting y sube la aplicación a este servicio.

## Consejos o mejores prácticas

- Utilizar contenedores o servicios de hosting en lugar de configurar manualmente un servidor para desplegar una aplicación Elixir.
- Realizar pruebas de rendimiento y seguridad antes de elegir una opción de despliegue en producción.
- Utilizar herramientas como Distillery para generar releases de la aplicación y facilitar el proceso de despliegue.
- Configurar correctamente las variables de entorno en el entorno de producción para mantener la seguridad de la aplicación.
- Revisar y actualizar regularmente las dependencias de la aplicación para mantenerla segura y eficiente.

### Navegación de lecciones

**<- Lección anterior**: [Pruebas y depuración](pruebas_y_depuracion.md)

**Siguiente lección ->**: [Supervisión de procesos](supervision_de_procesos.md)

