### 🔹 ¿Qué son los Teams?

- Son **grupos de miembros dentro de una organización**.
    
- Sirven para **organizar personas según su rol o proyecto** (ej. frontend, backend, QA).
    
- Facilitan la **administración de permisos** en repositorios sin tener que asignarlos uno por uno.
    

---

### 🔹 Funcionalidades principales

1. **Gestión de permisos**
    
    - Puedes dar acceso a un equipo entero a uno o varios repositorios (solo lectura, escritura, admin, etc.).
        
2. **Comunicación**
    
    - Se puede mencionar al equipo completo con `@org/team-name` en issues y PRs.
        
    - Esto notifica a todos los miembros del equipo.
        
3. **Jerarquía**
    
    - Los equipos pueden ser **anidados** (ej. `Dev` con subequipos `Frontend` y `Backend`).
        
    - Esto ayuda a reflejar la estructura real de una empresa.
        
4. **Visibilidad**
    
    - Pueden ser **públicos** (cualquiera en la organización los ve) o **privados** (solo los miembros los ven).
        
5. **Historial**
    
    - Se puede ver qué equipos tienen acceso a qué repositorios, facilitando auditorías y control.
        

---

### 🔹 Ejemplo práctico

Supongamos que tienes la organización **MegaSoft** en GitHub:

- Creas un **Team “Frontend”** → con acceso de escritura al repo `megaplay-ui`.
    
- Creas un **Team “Backend”** → con acceso admin al repo `megaplay-api`.
    
- Creas un **Team “QA”** → con acceso de solo lectura a ambos repos.
    
- Si quieres notificar a todos los testers, basta con escribir:
Nos dirigimos a la pestaña de `Teams` dentro del perfil de la organización

```
@MegaSoft/QA por favor revisen este bug.
```

![[teams_1.png]]

## Permisos en repositorios a los equipos

Una vez que creamos un equipo y asignamos un repositorio, podemos manejar el tipo de permiso para todos los miembros:

![[teams_2.png]]

Por defecto, el rol es de solo `lectura` para todos los miembros del equipo.

### 🔹 Roles de acceso en GitHub

1. **Read** (Lectura)
    
    - Ver el repositorio y su código.
        
    - Clonar y hacer _fork_.
        
    - Crear y comentar en **issues** y **pull requests**.
        
    - **No puede** subir cambios al repositorio.
        

---

2. **Triage** (Clasificación)
    
    - Pensado para colaboradores que ayudan a organizar.
        
    - Permite gestionar **issues y PRs**: etiquetar, cerrar, reabrir, asignar, etc.
        
    - **No puede** subir código ni administrar configuraciones.
        

---

3. **Write** (Escritura)
    
    - Incluye todo lo de _Read_ y _Triage_.
        
    - Puede **crear ramas y subir commits** (push).
        
    - Puede abrir y fusionar **pull requests**.
        
    - **No puede** borrar el repo ni cambiar configuraciones avanzadas.
        

---

4. **Maintain** (Mantenimiento)
    
    - Incluye todo lo de _Write_.
        
    - Puede **administrar el repo sin ser dueño**:
        
        - Gestionar ramas y etiquetas.
            
        - Manejar issues, PRs y proyectos asociados.
            
        - Administrar accesos de equipos y colaboradores.
            
    - **No puede** borrar el repo ni cambiar configuraciones críticas de seguridad.
        

---

5. **Admin** (Administrador)
    
    - Acceso total al repositorio.
        
    - Puede **cambiar cualquier configuración**, incluyendo visibilidad (público/privado).
        
    - Puede **eliminar el repo**, transferirlo o borrar ramas protegidas.
        
    - Puede administrar claves de despliegue, webhooks y secretos.

![[teams_3.png]]

## 🔹 Flujo de trabajo con dos Teams

1. **Equipo de Juniors (Team Jrs)**
    
    - **Rol asignado**: `Read` (solo lectura) en el repositorio principal.
        
    - **Acciones**:
        
        - Pueden **clonar** y **hacer un fork** del repo principal.
            
        - En su fork tienen **permisos completos de escritura**, por lo que pueden crear ramas, hacer commits y push.
            
    - **Flujo**:
        
        1. Cada Jr. crea una nueva rama en su fork (ej. `feature/login-ui`).
            
        2. Trabaja sus cambios y los sube a su fork.
            
        3. Abre un **Pull Request** desde su fork hacia la rama `main` del repo principal.
            

---

2. **Equipo de Seniors (Team Srs)**
    
    - **Rol asignado**: `Write` (escritura) en el repositorio principal.
        
    - **Acciones**:
        
        - Revisan los Pull Requests enviados por los Jrs.
            
        - Pueden comentar, solicitar cambios o aprobar los PRs.
            
        - Tienen la capacidad de **hacer merge** al repositorio principal.
            
    - **Flujo**:
        
        1. El PR llega al repo principal y queda en revisión.
            
        2. Los Srs. revisan código, estilo y pruebas.
            
        3. Si todo está correcto, hacen **merge** a `main`.
            
        4. Si no, piden correcciones al Jr., que actualiza el PR desde su fork.
            

---

## 🎯 Beneficios

- Los **Jrs.** no afectan directamente el repo principal → seguridad total.
    
- Los **Srs.** controlan la calidad y mantienen la rama principal estable.
    
- Se replica el mismo modelo que usa la mayoría de proyectos open source en GitHub.
    

---

👉 En resumen:

- **Jrs. (Read)** → fork → rama → commits → PR.
    
- **Srs. (Write)** → revisan PR → aprueban/mergean.

## Más información sobre los miembros de la organización

- Si esta en `private` solamente los miembros de la organización pueden saber quienes más están en la misma organización
- Si lo ponemos en `public` usuarios externos que **están fuera de la organización** pueden saber que pertenecemos a la organización

![[teams_4.png]]

- Con esta opción sacamos a la persona de la organización, pero aún podrá colaborar en proyectos que se le asignen, **ya no formarán parte del equipo**.

![[teams_5.png]]

