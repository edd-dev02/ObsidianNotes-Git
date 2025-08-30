En caso de haber borrado una rama tanto de manera remota como local, podemos conseguirla de vuelta de la siguiente manera

>Previamente, se necesita haber creado un **tag** del punto de referencia de la rama

## Para este caso...

*Rama eliminada*: `rama-kitkat`
*Último tag de la rama registrado*: `v1.0.0`

![[restore_!.png]]

- Realizamos un checkout hacia el tag
```bash
git checkout v1.0.0
```

![[restore_2.png]]

En este punto nos encontramos en un punto especial del proyecto ya que no estamos en ninguna rama

![[restore_3.png]]

- Creamos la rama nuevamente desde este punto especial
```bash
git checkout -b rama-kitkat
```

- Realizar un `git push` para crear la rama de manera remota
```bash
git push --set-upstream origin rama-kitkat
```

De esta manera, recuperamos la rama eliminada.

## Crear la rama desde el repositorio...

Seleccionamos el **tag**

![[restore_4.png]]

Después en `Branches` creamos una rama a partir de ese punto

![[restore_5.png]]

# Importante

>Los `tags` **no se deben de borrar nunca**

