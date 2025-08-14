# Introducción a Git y GitHub

Trabajar en proyectos de software de manera colaborativa puede ser riesgoso si todo se almacena únicamente de manera local. Por ejemplo, si el equipo sufre algún problema físico (fallo de computadora, pérdida de archivos), podríamos perder todo el historial del proyecto.  
## GitHub

GitHub es una **plataforma de desarrollo colaborativo** que permite alojar proyectos de software y trabajar en equipo.  
### Características de la versión gratuita

- Repositorios ilimitados (públicos y privados)
- Páginas HTML, CSS y JS ilimitadas (GitHub Pages)
- Push, Pull y Clones ilimitados
- Issues, Wikis y estadísticas ilimitadas
- Organizaciones ilimitadas
- Participación gratuita en proyectos privados

Para esto existen conceptos clave:

- **Push**: Envía los cambios de tu repositorio local a un servidor remoto.
- **Pull**: Trae los cambios desde el servidor remoto a tu repositorio local.
- **Clone**: Copia un repositorio remoto completo a tu máquina local.

De esta manera, varias personas pueden trabajar en el mismo proyecto de forma simultánea y sincronizada.

---

## Diferencia entre Git y GitHub

- **Git**: Sistema de control de versiones distribuido. Maneja el historial de cambios, ramas, commits y fusiones en tu máquina local.  
- **GitHub**: Plataforma que permite alojar repositorios Git en la nube, gestionar accesos y colaborar con otros desarrolladores.

> ⚠️ Git no maneja el acceso a los repositorios, eso se gestiona en servicios como GitHub.

---

## Servicios para control de accesos

### Hosted Services
Servicios que alojan repositorios y manejan accesos por ti:
- **GitHub**
- **BitBucket**
### Gestionados por nosotros mismos
Servicios que puedes instalar y administrar en tu propio servidor:
- **Gitosis**
- Otros como GitLab autohospedado

---
### Flujo de trabajo básico con GitHub

1. **Clonar un repositorio**:  
```bash
git clone https://github.com/usuario/repositorio.git
```

2. **Hacer cambios y commits**:  
```bash
git add .
git commit -m "Descripción de los cambios"
```

3. **Subir cambios al servidor (push)**:  
```bash
git push origin main
```

4. **Obtener cambios de otros colaboradores (pull)**:  
```bash
git pull origin main
```

***
## Recursos útiles

- Guardar contraseña de GitHub en Windows:  
    [Caching your GitHub credentials in Git](https://docs.github.com/en/get-started/git-basics/caching-your-github-credentials-in-git#platform-windows)

