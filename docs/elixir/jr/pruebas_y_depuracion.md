
#Pruebas y depuración
##Introducción
En el desarrollo de software, es importante asegurarse de que el código escrito funciona correctamente y de manera confiable. Para lograr esto, es necesario realizar pruebas y depuración de código. En este módulo, aprenderemos sobre la importancia de las pruebas y la depuración en Elixir y cómo aplicarlas en nuestro código.

##Teoría
###Pruebas
Las pruebas son un conjunto de acciones que se realizan en el código para verificar si funciona como se espera. Hay diferentes tipos de pruebas, como las pruebas unitarias, las pruebas de integración y las pruebas funcionales. En este módulo, nos enfocaremos en las pruebas unitarias, que son pruebas que se realizan en pequeñas partes del código, como funciones y módulos.

Las pruebas unitarias son importantes porque nos permiten detectar errores en el código y asegurarnos de que nuestro código cumpla con los requisitos y funcione correctamente. También nos ayudan a detectar posibles problemas en el futuro y facilitan el mantenimiento del código.

###Depuración
La depuración es el proceso de identificar y corregir errores en el código. Es una parte esencial del desarrollo de software, ya que incluso con pruebas rigurosas, es posible que se encuentren errores en el código. La depuración también nos permite comprender mejor el funcionamiento del código y cómo solucionar problemas en el futuro.

##Palabras clave
- Pruebas unitarias: pruebas que se realizan en pequeñas partes del código para verificar su correcto funcionamiento.
- Depuración: proceso de identificar y corregir errores en el código.
- Pruebas de integración: pruebas que se realizan en diferentes partes del código para verificar su correcta integración.
- Pruebas funcionales: pruebas que se realizan en el sistema completo para verificar su correcto funcionamiento.

##Preguntas de repaso
1. ¿Qué son las pruebas unitarias y por qué son importantes?
2. ¿Cuál es la diferencia entre las pruebas de integración y las pruebas funcionales?
3. ¿Por qué es importante realizar la depuración en el código?

##Ejemplos de código
A continuación, se muestra un ejemplo de una función en Elixir y cómo se podría escribir una prueba unitaria para ella.

```elixir
# Función que devuelve el cuadrado de un número
def square(num) do
  num * num
end
```

Para escribir una prueba unitaria para esta función, se puede utilizar el módulo `ExUnit` de Elixir de la siguiente manera:

```elixir
# Test para la función square
defmodule SquareTest do
  use ExUnit.Case

  # Definir el contexto de la prueba
  test "square of 2 should be 4" do
    assert Square.square(2) == 4
  end
end
```

##Ejercicios prácticos
1. Escribe una función en Elixir que devuelva la suma de dos números y escribe una prueba unitaria para ella.
2. Escribe una función en Elixir que determine si un número es par o impar y escribe una prueba unitaria para ella.

##Consejos y mejores prácticas
- Es importante escribir pruebas unitarias para todas las funciones y módulos en nuestro código.
- Utilizar nombres descriptivos para las pruebas y asegurarse de cubrir todos los casos posibles.
- Utilizar herramientas de depuración, como el módulo `IEx`, para identificar y corregir errores en el código.

### Navegación de lecciones

**<- Lección anterior**: [Desarrollo de aplicaciones web con Elixir](desarrollo_de_aplicaciones_web_con_elixir.md)

**Siguiente lección ->**: [Despliegue de aplicaciones Elixir](despliegue_de_aplicaciones_elixir.md)

