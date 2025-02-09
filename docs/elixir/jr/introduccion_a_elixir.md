
# Introducción a Elixir

## Descripción del módulo
En este módulo aprenderás los fundamentos de Elixir, un lenguaje de programación funcional y concurrente diseñado para construir aplicaciones escalables y fiables. Conocerás su historia, características y ventajas, y aprenderás a escribir código en Elixir utilizando ejemplos y ejercicios prácticos.

## Explicación teórica
Elixir fue creado en 2011 por José Valim, un desarrollador brasileño, con el objetivo de mejorar la productividad y la escalabilidad de las aplicaciones web. Está basado en Erlang, un lenguaje de programación de sistemas utilizado en aplicaciones de telecomunicaciones, y se ejecuta en la máquina virtual de Erlang (BEAM). Elixir se ha vuelto cada vez más popular en los últimos años gracias a su capacidad para gestionar grandes volúmenes de datos y procesos concurrentes, y su comunidad activa y colaborativa.

## Palabras clave y su definición
- Lenguaje de programación: un conjunto de reglas y símbolos utilizados para escribir instrucciones que una computadora puede entender y ejecutar.
- Funcional: un paradigma de programación en el que los programas se construyen a partir de funciones, que son unidades de código que reciben una entrada y producen una salida.
- Concurrente: la capacidad de un programa para realizar varias tareas al mismo tiempo.
- Escalabilidad: la capacidad de un sistema para manejar un aumento en la carga de trabajo sin disminuir su rendimiento.
- Máquina virtual: un entorno de ejecución que permite que un programa se ejecute en diferentes sistemas operativos y hardware sin cambios en el código fuente.

## Preguntas de repaso
1. ¿Quién creó Elixir y en qué año?
2. ¿En qué está basado Elixir?
3. ¿Qué es la escalabilidad y por qué es importante en las aplicaciones web?
4. ¿Qué es una máquina virtual y por qué es útil en el contexto de Elixir?

## Instalación de Elixir

A continuación, se muestra un breve resumen de cómo instalar Elixir en distintos sistemas operativos. Para más detalles, puedes consultar la [documentación oficial](https://elixir-lang.org/install.html).

### En Windows
1. Descarga el instalador de Elixir desde la [página oficial](https://elixir-lang.org/install.html#windows) o utiliza un administrador de paquetes como [Chocolatey](https://chocolatey.org/):
  
```bash
choco install elixir
```
1. Una vez instalado, abre una terminal (PowerShell o CMD) y verifica la instalación:

```bash
elixir -v
```

### En macOS
1. Si tienes [Homebrew](https://brew.sh/) instalado:

```bash
brew update
brew install elixir
```

1. Verifica la instalación:

```bash
elixir -v
```

### En Linux
- **Ubuntu/Debian**:

```bash
sudo apt-get update
sudo apt-get install elixir
```

- **Fedora/RHEL**:

```bash
sudo dnf install elixir
```
- O utiliza la herramienta de versiones [asdf](https://github.com/asdf-vm/asdf) para instalar y administrar múltiples versiones de Elixir y Erlang.

Tras la instalación, confirma la versión con:
```bash
elixir -v
```

## Uso de la consola interactiva (IEx)

Elixir incluye una consola interactiva llamada **IEx**, ideal para realizar pruebas rápidas de código y experimentar con Elixir. Para abrirla, simplemente escribe en tu terminal:

```bash
iex
```

Dentro de IEx, podrás ejecutar expresiones Elixir, ver resultados de forma inmediata y cargar módulos o archivos con facilidad.

**Ejemplo**:
```elixir
iex> IO.puts("¡Hola, Elixir!")
¡Hola, Elixir!
:ok
```

Para salir de IEx, presiona `Ctrl + C` dos veces.

## Ejecutar scripts de Elixir

Si tienes un archivo `.exs` (script de Elixir), puedes ejecutarlo directamente desde la terminal con:

```bash
elixir nombre_del_script.exs
```

Por ejemplo, si tu archivo se llama `hola.exs` y contiene:

```elixir
IO.puts("¡Hola desde un script de Elixir!")
```

Entonces, al correr:

```bash
elixir hola.exs
```

verás en la salida de tu terminal:

```bash
¡Hola desde un script de Elixir!
```

Con estos pasos, ya podrás instalar Elixir en tu sistema, probar código de manera interactiva en IEx y ejecutar scripts en tu entorno local.


## Ejemplos de código en Elixir
### Hola mundo
```
IO.puts "¡Hola mundo!"
```

### Funciones
```
defmodule Calculadora do
  def sumar(a, b) do
    a + b
  end
  
  def restar(a, b) do
    a - b
  end
end
```

### Concurrente
```
defmodule Proceso do
  def imprimir_mensaje(mensaje) do
    IO.puts mensaje
  end
end

spawn(fn -> Proceso.imprimir_mensaje("¡Hola!") end)
spawn(fn -> Proceso.imprimir_mensaje("¡Mundo!") end)
```



## Ejercicios prácticos
1. Crea una función en Elixir que multiplique dos números.
2. Escribe un programa concurrente en Elixir que imprima "¡Hola!" y "¡Mundo!" al mismo tiempo.
3. Utiliza Elixir para calcular el área de un círculo con un radio dado.

## Consejos o mejores prácticas
- Aprende los conceptos básicos de Erlang antes de sumergirte en Elixir.
- Utiliza la documentación oficial y la comunidad para resolver problemas y aprender nuevas técnicas.
- Practica la concurrencia y la programación funcional para aprovechar al máximo las capacidades de Elixir.


### Navegación de lecciones

**Siguiente lección ->**: [Sintaxis básica](sintaxis_basica.md)


