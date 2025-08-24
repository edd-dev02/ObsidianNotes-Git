*Para este ejemplo, modificaremos el archivo `README.md`*

Entonces, después de hacer un commit el estado sería:

![[push_1.png]]

El repositorio remoto estaría un commit atrás del `HEAD`

- Subir nuestros nuevos cambios a github
```bash
git push
```

>No es necesario poner el `git push -u origin` puesto que esta configuración ya la hemos establecido previamente al enlazar el repositorio local con el remoto

**Ojo:** Este movimiento puede crear conflictos en GitHub en caso de que se hayan hecho varias modificaciones

Entonces, se verían reflejados los siguientes cambios:

![[push_2.png]]








