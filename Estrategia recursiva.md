## 📌 Definición
La **estrategia recursiva** es el método por defecto que usa Git para combinar dos ramas cuando **ambas han avanzado con commits propios** desde su punto común.

Se llama "recursiva" porque, si hay **múltiples ancestros comunes** (por merges previos), Git los fusiona recursivamente para crear un **merge base virtual**, que sirve como referencia para el merge final.

---

## 🛠️ Proceso paso a paso
1. **Encontrar el ancestro común** entre las dos ramas.
2. **Si hay más de un ancestro**, fusionarlos recursivamente para generar un merge base virtual.
3. Comparar:
   - Cambios de la rama actual (`HEAD`) respecto al merge base.
   - Cambios de la rama que se va a fusionar respecto al merge base.
4. **Unir cambios**:
   - Si no hay modificaciones sobre las mismas líneas → merge automático.
   - Si hay cambios en las mismas líneas → **conflicto**, requiere intervención manual.
5. Crear un commit de merge con el resultado.

---

## 🔍 Características
- **Predeterminada** para merges de dos ramas.
- Puede resolver casos con múltiples ancestros (historial con merges previos).
- Puede terminar **sin conflictos** si los cambios no se solapan.
- Genera un commit de merge, salvo que se use `--ff-only` o `--squash`.

---

## 📘 Ejemplo
Supongamos el historial:

```css
A---B---C  (main)
     \
      D---E  (feature)
```

Al ejecutar:
```bash
git checkout main
git merge feature
```

Git:

- Detecta que el ancestro común es **B**.
    
- Compara `main` (C) y `feature` (E) contra B.
    
- Une los cambios (con o sin conflictos).

🎨 Diagrama visual

```css
      C (main)
     /
A---B
     \
      E (feature)
```

**Pasos**:

1. Encuentra `B` como ancestro común.
    
2. Si hubiera múltiples ancestros, los fusiona (merge base virtual).
    
3. Aplica los cambios de `B→C` y `B→E`.
    
4. Une resultados → Commit de merge.