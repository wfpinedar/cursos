
# Módulos y namespaces

En Clojure, los módulos y namespaces son herramientas fundamentales para organizar y estructurar el código de manera eficiente y escalable. Un módulo es una colección de código relacionado que puede ser reutilizado en diferentes partes de una aplicación. Por otro lado, un namespace es un espacio de nombres que permite agrupar y distinguir diferentes elementos dentro de un módulo. Esto ayuda a evitar conflictos de nombres y a facilitar la navegación y comprensión del código.

## Palabras clave y su definición

- Módulo: Colección de código relacionado que puede ser reutilizado en diferentes partes de una aplicación.
- Namespace: Espacio de nombres que permite agrupar y distinguir diferentes elementos dentro de un módulo.
- require: Función utilizada para cargar un módulo o namespace en el contexto actual.
- use: Función utilizada para cargar un módulo o namespace y ejecutar su código en el contexto actual.
- import: Función utilizada para importar una clase de Java en un namespace de Clojure.

## Preguntas de repaso
1. ¿Cuál es la diferencia entre un módulo y un namespace?
2. ¿Qué función se utiliza para cargar un módulo o namespace en el contexto actual?
3. ¿Cómo se importa una clase de Java en un namespace de Clojure?

## Ejemplos de código en Clojure

```clojure
(ns mi-app.modulo)

(defn suma [a b]
  (+ a b))

(defn resta [a b]
  (- a b))
```

En este ejemplo, definimos un módulo llamado "mi-app.modulo" que contiene dos funciones: suma y resta. Ahora, podemos utilizar estas funciones en cualquier otro namespace de nuestra aplicación utilizando la función "require".

```clojure
(ns mi-app.otro-namespace
  (:require [mi-app.modulo :as mod]))

(def resultado (mod/suma 5 3))
```

En este caso, utilizamos la función "require" para cargar el módulo "mi-app.modulo" con el alias "mod". Luego, podemos llamar a las funciones del módulo utilizando el alias y el nombre de la función.

## Ejercicios prácticos

1. Crea un módulo llamado "matematicas" con las funciones "multiplicacion" y "division". Importa este módulo en otro namespace y utiliza sus funciones para realizar operaciones matemáticas.
2. Crea un namespace llamado "utilidades" y utiliza la función "import" para importar la clase "Date" de Java. Luego, utiliza esta clase para obtener la fecha actual y mostrarla por pantalla.

## Consejos o mejores prácticas

- Utiliza nombres descriptivos y significativos para tus módulos y namespaces.
- Evita utilizar el mismo nombre para diferentes módulos o namespaces, ya que podría generar conflictos.
- Si tienes una gran cantidad de funciones en un namespace, considera dividirlo en sub-namespaces para una mejor organización.
- Al importar clases de Java, utiliza nombres de namespace específicos para evitar posibles conflictos de nombres.


**<- Lección anterior**: [Gestión de errores y depuración](gestion_de_errores_y_depuracion.md)

**Siguiente lección ->**: [Trabajo con archivos y bases de datos](trabajo_con_archivos_y_bases_de_datos.md)
