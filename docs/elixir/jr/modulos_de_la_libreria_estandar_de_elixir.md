
# Módulos de la librería estándar de Elixir

Los módulos de la librería estándar de Elixir son un conjunto de funciones y estructuras de datos predefinidas que nos permiten realizar tareas comunes de manera eficiente y sencilla. Estos módulos forman parte del núcleo de Elixir y se encuentran disponibles sin necesidad de instalar ningún paquete adicional. 

## Palabras clave y definiciones

- **String**: tipo de dato que representa una secuencia de caracteres. Los módulos de la librería estándar de Elixir permiten la manipulación y transformación de cadenas de manera eficiente.
- **Date**: tipo de dato que representa una fecha, incluyendo información sobre el año, mes y día. Los módulos de la librería estándar de Elixir ofrecen funciones para manipular y comparar fechas.
- **File**: tipo de dato que representa un archivo en el sistema. Los módulos de la librería estándar de Elixir proporcionan funciones para crear, leer, escribir y manipular archivos.

## Preguntas de repaso

1. ¿Qué son los módulos de la librería estándar de Elixir?
2. ¿Qué tipo de datos se pueden manipular con los módulos de cadenas?
3. ¿Cómo se representan las fechas en Elixir?
4. ¿Qué funciones ofrecen los módulos de la librería estándar para manipular archivos?
5. ¿Es necesario instalar algún paquete adicional para utilizar los módulos de la librería estándar de Elixir?

## Ejemplos de código en Elixir

### Manipulación de cadenas

```elixir
# Obtener la longitud de una cadena
String.length("Hola Mundo")
# => 10

# Convertir una cadena a mayúsculas
String.upcase("hola mundo")
# => "HOLA MUNDO"

# Reemplazar una subcadena por otra
String.replace("Elixir es genial", "genial", "increíble")
# => "Elixir es increíble"
```

### Manipulación de fechas

```elixir
# Obtener la fecha actual
Date.utc_today()
# => ~D[2021-12-03]

# Sumar un día a una fecha
Date.add(~D[2021-01-01], 1)
# => ~D[2021-01-02]

# Comparar dos fechas
Date.compare(~D[2021-01-01], ~D[2020-12-31])
# => :gt
```

### Manipulación de archivos

```elixir
# Crear un nuevo archivo
File.write("nuevo.txt", "Este es un nuevo archivo")
# => :ok

# Leer el contenido de un archivo
File.read("nuevo.txt")
# => {:ok, "Este es un nuevo archivo"}

# Mover un archivo a otro directorio
File.rename("nuevo.txt", "otro/nuevo.txt")
# => :ok
```

## Ejercicios prácticos

1. Crea una función que reciba una cadena y devuelva la misma cadena en mayúsculas.
2. Crea una función que reciba dos fechas y determine cuál de ellas es más reciente.
3. Crea una función que reciba una lista de nombres y los escriba en un archivo de texto, cada uno en una línea diferente.

## Consejos y mejores prácticas

- Antes de utilizar cualquier módulo de la librería estándar, es importante leer la documentación oficial para entender cómo funciona y qué parámetros recibe cada función.
- Al manipular cadenas, es recomendable utilizar el módulo String para aprovechar sus funciones optimizadas en lugar de realizar operaciones directamente sobre la cadena.
- Al trabajar con fechas, es importante tener en cuenta la zona horaria para evitar resultados inesperados.
- Antes de manipular archivos, es necesario asegurarse de tener los permisos adecuados para realizar las operaciones deseadas.

### Navegación de lecciones

**<- Lección anterior**: [Módulos](modulos.md)

**Siguiente lección ->**: [Desarrollo de aplicaciones web con Elixir](desarrollo_de_aplicaciones_web_con_elixir.md)

