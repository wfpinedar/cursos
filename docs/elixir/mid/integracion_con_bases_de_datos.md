
# Integración con bases de datos

## Explicación teórica

La integración con bases de datos es un aspecto fundamental en el desarrollo de aplicaciones, ya que permite almacenar y recuperar datos de manera eficiente. En el caso de Elixir, existen diferentes opciones para integrar con bases de datos, pero la más utilizada es a través del framework Ecto.

Ecto es un módulo de Elixir que permite interactuar con bases de datos relacionales y no relacionales de manera sencilla y segura. Utiliza el patrón de diseño de Repositorio para manejar las operaciones de lectura y escritura en la base de datos. Además, cuenta con un lenguaje de consulta propio llamado Ecto Query Language (EctoQL) que facilita la creación de consultas y evita la inyección de SQL.

## Palabras clave y su definición

- Base de datos: conjunto de información estructurada y almacenada en un sistema de computación.
- Integración: proceso de conectar diferentes sistemas para que puedan interactuar entre sí.
- Elixir: lenguaje de programación funcional y concurrente basado en Erlang.
- Ecto: módulo de Elixir para interactuar con bases de datos.
- SQL: lenguaje de consulta estructurado utilizado para comunicarse con bases de datos relacionales.
- NoSQL: bases de datos no relacionales que no utilizan SQL como lenguaje de consulta.
- EctoQL: lenguaje de consulta utilizado por Ecto para realizar operaciones en la base de datos.

## Preguntas de repaso

1. ¿Qué es Ecto y para qué se utiliza?
2. ¿Cuál es el patrón de diseño utilizado por Ecto?
3. ¿Qué es EctoQL y para qué se utiliza?
4. ¿Qué es una base de datos NoSQL?
5. ¿Cuál es la ventaja de utilizar Ecto en lugar de SQL directamente?

## Ejemplos de código en Elixir

### Conexión a una base de datos utilizando Ecto

```elixir
defmodule MyApp.Repo do
  use Ecto.Repo,
    otp_app: :my_app,
    adapter: Ecto.Adapters.Postgres
end
```

### Creación de un modelo y migración en Ecto

```elixir
defmodule MyApp.Post do
  use Ecto.Schema

  schema "posts" do
    field :title, :string
    field :content, :text
    field :author, :string

    timestamps()
  end
end

defmodule MyApp.Repo.Migrations.CreatePosts do
  use Ecto.Migration

  def change do
    create table(:posts) do
      add :title, :string
      add :content, :text
      add :author, :string

      timestamps()
    end
  end
end
```

### Consulta utilizando EctoQL

```elixir
query = from p in Post,
        where: p.author == "John",
        select: p
Repo.all(query)
```

## Ejercicios prácticos con instrucciones claras

1. Crea un modelo y migración para una tabla "users" con los campos "name", "email" y "password" utilizando Ecto.
2. Crea una consulta utilizando EctoQL para obtener todos los usuarios con el nombre "John".
3. Conecta tu aplicación de Elixir a una base de datos MySQL utilizando Ecto.

## Consejos o mejores prácticas

- Utilizar Ecto en lugar de SQL directamente para evitar la inyección de SQL y facilitar el mantenimiento del código.
- Seguir las convenciones de nomenclatura de Ecto para los modelos y migraciones.
- Utilizar transacciones en Ecto para asegurar la consistencia de los datos en la base de datos.
- Utilizar índices en la base de datos para mejorar el rendimiento de las consultas.

**<- Lección anterior**: [Diseño de APIs en Elixir](diseno_de_apis_en_elixir.md)

**Siguiente lección ->**: [Optimización de rendimiento](optimizacion_de_rendimiento.md)
