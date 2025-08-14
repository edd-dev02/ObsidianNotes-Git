## Paso 1.
Creamos un repositorio nuevo en github

![[github_1.jpeg]]

Clic en `Create repository`
## Paso 2
Enlazar el repositorio remoto con el repositorio local en nuestra PC. Git nos dará dos opciones:
1. En caso de que **ya hayamos** iniciado un repositorio local
2. En caso de que **no hayamos** iniciado un repositorio local

![[github_2.jpeg]]

>En este caso ya iniciamos un repositorio local, por lo que utilizaremos la opción número dos con los comandos:

```bash
git remote add origin https://github.com/edd-dev02/liga-justicia.git
git branch -M main
git push -u origin main
```

>La bandera `-u` significa que este será el repositorio por defecto

![[github_3.png]]

De esta manera, ya enlazamos nuestro repositorio local con el repositorio remoto

![[github_4.jpeg]]

>*Dato: Podemos enlazar múltiples repositorios remotos en un solo repositorio local*



