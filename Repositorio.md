- Iniciar un repositorio nuevo, nos vamos a la raíz del proyecto y escribimos:
```bash
git init
```

Crea una carpeta oculta llamada .git
![[repositorio_4.png]]

>Importante nunca borrar esa carpeta, ya que es la que contiene el historial de versiones

- Cambiar el nombre de la rama principal de manera global, por defecto cada que iniciemos un nuevo repositorio la rama principal siempre se llamará main
```bash
git config --global init.defaultBranch main
```

- Cambiar el nombre de una rama en un proyecto ya inicializado (master -> main)
```bash
git branch -m master main
```

![[repositorio_5.png]]

- Comando para obtener información sobre los commits, la rama en la que nos encontramos y los archivos o directorios a los que git no les está dando seguimiento.
```bash
git status
```
![[repositorio_1.png]]
- Añadir archivos
	- Manualmente:
```bash
git add index.html
```
	- Añadir todo a la vez
```bash
git add .
```

>Si se nos presenta el problema con el CRLF, no hay que preocuparse ya que no es nada serio. Es básicamente una interpretación de un carácter.
>Utilizar el siguiente comando y quedará solucionado.

![[repositorio_3.png]]
```bash
git config core.autocrlf true
```

- Eliminar un archivo que no debía ser añadido
```bash
git reset .DS_Store 
```

- Realizar un commit
```bash
git commit -m "Primer commit"
```

>Al realizar de nuevo un git status, la consola nos dirá que no hay ningún cambio nuevo.

![[repositorio_2.png]]

##### Reconstruir el proyecto a como estaba en el último commit.
```bash
git checkout -- .
```

- Abreviar el commit en un solo comando (git add . & git commit -m)
```bash
git commit -am "Archivo actualizado"
```
>Solo funciona si anteriormente ya le habíamos dado seguimiento al archivo, pero si su estado es de Untracked entonces puede dar error.

- Observar el historial de commit´s
```bash
git log
```
![[repositorio_6.png]]
