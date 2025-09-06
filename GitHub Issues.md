# ¿Qué es un Issue?

Un `Issue` es por lo general utilizado para marcar preguntas o añadir recomendaciones. Los usuarios los utilizan para decirle a los administradores del repositorio que presentan errores, asi mismo, se utiliza este apartado para darle seguimiento a todos estos errores que el repositorio tiene y todas las características que la aplicación debe tener *antes de salir a producción*.

Para trabajar con un Issues es necesario tener habilitada una opción en nuestro repositorio, dentro de *settings* debemos tener marcada la siguiente opción:

![[issues_1.png]]

Si desactivamos la opción, simplemente las personas ya no podrán crear issues nuevos.

![[issues_2.png]]

## Crear un Issue

Si el repositorio es público, cualquier persona podrá crear un Issue

![[issues_3.png]]

Y llenamos la información necesaria, también podemos añadir binarios de ser necesario.

![[issues_4.png]]

En este punto, nuestro `Issue` ya es visible

![[issues_5.png]]

## Cerrar un `Issue`

### Forma 1
Presionar el botón para cerrar el `issue` y añadir un comentario
![[issues_6.png]]

- Después de cerrar un issue, es necesario también  bloquear la conversación
![[issues_7.png]]

![[issues_8.png]]

>Podemos seguir agregando comentarios debido a que somos los administradores del repositorio

### Forma 2
Lo haremos resolviendo el issue en código

1. Realizamos los cambios en el código que nos piden y hacemos commit junto con push al repositorio
2. Dentro de los cambios del commit en el repositorio, nos aseguramos de añadir un comentario en la línea de código en donde resolvemos el `issue` haciendo referencia a este por su índice generado por GitHub
![[issues_9.png]]

Si nos vamos al `issue` ya tendremos la referencia del commit en donde se resolvió
![[issue_10.png]]

3. Posterior a esto, en los comentarios también podemos agregar el hash del commit en donde se resolvió el `issue` y acto seguido cerrarlo en el botón 'Close Issue'.

## Cerrar un `Issue` mediante un commit
Para ello: abrimos un issue nuevo y realizamos las modificaciones en el archivo correspondiente.

![[issues_11.png]]

- Después de atender la request en el código
```bash
git commit -am "Fixes #5: Hecho, añadí al super villano Thanos"
```

>**Importante**: tener presente el numeral del `issue` y usar exactamente el mismo en el commit en este caso es el número #5.

Después de esto, en GitHub el Issue debería de aparecer cerrado en automático y haciendo referencia al hash del commit en el que se resolvió.

![[issues_12.png]]

- Realizamos un `git push` y el repositorio ahora debe mostrar lo siguiente:
![[issues_13.png]]

## Issue Templates

Si hemos colaborado en proyectos, habrá ocasiones en  las que se nos proporcionará un formato para describir el `issue` 
En el apartado de configuración (dando por hecho que nosotros somos los administradores del repositorio) podemos encontrar un apartado para establecer una plantilla:

![[issues_14.png]]

![[issues_15.png]]

1. Bug report: reportar algún error
2. Feature request: sugerir alguna mejora
3. Custom template: Por si acaso queremos crear la plantilla de cero

![[issues_16.png]]

Si intentamos crear un nuevo `issue` GitHub nos dará la opción de seleccionar la plantilla y al hacerlo el formato lucirá de la manera establecida

![[issues_17.png]]


