## 📌 Introducción a `git rebase`

El **`git rebase`** es una técnica en Git que permite **mover o "reaplicar"** una serie de commits de una rama encima de otra, como si siempre hubieran estado allí.  
En otras palabras, toma el historial de una rama y lo "reconstruye" partiendo de otro punto.

**Ejemplo sencillo**

- Rama **B**: commits `1` y `2`
    
- Rama **A**: commits `1`, `2` y `3`  
    Si en **B** queremos continuar el desarrollo pero necesitamos los cambios de **A**, hacemos:
    
```bash
git checkout B
git rebase A
```

Después del rebase, la rama **B** tendrá los commits de **A** seguidos por los commits originales de **B**, manteniendo un historial más lineal.

---

### 🔹 ¿Para qué sirve `git rebase`?

- **Mantener un historial limpio y lineal** (sin ramas entrecruzadas).
    
- **Unir commits** (_squash_).
    
- **Ordenar commits** para que el historial tenga más sentido.
    
- **Separar commits** (_split_) si tienen cambios no relacionados.
    
- **Renombrar commits** con mensajes más claros.

---

### ⚠️ Recomendaciones de uso

- Úsalo **solo en commits que no hayas compartido** (no enviados a un repositorio remoto) para evitar conflictos con el trabajo de otros.
    
- Es ideal para **trabajo local** antes de subir los cambios.
    
- Evita reescribir el historial de commits que ya estén en producción o en repositorios externos.

## 📊 Comparativa: `merge` vs `rebase`

| Característica            | `git merge`                                                   | `git rebase`                                                           |     |
| ------------------------- | ------------------------------------------------------------- | ---------------------------------------------------------------------- | --- |
| **Forma de unir cambios** | Une ramas creando un **commit de fusión** adicional.          | Mueve/reescribe commits para unirlos en un **historial lineal**.       |     |
| **Historial**             | Puede verse ramificado, muestra todos los merges.             | Más limpio y lineal, como si los cambios siempre hubieran estado allí. |     |
| **Conflictos**            | Pueden aparecer, pero se resuelven una sola vez.              | Pueden aparecer en cada commit reaplicado.                             |     |
| **Seguridad**             | No reescribe historial, es más seguro para ramas compartidas. | Reescribe historial, peligroso en ramas compartidas.                   |     |
| **Uso recomendado**       | Integrar cambios de forma rápida y sin reescribir historial.  | Mantener historial limpio antes de subir cambios.                      |     |
| **Ejemplo comando**       | `git merge ramaA`                                             | `git rebase ramaA`                                                     |     |
- Realizar un Rebase para obtener todos los avances de la rama `master` en la rama `rama-misiones-completadas`, de esta forma en la rama de las misiones primero se ordenarán todos los commits de `master` y posteriormente se insertaran todos los commits de la rama `rama-misiones-completadas`.
```bash
git checkout rama-misiones-completadas
git rebase master
git checkout master
git merge rama-misiones-completadas
```

Al tener lo mismo, se realizara un merge de tipo **Fast-forward**

![[rebase_1.png]]

Los primeros dos commits de `master` son los dos commits secundarios de la rama `rama-misiones-completadas`.
***
### Rebase - Squash
Para este ejemplo práctico vamos a unir dos commits cuyo objetivo fue parecido.

![[rebase_2.png]]

- Unir los 4 primeros commits a partir del HEAD
```bash
git rebase -i HEAD~4
```

La bandera `-i` es para ver el proceso de una manera más gráfica

![[rebase_3.png]]

Al guardar cambios y salir de esta ventana, ahora nos pedirá que renombremos el nuevo commit, se puede dejar el que viene por defecto o bien crear un nuevo mensaje.

![[rebase_4.png]]

Y en nuestro historial de commits, solamente aparecerá uno con el  mensaje que asignamos:

![[rebase_5.png]]

### Rebase - Reword

Consiste en renombrar los commits que queramos a partir del commit más reciente.
Ejemplo: 
![[rebase_6.png]]

Esos dos vamos a renombrarlos, para ello...

- Renombrar commits
```bash
git rebase -i HEAD~4
```

Al igual que el comando anterior, se nos abrirá la ventana de VSC ya que escogimos hacerlo de la manera gráfica

Debemos seleccionar los commits que queremos renombrar y asignarles el comando correspondiente, en este caso `reword` abreviado con `r`

![[rebase_7.png]]

Después, cerramos esta ventana y posteriormente nos saldrán otras dos ventanas, una de cada respectivo commit en donde podremos re escribir el mensaje.

![[rebase_8.1.png]]
![[rebase_8.2.png]]

Después de cerrar los archivos, los cambios quedan guardados

![[rebase_9.png]]

### Rebase - Edit

Para esta práctica, editaremos 3 archivos:

![[rebase_10.png]]

- Revertir los cambios de un único archivo `README.md`

```bash
git checkout -- README.md
```

De esta manera, habrá vuelto a su estado original como si no hubieramos hecho nada.

![[rebase_11.png]]

Caso: Creamos un commit con esos dos archivos llamado "Commits", pero **queremos realizar mejor commits independientes**


```bash
git rebase -i HEAD~3
```

![[rebase_12.png]]

La `e` o `edit` quiere decir que vamos a editar el commit.

A continuación git nos da las siguientes opciones:

```bash
Stopped at 8620ada...  Commits
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue

```

- `git commit --amend` para editar el commit
- `git rebase --continue` para dar el siguiente paso

>Al realizar este proceso, deberemos terminar con los pasos de una manera directa y evitar el uso de operaciones tales como un `stash`.

>Git nos indicará que nos encontramos en un rebase interactivo

![[rebase_13.png]]

Entonces, **siguiendo con el proceso para editar el commit** vamos a realizar un `reset --soft`

```bash
git reset HEAD^
```

De esta manera, los cambios del commit se bajaran del `stage` 

![[rebase_14.png]]

- Realizamos nuestros respectivos commits para cada archivo
```bash
git add villanos.md
git commit -m "Agregamos a Deadshot"
git commit -am "Misiones actualizadas"
```

- Finalmente, *terminamos el proceso del rebase interactivo*

```bash
git rebase --continue
```

![[rebase_15.png]]

>En caso de que haya un error relacionado de `HEAD` con la rama master:

```bash
git checkout master
```

