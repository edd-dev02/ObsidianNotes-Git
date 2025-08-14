- Para renombrar un archivo utilizamos 'mv', en teoría esto funciona para mover de un directorio hacia otro un archivo, pero si no especificamos una ruta funciona para cambiar el nombre de un archivo:
```bash
git mv destruir-mundo.md salvar-mundo.md
```
En automático se agrega al stage, por lo que solo es necesario realizar el commit.
![[archivos_1.png]]

- Para eliminar un archivo:
```bash
git rm salvar-mundo.md
```

Repetimos el mismo proceso de realizar un commit para que el archivo deje de estar en el stage
