Los utilizamos para abreviar comandos que utilizamos mucho, se trata de comandos de git resumidos.

>Resumir un 'git status --short' para solo utilizar 'git s'

```bash
git config --global alias.s status --short
```

Después para terminar de configurarlo correctamente ingresamos:
```bash
git config --global -e
```

y añadimos la bandera faltante:
![[alias_1.png]]
### La manera indicada de hacerlo es con comillas:

```bash
git config --global alias.s "status --short"
```

>Resumir 'git log' en un 'git log --oneline'

```bash
git config --global alias.l "log --oneline"
```

![[alias_2.png]]

>Alias para un informe detallado de los commits

```bash
git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"
```

![[alias_3.png]]

>Alias para mostrar la rama en un `status` short

```bash
git config --global alias.s "status -sb"
```

