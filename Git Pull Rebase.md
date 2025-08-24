- **A continuación, procedemos a actualizar el  archivo `README.md` desde Github**

- **Después, hacemos lo mismo desde VSC actualizando la misma línea pero en el repositorio local**

### Si intentamos obtener los cambios del repositorio remoto...

```bash
git pull
```

![[github-rebase_1.png]]

>Existen dos versiones del mismo cambio en ambos repositorios, no fue posible un `Fast-forward`.

- Para resolverlo, primero cambiamos la estrategia del `pull`
```bash
git config pull.rebase true
```

>La configuración aplica de manera local *solamente en el repositorio actual*, de manera global seguimos teniendo activa la estrategia `Fast-forward`

- Después procedemos a intentar bajar los cambios para entrar en un `estado de conflicto` y resolverlo manualmente
	- Si el siguiente comando no funciona para mostrar la interfaz de resolución de conflictos
```bash
git pull
```

- Utilizar el siguiente:
```bash
git pull --no-ff
```

![[github-rebase_2.png]]

Entonces se nos mostrará la siguiente ventana que ya es familiar:

![[github-rebase_3.png]]

>Git nos marcaría un estado de `rebase`, por lo que no es recomendable realizar otro tipo de movimiento hasta que resolvamos los inconvenientes

![[github-rebase_4.png]]

- *Resolvemos el conflicto aceptando ambos cambios, realizamos un commit *

A continuación, para terminar el `rebase`:
```bash
git rebase --continue
```

Y finalmente para actualizar los cambios en el repositorio remoto:
```bash
git push
```

![[github-rebase_5.png]]

>Opcional: Establecer la estrategia de `Pull Rebase` como true de manera global

```bash
git config --global pull.rebase true
```

![[github-rebase_6.png]]

