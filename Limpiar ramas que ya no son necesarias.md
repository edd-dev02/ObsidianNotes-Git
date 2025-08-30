Se deben limpiar las siguientes ramas:
1. Feature_Rama-Villanos
2. rama-misiones

![[limpieza_1.png]]

```bash
# 1. Regresamos primero a la rama principal o en la que estaremos trabajando
git checkout main

# 2. Opcional, obtener los cambios del compañero recién añadidos (pull o merge)
git pull

# 3. Borrar la rama rama-misiones de manera local
git branch -d rama-misiones

# Opcional: Borrar la referencia de la rama rama-misiones en Origin desde local
# Si en el repositorio remoto no se ha borrado la rama, con este comando lo hará
git push origin :rama-misiones

# 4. Revisar las ramas que ya no existen en el remoto y eliminarlas localmente
git remote prune origin
```

![[limpieza_2.png]]

