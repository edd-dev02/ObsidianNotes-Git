Se trata de un **Hosting gratuito que ofrece GitHub** para poder montar sitios web que contienen código de solamente *HTML, CSS y JavaScript*.
No admite código de servidor y por lo tanto toda funcionalidad que este desarrollada para ese fin **no va a funcionar**.

- Solo funcionarán las llamadas a endpoints que tengamos desplegados en otro lugar
- Es una excelente opción para sitios web de contenido estático 
- Ideal para sitios web dinámicos cuyo contenido cambie con JavaScript (Astro, Angular, Vue, React, étc.)

## Tipos de GitHub Pages

1. Sitio web para el repositorio seleccionado en general
2. Sitio web por usuario de GitHub

## GitHub Pages por repositorio

- Creamos una carpeta llamada `docs` en el repositorio, desde VSC y añadimos archivos y directorios permitidos para ser renderizados en GitHub Pages.

![[pages_3.png]]

- Mandamos los nuevos cambios al repositorio remoto

Después nos dirigimos a la parte de `Pages` y seleccionamos la rama en la que se encuentran nuestros cambios, también seleccionamos la carpeta:

![[pages_4.png]]

## GitHub Pages por usuario

- Creamos un repositorio nuevo, la clave está en el nombre del repositorio
[nombreUsuario].[github].[io]
`edd-dev02.github.io`

![[pages_1.png]]

- Creamos el repositorio y nos dirigimos a la parte de `Settings` y seleccionamos la parte de `pages`

![[pages_2.png]]






