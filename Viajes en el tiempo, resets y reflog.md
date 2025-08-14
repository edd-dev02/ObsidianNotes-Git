- Modificar un commit utilizando el identificador del commit en especifico:
![[tiempo_1.png]]
```bash
git reset --soft 0855f13
```

Después de realizar las modificaciones necesarias, volvemos a preparar todo en el stage y realizamos el commit, en este caso añadimos un superhéroe nuevo.
![[tiempo_2.png]]
#### Regresar en el tiempo varios commits (antes de que algo saliera mal)

Se necesita regresar al commit donde agregamos las ciudades:
![[tiempo_3.png]]

--mixed: saca todo del stage y los cambios quedan listos para volverlos a añadir
```bash
git reset --mixed e9fc772
```
Al hacer esto, en el historial de commits solamente nos mostrara todos los que hayamos hecho hasta ese punto.
![[tiempo_4.png]]
De esta manera, los cambios nuevos **si se conservan en los archivos modificados y su estado será como untracked o modified según hasta donde hayamos retrocedido con el reset.
![[tiempo_5.png]]

#### Eliminar los cambios en los archivos en un reset
Si queremos que el estado de los archivos vuelva a como era originalmente al volver en el tiempo en un commit, en este caso al commit que retrocedimos anteriormente (e9fc772 - (34 minutes ago) Agregamos ciudades.md - Eduardo Sandoval (HEAD -> main)

Entonces utilizamos la bandera --hard:
```bash
 git reset --hard e9fc772
```

También podemos ir retrocediendo de uno en uno:
```bash
 git reset --hard HEAD^
```

Hasta este punto, en el historial de commit's todo se habrá borrado:
![[tiempo_6.png]]

Pero si queremos recuperar todo lo perdido en caso de que se desee abortar la operación de resets, entonces debemos recuperar todo el historial de movimientos.

>Consultar el HASH de todos los movimientos hechos a través del tiempo:

```bash
 git reflog
```

![[tiempo_7.png]]
Para recuperar todos los commits perdidos, simplemente aplicamos un reset hard al movimiento con el hash: **9839b62 HEAD@{5}: commit: heroes.md: Agregamos a Linterna Verde y Robin**
Ya que este fue el último commit.
```bash
 git reset --hard 9839b62
```

De esta forma, eliminamos todos los movimientos de los resets y recuperamos todos los commit's
![[tiempo_8.png]]
