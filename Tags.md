Son una referencia a un commit específico en el tiempo
Normalmente los tags son utilizados para marcar **versiones o releases** de nuestro aplicativo o programas.

![[tags_1.png]]

En resumen, un tag hace referencia a un commit y a todo el estado del proyecto en ese punto específico.

## Creando Tags

```bash
git tag super-release
```

Se asocia al commit más reciente en la rama que nos encontremos.

![[tags_2.png]]

- Consultar todos los tags
```bash
git tag
```

- Borrar un tag
```bash
git tag -d super-release
```

>Se acostumbra a trabajar con el versionamiento semántico en los tags para que sean más asertivos.

```bash
 git tag -a v1.0.0 -m "Version 1.0.0 lista"
```

- Añadir un tag a un commit en específico
```bash
git tag -a v0.1.0 374ce69 -m "Version Alpha de nuestra App"
```

![[tags_3.png]]

- Obtener más información sobre un tag
```bash
git show v0.1.0
```

![[tags_4.png]]

### 🔄 Renombrar un tag

- Renombrar un tag local
Suponiendo que creamos 'v1.00' pero queriamos 'v1.0.0'
```bash
git tag v1.0.0 v1.00  # crea nuevo tag apuntando al mismo commit
git tag -d v1.00      # borra el tag viejo
```

- Si el tag era anotado '-a' y queremos que el nuevo tenga el mismo mensaje
```bash
git tag -a v1.0.0 -m "Primera versión estable" v1.00
git tag -d v1.00
```

- Renombrar tags que ya están en el repositorio
```bash
# Borrar en remoto
git push origin :refs/tags/v1.00

# Subir el nuevo
git push origin v1.0.0
```

💡 ** Importante:**
Si otros ya descargaron el tag incorrecto, deberán borrarlo localmente en su repositorio también, o verán duplicados.
