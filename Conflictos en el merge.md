Un conflicto es cuando git no puede unir de manera automática los cambios debido a una modificación de código, sucede cuando en dos o más ramas se toca la misma línea de código y **git no sabe con que versión quedarse**.

Ejemplo de conflicto en el archivo 'misiones.md':

- Rama 'master'
![[conflictos_1.png]]

- Rama 'rama-conflicto'
![[conflictos_2.png]]

En ambas ramas se edito el mismo archivo y la misma línea.

- Intento de merge para declarar el conflicto
```bash
git merge rama-conflicto
```

![[conflictos_3.png]]

Entonces, VSC nos mostrará lo siguiente:
![[conflictos_4.png]]
Nos muestra ambas versiones del archivo

Tenemos que sobre escribir directamente el archivo y seleccionar los cambios que queremos dejar, el resultado final sería:
![[conflictos_5.png]]

Después, simplemente volvemos a subir al stage los cambios y realizamos el commit, con esto queda resuelto el conflicto.