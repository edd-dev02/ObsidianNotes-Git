La idea del `Pull request` es que nos sirva para hacer un análisis **previo a un merge**.

- Creamos un nuevo archivo desde Github y ahora seleccionamos la opción de Pull request para pedir el permiso y realizar el commit
![[pr_1.png]]

El nombre de la `rama patch` que crearemos debe tener sentido y ser referente a los cambios.

Lo siguiente que veremos será la rama  a la que queremos mandar el Pull request
![[pr_2.png]]

>En este caso, la petición será a la rama `main`

![[pr_3.png]]

De esta manera, los administradores del repositorio ahora podrán revisar nuestro nuevo cambio.

![[pr_4.png]]

Entonces, para aceptar los cambios tenemos diferentes opciones:

![[pr_5.png]]

Escogemos la mas conveniente según el caso

> Lo mas común es utilizar *Create a merge commit* y *Squash and merge*

**Importante**
- Se pueden presentar conflictos de merge y hay que resolverlos
- Si la funcionalidad ya fue aceptada, la mejor práctica es borrar la rama

![[pr_6.png]]

>Para bajar los nuevos cambios al repositorio local, ejecutamos `git pull` 

![[pr_8.png]]

![[pr_7.png]]



