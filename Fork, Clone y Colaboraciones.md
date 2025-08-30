## Caso
Se tiene un repositorio en GitHub que es público, pero nosotros no somos colaboradores, en este caso **podemos clonarlo** 
- Podremos hacer commits locales
- No podremos hacer `push` al repositorio original
### ¿Cómo podemos colaborar con el repositorio original?
Para este caso, necesitamos realizar un **Fork**, que significa tomar el repositorio original y clonarlo a un lugar en donde tenemos total acceso, ejemplo:
#### Repositorio remoto: google/maps

- Después de realizar el `fork`, veámoslo como si generamos una rama adicional **exclusivamente** para el desarrollo en especifico que tenemos en mente
#### Repositorio local: mi_usuario/maps

### ¿Qué hacer cuando queremos que los autores añadan nuestra característica?

- Tenemos que realizar un `Pull request` desde nuestra rama que creamos al realizar el `Fork`
***
## Práctica
Crearemos un `fork` el siguiente repositorio:
https://github.com/Klerith/legion-del-mal

![[fork_1.png]]

![[fork_2.png]]

![[fork_3.png]]

De esta manera,  ya contamos con la copia exacta del repositorio y nuestra propia rama

- El siguiente paso es clonar este repositorio de manera local, **ojo: no clonar el repositorio del autor original, si no, el del fork de nuestro perfil de GitHub**.

![[fork_4.png]]

- A partir de este momento, ya podemos realizar nuestros commits y subirlos a nuestro repositorio del fork
***
## Pull Request
- Después de  realizar un push con nuestros cambios, ahora vamos a realizar una petición de *contribución* desde Github
![[fork_5.png]]

Podemos observar...

1. El repositorio original al cual hicimos `fork` y la rama a la que aspiramos aplicar nuestros cambios
2. Nuestro propio repositorio y la rama que queremos mandar

![[fork_6.png]]

3. Los commits realizados

![[fork_7.png]]

>Si aún no hemos enviado el `Pull request`, tranquilamente podemos seguir realizando modificaciones al proyecto y mandar los cambios, el PR se actualizará sin problemas mostrando ahora más commits







