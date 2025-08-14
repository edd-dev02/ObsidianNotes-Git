Una rama es una línea de tiempo de commits

- Crear una rama llamada 'rama-villanos'
```bash
git branch rama-villanos
```

- Consultar las ramas existentes
```bash
git branch
```

![[ramas_1.png]]
>Nos encontramos en la rama con el nombre resaltado

- Cambiar de rama
```bash
git checkout rama-villanos
```

Tanto la rama master como rama-villanos comparten el último commit, por lo que se verá reflejado que ambas apuntan a 'HEAD'
![[ramas_2.png]]
Esto quiere decir que tienen los mismos avances.
Si hacemos un commit en la rama-villanos entonces el HEAD apuntará solamente  a esa rama, y conforme vayamos haciendo commits la rama master ira quedándose atrás, esto es normal.
![[ramas_3.png]]
**Unir los 'villanos' o los cambios de la rama-villanos a la rama principal master.**
Para ello, primero cambiamos de rama a la que deseamos unir los cambios nuevos
```bash
git checkout master
```

>El archivo villanos.md dejara de ser visible, ya que este solo existe en la rama 'rama-villanos'

Después de que nos posicionamos en la rama que queremos obtener los cambios, ejecutamos:
```bash
git merge rama-villanos
```

Con esto se obtiene un merge 'Fast-forward' y esto significa que git logró identificar cada uno de los cambios y no hay ningún conflicto, todo se implementó correctamente.
![[ramas_4.png]]
Con esta implementación, ahora ambas ramas de nuevo apuntan al 'HEAD'. Es conveniente eliminar las ramas adicionales cuando ya implementamos lo necesario.

- Eliminar una rama
```bash
git branch -d rama-villanos
```

>Si git marca cambios nuevos y queremos borrar de manera forzada, usar:

```bash
git branch -d rama-villanos -f
```

## Merge: Unión automática

>Crear una rama y cambiarnos a ella directamente

```bash
git checkout -b rama-villanos
```

**En la rama villanos hicimos dos commit´s, después nos cambiamos a máster e hicimos un commit**
![[ramas_5.png]]
La consola marca los dos commits en la rama de villanos.

> A continuación, para realizar un merge en la rama 'master' utilizaremos la [[Estrategia recursiva]]

```bash
git merge rama-villanos
```
 Entonces, se nos abrirá una opción visual para agregar un mensaje al Merge, puede ser **desde VSC o en la consola**
 ![[ramas_6.png]]
 Esta estrategia 'recursiva' analiza los cambios y los va a unir y esto solo lo va a hacer si no hay conflictos.
![[ramas_7.png]]
