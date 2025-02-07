
# Programación concurrente y paralela

La programación concurrente y paralela son dos paradigmas de programación que permiten ejecutar múltiples tareas al mismo tiempo. Aunque a menudo se utilizan de manera intercambiable, existen algunas diferencias clave entre ellos.

## Explicación teórica

La programación concurrente se refiere a la capacidad de un programa de ejecutar varias tareas de manera intercalada. Esto significa que el programa puede iniciar una tarea, luego pasar a otra y luego volver a la tarea original. En la programación concurrente, las tareas se ejecutan de manera no determinista, lo que significa que su orden de ejecución no se puede predecir.

En Clojure, la programación concurrente se logra mediante el uso de hilos. Los hilos son secuencias de instrucciones que se ejecutan de forma independiente dentro de un programa. Cada hilo tiene su propio estado y puede realizar operaciones de manera concurrente con otros hilos.

Para lograr una programación concurrente efectiva, es importante tener en cuenta el manejo de la concurrencia. Esto se refiere a cómo se gestionan los recursos compartidos entre diferentes hilos. En Clojure, se utilizan estructuras de datos inmutables para evitar conflictos entre hilos y garantizar una ejecución segura y sin errores.

Por otro lado, la programación paralela se refiere a la capacidad de ejecutar varias tareas al mismo tiempo en diferentes núcleos de procesamiento o máquinas. A diferencia de la programación concurrente, en la programación paralela las tareas se ejecutan de manera simultánea y se pueden predecir su orden de ejecución.

En Clojure, ambos paradigmas se pueden implementar utilizando el modelo de concurrencia de Agent y el modelo de paralelismo de Pmap.

## Palabras clave y su definición

- Hilos: Secuencias de instrucciones que se ejecutan de forma independiente en un programa.
- Concurrencia: la capacidad de un programa para ejecutar varias tareas de manera intercalada.
- Paralelismo: la capacidad de un programa para ejecutar varias tareas de manera simultánea.
- Atom: Estructura de datos en Clojure que permite la actualización de un valor de forma segura y sin conflictos entre hilos.
- Refs: Referencias a estructuras de datos que se pueden modificar de forma transaccional y concurrente.
- Agent: un modelo de concurrencia en Clojure que permite la ejecución de tareas de manera asíncrona y en paralelo.
- Pmap: un modelo de paralelismo en Clojure que permite aplicar una función a una colección de elementos de manera paralela.
- Promise: Objeto que representa un valor que será entregado en algún momento futuro.

## Preguntas de repaso

1. ¿Qué es la programación concurrente y por qué es importante en Clojure?
2. ¿Cómo se logra la programación concurrente en Clojure?
3. ¿Cuál es la diferencia entre programación concurrente y paralela?
4. ¿Qué modelos de concurrencia y paralelismo existen en Clojure?
5. ¿Qué es un Agent en Clojure?
6. ¿Qué es Pmap en Clojure?

## Ejemplos de código en Clojure

### Programación concurrente

```clojure
(defn tarea [x]
  (println (str "Iniciando tarea " x))
  (Thread/sleep 1000)
  (println (str "Finalizando tarea " x)))

(dosync (future (tarea 1))
        (future (tarea 2))
        (future (tarea 3)))
```

En este ejemplo, la función `tarea` se ejecuta de manera asíncrona utilizando el modelo de concurrencia de Agent. Las tareas se ejecutarán de manera intercalada y su orden de ejecución no se puede predecir.

### Uso de hilos

```clojure
(defn funcion1 []
  (println "Ejecutando función 1")
  (Thread/sleep 1000)
  (println "Fin de función 1"))

(defn funcion2 []
  (println "Ejecutando función 2")
  (Thread/sleep 2000)
  (println "Fin de función 2"))

(def t1 (Thread. funcion1))
(def t2 (Thread. funcion2))

(.start t1)
(.start t2)

;; Resultado:
;; Ejecutando función 1
;; Ejecutando función 2
;; Fin de función 1
;; Fin de función 2
```

### Uso de atoms

```clojure
(def saldo (atom 100))

(defn depositar [cantidad]
  (swap! saldo + cantidad))

(defn retirar [cantidad]
  (swap! saldo - cantidad))

;; Ejecutar en hilos separados
(dotimes [i 10]
  (future (depositar 10))
  (future (retirar 5)))

@saldo ;; Resultado: 150
```

### Programación paralela

```clojure
(defn tarea [x]
  (println (str "Iniciando tarea " x))
  (Thread/sleep 1000)
  (println (str "Finalizando tarea " x)))

(pmap tarea (range 1 4))
```

En este ejemplo, la función `pmap` se encarga de aplicar la función `tarea` de manera paralela a cada elemento de la colección generada por `range`. Esto significa que las tareas se ejecutarán en diferentes núcleos de procesamiento o máquinas de manera simultánea.

## Ejercicios prácticos con instrucciones claras

1. Crea una función que reciba un número entero y devuelva su cuadrado utilizando el modelo de concurrencia de Agent.
2. Crea una función que reciba una lista de números y devuelva una lista con sus respectivos cuadrados utilizando el modelo de paralelismo de Pmap.
3. Modifica la función anterior para que solo devuelva los cuadrados de los números pares de la lista.
4. Crea una función en Clojure que calcule el área de un círculo utilizando hilos y muestre el resultado por pantalla.
5. Modifica la función anterior para que utilice una estructura de datos inmutable y evite conflictos entre hilos.
6. Crea una función que realice una operación matemática compleja en un agente y muestre el resultado por pantalla.
7. Crea una promesa en Clojure que devuelva un número aleatorio después de 5 segundos y muestra el resultado por pantalla.

## Consejos o mejores prácticas

- Utiliza la programación concurrente cuando necesites ejecutar tareas en segundo plano y no te importe su orden de ejecución.
- Utiliza la programación paralela cuando necesites mejorar el rendimiento de tu aplicación al ejecutar tareas en diferentes núcleos de procesamiento o máquinas.
- Ten en cuenta que la programación paralela puede tener un costo adicional de comunicación entre los diferentes procesos, por lo que es importante medir y evaluar su rendimiento antes de implementarla en tu aplicación.
- Utiliza estructuras de datos inmutables para evitar conflictos entre hilos.
- Evita la modificación directa de estructuras de datos compartidas entre hilos.
- Utiliza estructuras de datos específicas para la programación concurrente, como atoms, refs, agents y promises.
- Asegúrate de entender y manejar adecuadamente el manejo de la concurrencia en tus aplicaciones.
- Utiliza herramientas como la función "future" para ejecutar tareas de forma asincrónica y no bloquear el flujo principal del programa.


**<- Lección anterior**: [Programación funcional avanzada](programacion_funcional_avanzada.md)

**Siguiente lección ->**: [Testing y depuración](testing_y_depuracion.md)
