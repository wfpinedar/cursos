
# Estructuras de datos avanzadas en Elixir

En Elixir, las estructuras de datos avanzadas son una parte esencial de la programación funcional. Estas estructuras nos permiten almacenar, organizar y manipular datos de manera eficiente y efectiva. Algunas de las estructuras de datos avanzadas más utilizadas en Elixir son los mapas, diccionarios y estructuras de árbol.

## Palabras clave y su definición

- Mapas: Una estructura de datos que almacena pares de clave-valor, donde cada clave es única y los valores pueden ser de cualquier tipo de datos.
- Diccionarios: También conocidos como "hashes" o "tablas de dispersión", son estructuras de datos que almacenan pares de clave-valor, pero a diferencia de los mapas, los diccionarios no garantizan el orden de los elementos.
- Estructuras de árbol: Una estructura de datos jerárquica en la que cada elemento tiene un padre y cero o más hijos.

## Preguntas de repaso

1. ¿Qué es un mapa en Elixir y cómo se diferencia de un diccionario?
2. ¿Qué es una estructura de árbol y cómo se puede utilizar en Elixir?
3. ¿Cuál es la diferencia entre una lista y un mapa en Elixir?
4. ¿Cómo se pueden agregar elementos a un mapa existente en Elixir?
5. ¿Por qué las estructuras de datos avanzadas son importantes en la programación funcional?

## Ejemplos de código en Elixir

### Mapas

```elixir
# Crear un mapa con pares de clave-valor
mapa = %{nombre: "Ana", edad: 30, ciudad: "Barcelona"}

# Acceder a un valor en el mapa
mapa[:nombre] # "Ana"

# Agregar un nuevo par de clave-valor al mapa
Map.put(mapa, :telefono, "123456789")

# Actualizar un valor existente en el mapa
Map.put(mapa, :edad, 31)

# Eliminar un par de clave-valor del mapa
Map.delete(mapa, :ciudad)
```

### Diccionarios

```elixir
# Crear un diccionario con pares de clave-valor
diccionario = %{nombre: "Juan", edad: 25, ciudad: "Madrid"}

# Acceder a un valor en el diccionario
diccionario[:ciudad] # "Madrid"

# Agregar un nuevo par de clave-valor al diccionario
Map.put(diccionario, :telefono, "987654321")

# Actualizar un valor existente en el diccionario
Map.put(diccionario, :edad, 26)

# Eliminar un par de clave-valor del diccionario
Map.delete(diccionario, :nombre)
```

### Estructuras de árbol

```elixir
# Crear una estructura de árbol con un nodo raíz
arbol = %{valor: 5, hijos: [%{valor: 3, hijos: [%{valor: 1, hijos: []}, %{valor: 4, hijos: []}]}, %{valor: 8, hijos: [%{valor: 6, hijos: []}, %{valor: 9, hijos: []}]}]}

# Acceder a un valor en el árbol
arbol[:hijos][0][:valor] # 3

# Agregar un nuevo nodo al árbol
Map.put(arbol[:hijos][0][:hijos][1], :hijos, [%{valor: 2, hijos: []}])

# Eliminar un nodo del árbol
Map.delete(arbol[:hijos][1][:hijos][1], :valor)
```

## Ejercicios prácticos

1. Crea un mapa con los datos de una persona (nombre, edad, ciudad) y agrega su número de teléfono.
2. Crea un diccionario con las calificaciones de un estudiante en diferentes materias y actualiza su nota en una de ellas.
3. Crea una estructura de árbol con los nombres de diferentes países y agrega un nuevo país como hijo de uno existente.
4. Crea una función que reciba un mapa y una clave, y devuelva el valor correspondiente o "No existe" si la clave no está presente.
5. Crea una función que reciba una lista de números y devuelva la suma de todos los elementos utilizando una estructura de árbol.

## Consejos o mejores prácticas

- Utiliza mapas cuando necesites almacenar pares de clave-valor y mantener el orden de los elementos.
- Utiliza diccionarios cuando necesites una estructura de datos más rápida para buscar y actualizar valores.
- Utiliza estructuras de árbol cuando necesites almacenar datos de manera jerárquica y realizar operaciones de búsqueda y modificación de manera eficiente.
- Asegúrate de entender cómo se comportan las estructuras de datos en Elixir para elegir la más adecuada para cada situación.
- No tengas miedo de utilizar patrones de recursividad para trabajar con estructuras de datos avanzadas en Elixir.