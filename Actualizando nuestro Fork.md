Se tiene el siguiente caso:
- Dos miembros del equipo hicieron un `fork` el repositorio de GitHub upstream, lo clonaron, hicieron push y mandaron su respectivo `Pull request`, si nosotros somos el miembro A ¿cómo obtenemos los cambios del PR del miembro b?
 ![[a-fork_1.png]]
 >En términos sencillos, se realiza un `pull` al repositorio upstream
 
 ![[a-fork_2.png]]
## Práctica
*Se recomienda tener otro usuario para la práctica*
**Tutorial:** https://cursos.devtalles.com/courses/take/git-github-control-versiones/lessons/35435011-actualizando-nuestro-fork-practica

Al tocar la siguiente opción en nuestro repositorio del fork
![[a-fork_3.png]]

Si es que estamos por lo menos **un commit** atrasado, nos debería de salir de la siguiente manera:
![[a-fork_4.png]]

- Con la opción de `Fetch and merge` nuestro fork del repositorio remoto quedará actualizada

- Lo siguiente sería obtener los cambios de manera local

```bash
git pull
```

### Realizarlo a través de la consola
Para hacerlo necesitamos la referencia del repositorio oficial
>Se necesita por lo menos tener acceso de lectura

Primero, verificamos nuestras fuentes de origen

```bash
git remote -v
```

![[a-fork_5.png]]

Después añadimos el repositorio del cual obtendremos solo información, se les conocen como `upstream`, en el comando esto solamente es un **alias** y podemos asignarle el nombre que queramos, sin embargo, por convención se le llama de esa manera.

```bash
git remote add upstream https://github.com/Klerith/legion-del-mal.git
```

De esta manera si volvemos a consultar los orígenes deberian mostrarse las nuevas opciones

![[a-fork_6.png]]

>A pesar de que nos sale la opción de `push` recordar que no se tienen permisos de escritura y por lo tanto no es posible realizar la acción directamente.

- Para obtener los cambios del `upstream` y de una `branch` en concreto:
```bash
git pull upstream master
```

![[a-fork_7.png]]

### En caso de obtener nuevos cambios y se necesiten resolver conflictos...
*Primero, se resuelven los conflictos*

```bash
git status
git add .
git commit -m "Cambios nuevos de upstream obtenidos"
git rebase --continue
git push
```

>Ahora tenemos nuestro Fork actualizado







 