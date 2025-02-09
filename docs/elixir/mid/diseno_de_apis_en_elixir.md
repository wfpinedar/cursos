
# Diseño de APIs en Elixir

## Explicación teórica

Una API (Application Programming Interface) es una interfaz de programación que permite la comunicación entre diferentes aplicaciones o sistemas. En el contexto de Elixir, una API se refiere a una interfaz que permite la comunicación entre el código escrito en Elixir y otras aplicaciones o servicios.

El diseño de APIs en Elixir se basa en el uso del framework Phoenix, que es una herramienta poderosa para construir aplicaciones web y APIs RESTful. Las APIs RESTful (Representational State Transfer) son un estilo de arquitectura de software que se basa en los principios fundamentales de HTTP, como el uso de los verbos GET, POST, PUT y DELETE para manipular recursos.

El enfoque de diseño de APIs en Elixir se basa en la simplicidad, escalabilidad y robustez. Elixir es un lenguaje funcional que se ejecuta en la máquina virtual de Erlang, lo que le brinda una gran capacidad de concurrencia y tolerancia a fallos. Esto lo convierte en una excelente opción para construir APIs que deben manejar grandes cantidades de solicitudes y ser resilientes a errores y caídas del sistema.

## Palabras clave y su definición

- **API:** Interfaz de programación que permite la comunicación entre diferentes aplicaciones o sistemas.
- **Elixir:** Lenguaje de programación funcional que se ejecuta en la máquina virtual de Erlang.
- **Phoenix:** Framework de Elixir para construir aplicaciones web y APIs RESTful.
- **REST:** Estilo de arquitectura de software basado en los principios de HTTP.
- **HTTP:** Protocolo de transferencia de hipertexto, utilizado para la comunicación entre servidores y clientes en la web.
- **Verbos HTTP:** GET, POST, PUT y DELETE, utilizados para indicar la acción que se desea realizar sobre un recurso.
- **Recursos:** Elementos que se pueden manipular mediante una API RESTful, como por ejemplo usuarios, productos o publicaciones.
- **Concurrencia:** Capacidad de un sistema para ejecutar múltiples tareas al mismo tiempo.
- **Tolerancia a fallos:** Capacidad de un sistema para continuar funcionando a pesar de errores o caídas en el sistema.

## Preguntas de repaso

1. ¿Qué es una API y para qué se utiliza?
2. ¿Cuáles son los principios fundamentales de HTTP?
3. ¿Qué es Phoenix y por qué se utiliza en el diseño de APIs en Elixir?
4. ¿En qué se basa el enfoque de diseño de APIs en Elixir?
5. ¿Qué es la concurrencia y por qué es importante en el diseño de APIs?
6. ¿Qué es la tolerancia a fallos y por qué es importante en el diseño de APIs?

## Ejemplos de código en Elixir

A continuación, se muestra un ejemplo de código en Elixir para crear una API RESTful utilizando Phoenix:

```elixir
defmodule MyApp.UserController do
  use Phoenix.Controller

  # Acción para obtener todos los usuarios
  def index(conn, _params) do
    users = MyApp.Repo.all(MyApp.User)
    render(conn, "index.json", users: users)
  end

  # Acción para crear un nuevo usuario
  def create(conn, %{"user" => user_params}) do
    changeset = MyApp.User.changeset(%MyApp.User{}, user_params)
    case MyApp.Repo.insert(changeset) do
      {:ok, user} ->
        conn
        |> put_status(:created)
        |> put_resp_header("location", Routes.user_path(conn, :show, user))
        |> render("show.json", user: user)
      {:error, changeset} ->
        conn
        |> put_status(:unprocessable_entity)
        |> render("error.json", changeset: changeset)
    end
  end

  # Acción para obtener un usuario específico
  def show(conn, %{"id" => id}) do
    user = MyApp.Repo.get!(MyApp.User, id)
    render(conn, "show.json", user: user)
  end

  # Acción para actualizar un usuario
  def update(conn, %{"id" => id, "user" => user_params}) do
    user = MyApp.Repo.get!(MyApp.User, id)
    changeset = MyApp.User.changeset(user, user_params)
    case MyApp.Repo.update(changeset) do
      {:ok, user} ->
        render(conn, "show.json", user: user)
      {:error, changeset} ->
        conn
        |> put_status(:unprocessable_entity)
        |> render("error.json", changeset: changeset)
    end
  end

  # Acción para eliminar un usuario
  def delete(conn, %{"id" => id}) do
    user = MyApp.Repo.get!(MyApp.User, id)
    MyApp.Repo.delete(user)
    send_resp(conn, :no_content, "")
  end
end
```

## Ejercicios prácticos con instrucciones claras

1. Crea un nuevo proyecto en Phoenix utilizando el comando `mix phx.new my_api`.
2. Agrega un modelo `Product` con los campos `name`, `price` y `description`.
3. Crea las migraciones para crear la tabla `products` en la base de datos.
4. Genera un controlador `ProductController` con las acciones `index`, `create`, `show`, `update` y `delete`.
5. Implementa la lógica en cada acción para manipular los recursos de la tabla `products`.
6. Realiza pruebas utilizando herramientas como Postman para asegurarte de que la API funciona correctamente.

## Consejos o mejores prácticas

- Utiliza el principio de responsabilidad única para mantener tus controladores y modelos simples y fáciles de entender.
- Utiliza los verbos HTTP adecuados para cada acción, siguiendo las convenciones de las APIs RESTful.
- Utiliza el patrón de repositorio para encapsular la lógica de acceso a la base de datos en una capa separada.
- Utiliza el enrutamiento basado en recursos para definir las rutas de tu API de forma clara y coherente.
- Utiliza las pruebas automatizadas para garantizar que tu API funcione correctamente y maneje errores de manera adecuada.
- Utiliza los módulos de autenticación y autorización de Phoenix para proteger tu API de accesos no autorizados.
- Utiliza herramientas como Swagger para documentar tu API de forma clara y concisa.

**<- Lección anterior**: [Desarrollo de aplicaciones de tiempo real](desarrollo_de_aplicaciones_de_tiempo_real.md)

**Siguiente lección ->**: [Integración con bases de datos](integracion_con_bases_de_datos.md)
