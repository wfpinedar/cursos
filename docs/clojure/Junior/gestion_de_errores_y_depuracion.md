
# Gestión de errores y depuración en Clojure

En cualquier lenguaje de programación, es inevitable encontrarse con errores en el código. Estos pueden surgir por diversos motivos, como errores de sintaxis, problemas de lógica o errores en la entrada de datos. Por lo tanto, es esencial saber cómo manejar y solucionar estos errores de manera eficiente. En este módulo, aprenderemos cómo gestionar errores y depurar código en Clojure.

## Palabras clave

- Try/catch: Estructura de control utilizada para manejar excepciones en Clojure.
- catch: Bloque de código donde se define el manejo de la excepción.
- finally: Bloque de código que se ejecuta siempre, independientemente de si se produce una excepción o no.
- Excepción: Un evento inesperado que interrumpe el flujo normal de ejecución de un programa.
- Depuración: Proceso de identificar y corregir errores en el código.
- Traza: Información detallada sobre el flujo de ejecución del programa, incluyendo los errores que han ocurrido.

## Preguntas de repaso

1. ¿Qué es una excepción en Clojure?
2. ¿Cuál es la estructura de control utilizada para manejar excepciones en Clojure?
3. ¿Qué es la depuración y por qué es importante?
4. ¿Qué es una traza y cómo puede ser útil en la depuración?
5. ¿Cuál es la función del bloque `finally`?
6. ¿Cómo se desvía el programa al bloque `catch`?

## Ejemplos de código

### Utilizando try/catch para manejar excepciones

Manejo de una excepción aritmética. 
```clojure
(defn divide [num1 num2]
  (try
    (/ num1 num2)
    (catch ArithmeticException e
      (println "Error: No se puede dividir por cero."))))
```

Manejo de una excepción específica
```clojure
(try
  (throw (Exception. "Este es un ejemplo de excepción"))
  (catch Exception e
    (println "Se ha producido una excepción:" (.getMessage e))))
```

Manejo de cualquier excepción
```clojure
(try
  (/ 5 0)
  (catch Exception e
    (println "Se ha producido una excepción:" (.getMessage e))))
```

Uso del bloque `finally`
```clojure
(try
  (/ 5 0)
  (catch Exception e
    (println "Se ha producido una excepción:" (.getMessage e)))
  (finally
    (println "Este bloque se ejecuta siempre")))
```

En este ultimo ejemplo, utilizamos la estructura de control try/catch para manejar la excepción de división por cero. Si el código dentro de la cláusula try se ejecuta sin problemas, el resultado de la división se devuelve. Sin embargo, si ocurre una excepción, el código dentro de la cláusula catch se ejecuta y se imprime un mensaje de error.

### Imprimir una traza para depurar código

```clojure
(defn sum [nums]
  (if (empty? nums)
    (throw (Exception. "La lista está vacía."))
    (reduce + nums)))

(sum [1 2 3 4 5])
```

En este ejemplo, creamos una función que suma todos los elementos de una lista. Sin embargo, si la lista está vacía, lanzamos una excepción. Si ejecutamos esta función con una lista vacía, obtendremos el siguiente mensaje de error:

```
Exception: La lista está vacía.
```

Para obtener más información sobre dónde ocurrió el error, podemos imprimir una traza utilizando la función *print-stack-trace*:

```clojure
(defn sum [nums]
  (if (empty? nums)
    (throw (Exception. "La lista está vacía."))
    (reduce + nums)))

(try
  (sum [])
  (catch Exception e
    (println (.printStackTrace e))))
```

Esto nos dará una traza más detallada sobre el error:

```
java.lang.Exception: La lista está vacía.
	at user/sum (REPL:1)
	at user/eval325 (REPL:1)
	at clojure.lang.Compiler.eval (Compiler.java:7177)
	at clojure.lang.Compiler.eval (Compiler.java:7167)
	at clojure.lang.Compiler.load (Compiler.java:7635)
	at clojure.lang.Compiler.loadFile (Compiler.java:7573)
	at clojure.main$load_script.invokeStatic (main.clj:452)
	at clojure.main$init_opt.invokeStatic (main.clj:454)
	at clojure.main$init_opt.invoke (main.clj:454)
	at clojure.main$initialize.invokeStatic (main.clj:485)
	at clojure.main$null_opt.invokeStatic (main.clj:519)
	at clojure.main$null_opt.invoke (main.clj:516)
	at clojure.main$main.invokeStatic (main.clj:598)
	at clojure.main$main.doInvoke (main.clj:561)
	at clojure.lang.RestFn.applyTo (RestFn.java:137)
	at clojure.lang.Var.applyTo (Var.java:705)
	at clojure.main.main (main.java:37)
```

Esta información puede ser útil para identificar dónde ocurrió exactamente el error y solucionarlo.

## Ejercicios prácticos

1. Crea una función que calcule el promedio de una lista de números. Si la lista está vacía, lanza una excepción y muestra un mensaje de error.
2. Crea una función que encuentre el número más grande en una lista de números. Si la lista está vacía, lanza una excepción y muestra un mensaje de error.
3. Escribe un programa que solicite al usuario ingresar un número y lo multiplique por 10. Si el usuario ingresa un valor no numérico, muestra un mensaje de error y solicita nuevamente el número.
4. Modifica el programa anterior para que, en caso de que se produzca un error, solicite al usuario que ingrese un número diferente y lo multiplique por 10.

## Consejos y mejores prácticas

- Utiliza try/catch para manejar excepciones en lugar de dejar que el programa se bloquee.
- Imprime trazas para obtener información detallada sobre los errores y facilitar la depuración.
- Asegúrate de manejar todas las posibles excepciones en tu código para evitar que el programa se bloquee o produzca resultados inesperados.
- Utilizar el bloque `finally` para realizar tareas de limpieza o cierre de recursos, como cerrar archivos o conexiones a bases de datos.
- Evitar el uso excesivo de `try-catch` y en su lugar, utilizar funciones que manejen de forma más adecuada los posibles errores.

### Navegación de lecciones

**<- Lección anterior**: [Programación funcional](programacion_funcional.md)

**Siguiente lección ->**: [Módulos y namespaces](modulos_y_namespaces.md)

