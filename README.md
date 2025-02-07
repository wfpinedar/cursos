# Mis Cursos

Este repositorio contiene material de aprendizaje y documentación en formato Markdown para distintos cursos de programación (Clojure, Elixir, Luminus, Phoenix, etc.). Todo el contenido se publica como un sitio estático utilizando **MkDocs**.

## Contenido

- **docs/**  
  Carpeta principal con los archivos `.md` de cada curso y sus respectivos niveles (Junior, Mid, Senior). Cada carpeta tiene su propio `index.md`.

- **mkdocs.yml**  
  Archivo de configuración de MkDocs, donde se define la navegación (nav), el tema y otras opciones.

- **.gitignore**  
  Lista de archivos y carpetas que deben ser ignorados por Git (por ejemplo, la carpeta `site/` generada por MkDocs).

- **README.md**  
  Este archivo, que describe la estructura del proyecto y los pasos para ejecutarlo.

## Requisitos

- **Python 3** (para usar MkDocs).
- **pip** o **pipenv/poetry** para instalar las dependencias de Python.
- (Opcional) Instalar un tema adicional, por ejemplo `mkdocs-material`.

## Instalación

1. Clona este repositorio:
   ```bash
   git clone https://github.com/tu-usuario/mis-cursos.git
   ```

2. Entra en la carpeta del proyecto:
   ```bash
   cd mis-cursos
   ```

3. Instala MkDocs y, si lo deseas, un tema adicional (por ejemplo, `dracula` o `mkdocs-material`):
   ```bash
   pip install mkdocs
   pip install mkdocs-dracula
   ```

## Uso

### Servir el sitio localmente

Para arrancar un servidor local con MkDocs y poder ver los cursos en tu navegador:

```bash
mkdocs serve
```

Esto levantará un servidor (por defecto en [http://127.0.0.1:8000](http://127.0.0.1:8000)).  
Cada vez que edites un archivo `.md`, MkDocs recargará automáticamente la página.

### Generar el sitio estático

Si quieres generar la carpeta `site/` con el contenido HTML:

```bash
mkdocs build
```

Se creará una carpeta `site/` en la raíz del proyecto, que contiene todos los archivos estáticos listos para publicar en cualquier hosting.


## Estructura de los Cursos

Actualmente, se incluyen cursos de:

- **Clojure**  
  - Niveles: Junior, Mid, Senior

- **Elixir**  
  - Niveles: Jr, Mid, Sr

- **Go**  
  - Niveles: Jr, Mid, Sr

- **Haskell**  
  - Niveles: Jr, Mid, Sr

- **Luminus**  
  - Niveles: Jr, Mid, Sr

- **Phoenix**  
  - Niveles: Jr, Mid, Sr

- **Phoenix (segunda parte)**  
  - Niveles: Jr, Mid, Sr

Cada nivel contiene varios archivos Markdown con la teoría, ejercicios y ejemplos de código.

## Cómo Contribuir

1. Haz un **fork** de este repositorio.
2. Crea una rama con un nombre descriptivo:
   ```bash
   git checkout -b feature/mi-mejora
   ```
3. Haz tus cambios (correcciones, nuevas lecciones, mejoras en la redacción, etc.).
4. Realiza un **pull request** para que tus cambios sean revisados e integrados.

## Licencia

Este proyecto está disponible bajo la [WPFL](http://www.wtfpl.net/).
