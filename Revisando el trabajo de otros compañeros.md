>Para este caso, tomaremos el rol de un participante externo que envía cambios al repositorio

- Creamos una rama nueva desde GitHub a partir de la rama `main` y creamos un archivo llamado `misiones.md`
![[revisiones_1.png]]

Entonces, en la rama `main` no contamos con este archivo
![[revisiones_2.png]]

![[revisiones_3.png]]

## ¿Cómo obtener las referencias de la nueva rama creada por otro miembro del equipo de manera **local**?

- Es necesario realizar un `git pull` con una bandera:
```bash
git pull --all
```

>Si ejecutamos un `git branch` no veremos la nueva rama, debido a que aún no la tenemos localmente

- Visualizar las ramas remotas de manera local
```bash
git branch -a
```

![[revisiones_4.png]]

- Ahora, simplemente con cambiarnos a esa rama llamada `rama-misiones` podemos visualizar sus cambios de manera local
```bash
git checkout rama-misiones
```

![[revisiones_5.png]]

>El siguiente paso, de ser necesario agregamos cambios, realizamos push y la rama de origin ya está lista para un Pull request, acto seguido debe borrarse esa rama

- A partir de este punto, **aún tendremos las referencias de la rama eliminada**, podemos comprobarlo con el comando `git branch -a`, entonces, es necesario realizar una limpieza de ramas.

[[Limpiar ramas que ya no son necesarias]]

