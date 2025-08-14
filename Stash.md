`git stash` es como una **bóveda temporal** para guardar cambios de forma rápida, incluso aquellos de archivos que **Git aún no está rastreando** (_untracked_).  
Se utiliza principalmente cuando estás trabajando en una rama y surge un inconveniente que te obliga a **guardar tu trabajo pendiente de forma urgente** para poder cambiar de contexto sin perder nada.

---

## 📌 Conceptos clave

- Al hacer un **stash**, el repositorio **vuelve al último commit apuntado por el `HEAD`** en la rama actual.
    
- Al igual que en los _merge_, pueden darse diferentes escenarios al aplicar un stash:
    
    - Aplicación directa (_fast-forward_)
        
    - Conflictos que requieren resolución manual
        
- Usar muchos stashes puede ser **confuso** si no se nombran o gestionan adecuadamente.
    
- **Mejor práctica**: usar `git stash` solo para guardar cambios temporalmente, resolver el inconveniente y **recuperarlos lo antes posible**.

### Guardar cambios en un stash

```bash
git stash
```

![[stash_1.png]]

- Obtener las referencias de los stash creados
```bash
git stash list
```

El stash muestra el commit al que apunta
![[stash_2.png]]

- Recuperar el trabajo del último stash:
```bash
git stash pop
```

Después de esto va ocurrir lo siguiente:
1. En caso de tener mas stash, la posición se ira recorriendo
2. Git indicará que los cambios del stash no estan subidos al stage y no les está dando seguimiento
3. Git eliminara la marca del stash del `git log`

![[stash_3.png]]

## Conflictos con el stash
Suponiendo que modificamos la misma línea de codigo en  nuestros cambios que guardamos en el stash como en el desarrollo principal, el error se nos mostrará **exactamente igual** a un conflicto de merge, se resuelve **de la misma manera**

![[stash_4.png]]

Después, solamente guardamos cambios y aplicamos un commit.

### Residuos del stash
Muy posiblemente nos quede espacio en memoria de lo que fue un movimiento anterior de un stash , para comprobarlo aplicamos un `git stash list`
![[stash_5.png]]

- *Obligatorio después de terminar con los stash: Limpiar el historial del stash:*
```bash
git stash clear
```

### Aplicando varios stash a la vez
Modificando el archivo de 'villanos.md' agregamos varios elementos en la misma línea en diferentes stash, dando como resultado la siguiente lista:
![[stash_6.png]]

>No sabemos que movimientos se hicieron en cada stash

- Recuperar un stash en especifico para averiguar que se hizo:
```bash
git stash apply stash@{2}
```

Se sabe entonces que en ese stash se modifico el archivo 'villanos.md' y se agrego el elemento '5. Deathstroke'

![[stash_7.png]]

>Detalle: Si lo regresamos al stash, se va a crear un stash nuevo con **el mismo movimiento**, por lo que ahora tenemos **2 stash referenciando el mismo cambio**

```bash
git stash
git stash list
```

![[stash_8.png]]

>Sabemos que el stash recién creado son cambios repetidos, por lo que lo eliminaremos y tenemos dos formas de hacerlo:

- Al ser el stash más reciente podemos usar
```bash
 git stash drop
```

- Si queremos referenciar un stash en especifico
```bash
git stash drop stash@{0}
```

![[stash_9.png]]

>Obteniendo información un poco más detallada de lo que se hizo en un stash en especifico sin tener que recuperar sus cambios en el editor de código

```bash
git stash show stash@{2}
```

![[stash_10.png]]

Ahora se sabe que ese stash realizó un cambio en el archivo mencionado.

>Para evitar confusiones, *podemos agregar una descripción al stash*

```bash
git stash save "Agregamos a Loki en villanos"
```

![[stash_11.png]]

- Obtener información en general de todos los stash
```bash
git stash list --stat
```

![[stash_12.png]]

