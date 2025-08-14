- Añadir todos los archivos de un solo tipo extensión al stage
```bash
git add *.html
```

>El comando busca los archivos desde la raíz de la carpeta, es necesario especificar la ruta completa considerando todos los directorios

```bash
git add js/*.js
```

![[comodines_1.png]]
![[comodines_2.png]]

### ¿Cómo añadir solamente directorios vacíos al historial de versiones?
Lo hacemos añadiendo un archivo especial al directorio llamado ".gitkeep"
![[comodines_3.png]]
Entonces Git no lo ignorará y lo contemplará para añadirlo al stage
![[comodines_4.png]]

- Añadir todo el contenido de un directorio incluyendo archivos y subdirectorios
```bash
git add css/
```

- Obtener información más compacta de un status
```bash
git status --short
```
![[comodines_5.png]]
