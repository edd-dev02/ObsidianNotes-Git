# Flujo de Trabajo con GitHub Pull Requests (según Mergify)

## 1. Modelo GitHub Flow simplificado
- Cada nueva funcionalidad (o hotfix) se desarrolla en una **rama de feature**, no directamente en `main`.  
- **No existe una rama `develop`**, a diferencia de Gitflow. El desarrollo ocurre en ramas separadas y se integra solo tras revisión y pruebas.  

## 2. Revisión formal mediante Pull Request (PR)
- Creas una PR para fusionar tu rama al `main` una vez lista.
- Aquí inicia una revisión **formal** del código, donde:
  - Se verifica que cumple con los estándares del proyecto.
  - Se ejecutan pruebas automáticas (CI).  

## 3. Revisión colaborativa (Review)
- Los colaboradores revisan tu código, sugieren mejoras o aprueban.
- Es común un intercambio iterativo hasta que todo está listo:
  - Comentarios en el código.
  - Cambios adicionales en la rama según feedback.  

## 4. Fusión de la característica con `main`
- Una vez aprobado y pasando todas las pruebas, un mantenedor puede fusionar el PR a `main`.  

## 5. Comparativa con otros modelos de flujo Git
- **Gitflow**: involucra ramas dedicadas como `develop` y `release`, más compleja.  
- **Forking workflow**: ideal para proyectos open source con múltiples colaboradores, cada uno hace fork del repositorio.  
- **Feature branch workflow**: similar al GitHub Flow, pero GitHub Flow es más directo y flexible.  

---

##  Notas adicionales
- La ausencia de una rama `develop` en GitHub Flow simplifica el historial y reduce la complejidad en el flujo.  
- Las PR actúan como **puntos de control formales**, donde se revisa, prueba y colabora antes de integrar cualquier cambio al `main`.  
- Es un flujo altamente adaptable, ideal para equipos que priorizan simplicidad, colaboración y control de calidad.

---

## Referencias
https://blog.mergify.com/understanding-the-github-pull-request-workflow/
