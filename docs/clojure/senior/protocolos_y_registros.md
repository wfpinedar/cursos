
# Protocolos y registros en Clojure

## Descripción del módulo

En este módulo, aprenderás sobre el uso de protocolos y registros en Clojure para estructurar y extender tipos de datos. Los protocolos y registros son herramientas fundamentales en Clojure para trabajar con estructuras de datos y permiten una mayor flexibilidad y extensibilidad en el código.

## Explicación teórica

### ¿Qué son los protocolos y registros?

En términos simples, los protocolos son un conjunto de funciones que se pueden aplicar a diferentes tipos de datos. Los registros, por otro lado, son una forma de definir estructuras de datos con campos específicos y funciones asociadas.

Los protocolos y registros se complementan entre sí, ya que los protocolos se utilizan para definir comportamientos comunes entre diferentes tipos de datos, mientras que los registros se utilizan para definir tipos de datos concretos con campos específicos y comportamientos definidos por los protocolos.

### ¿Por qué usar protocolos y registros?

La principal ventaja de utilizar protocolos y registros es que permiten una mayor extensibilidad y flexibilidad en el código. Al definir comportamientos comunes a través de protocolos, se puede aplicar a diferentes tipos de datos sin necesidad de cambiar el código existente. Además, los registros permiten definir tipos de datos personalizados con campos específicos y comportamientos definidos por los protocolos, lo que facilita la creación de estructuras de datos complejas.

Otra ventaja de los protocolos y registros es que fomentan la programación orientada a objetos (POO) en Clojure, lo que facilita la transición para aquellos que vienen de otros lenguajes de programación orientados a objetos.

## Palabras clave y su definición

- Protocolo: Un conjunto de funciones que se pueden aplicar a diferentes tipos de datos.
- Registro: Una estructura de datos con campos específicos y funciones asociadas.
- Extensibilidad: La capacidad de extender o agregar nuevas funcionalidades a un sistema existente.
- Flexibilidad: La capacidad de adaptarse y cambiar fácilmente para cumplir diferentes requisitos.
- Programación orientada a objetos (POO): Un paradigma de programación que se centra en la definición de objetos y sus interacciones.

## Preguntas de repaso

1. ¿Qué son los protocolos y registros en Clojure?
2. ¿Cuál es la relación entre los protocolos y registros?
3. ¿Para qué se utilizan los protocolos y registros?
4. ¿Cuál es la ventaja de utilizar protocolos y registros en Clojure?
5. ¿Cómo fomentan los protocolos y registros la programación orientada a objetos en Clojure?

## Ejemplos de código en Clojure

### Definir un protocolo

Para definir un protocolo en Clojure, se utiliza la macro `defprotocol`. Por ejemplo:

```clojure
(defprotocol Printable
  (print [data]))
```

Este protocolo se llama `Printable` y define una única función `print` que puede ser aplicada a diferentes tipos de datos.

### Implementar un protocolo en un registro

Para implementar un protocolo en un registro, se utiliza la macro `defrecord`. Por ejemplo:

```clojure
(defrecord Person [name age]
  Printable
  (print [data]
    (println (str "Name: " (:name data) " Age: " (:age data)))))
```

Este registro se llama `Person` y tiene dos campos: `name` y `age`. Además, implementa el protocolo `Printable` y define la función `print` para imprimir el nombre y la edad de la persona.

### Utilizar un registro y su función implementada

Una vez que se ha definido un registro que implementa un protocolo, se puede crear una instancia del registro y utilizar su función implementada. Por ejemplo:

```clojure
(def person (->Person "John" 30))
(print person)
```

Este código crea una instancia de `Person` con el nombre "John" y edad 30, y luego llama a la función `print` para imprimir su información.

## Ejercicios prácticos

1. Define un protocolo llamado `Calculable` con las funciones `sumar` y `restar`.
2. Implementa el protocolo `Calculable` en un registro llamado `Operacion` con dos campos `num1` y `num2`.
3. Crea una función `calcular` que tome un registro `Operacion` y devuelva el resultado de sumar `num1` y `num2`.
4. Crea una instancia de `Operacion` con los números 10 y 5 y utiliza la función `calcular` para obtener el resultado.

## Consejos o mejores prácticas

- Utiliza protocolos y registros para estructurar y extender tipos de datos en lugar de utilizar estructuras de datos anidadas.
- Antes de crear un registro, piensa en qué protocolos podría implementar y qué campos y funciones asociadas necesitará.
- Utiliza nombres descriptivos para tus protocolos y registros para facilitar su comprensión y uso en el código.

**<- Lección anterior**: [Transducers y reducers](transducers_y_reducers.md)

**Siguiente lección ->**: [Programación lógica](programacion_logica.md)

