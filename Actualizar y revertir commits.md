Al realizar un commit puede que nos equivoquemos, como en el siguiente caso:
![[actualizaciones_1.png]]
Hay varias formas de arreglarlo, comenzando por la más sencilla:

- Actualizar el mensaje del **último commit más reciente**: 
```bash
git commit --amend -m "Instalaciones actualizadas"
```

>Si utilizamos "git commit --amend" veremos una forma más gráfica de actualizar el mensaje del commit

- Añadir cambios nuevos a un commit que ya se hizo, evitando realizar un commit nuevo
(reset --soft no elimina los cambios, reset --hard si lo hace)
```bash
git reset --soft HEAD^
```

>HEAD^ apunta al último commit realizado de la rama main, HEAD puede ser reemplazado por el hash de un commit

Con este comando, volveremos a ese commit realizado, ya podemos subir los nuevos cambios al stage y realizar el commit.

![[actualizaciones_2.png]]
Ahora, podemos guardar los cambios y realizar el commit de nuevo

![[actualizaciones_3.png]]
