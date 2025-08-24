- Listar el `path del repositorio`
```bash
git remote -v
```

![[pull_1.png]]

- Fetch: Lugar de donde obtenemos la información
- Push: Lugar en donde depositaremos los cambios

>El origen por defecto se configuró al momento de clonar el repositorio

[[Push a Github]]

- Obtener los cambios
```bash
git pull
```

![[pull_2.png]]

- Obtener cambios de una rama en especifico
```bash
git pull origin master
```

### Configuración global para `pull` en caso de tener alguna advertencia

```bash
git config --global pull.ff only
```

Le indicamos a git cómo debe manejar los merges automáticos cuando hacemos un `git pull` al repositorio remoto, en este caso optamos por un *Fast-Forward*

![[pull_3.png]]





