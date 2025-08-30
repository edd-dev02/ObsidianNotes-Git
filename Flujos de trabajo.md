## Flujo mediante Pull request
No se debe trabajar directamente sobre la rama main, como mínimo debemos implementar **ramas independientes para cada feature** 

- Si ya sabemos que trabajaremos en una rama nueva, entonces crearemos una **localmente**, al momento de hacer push debemos mandar esta rama nueva al **upstream** ya que no existe de manera remota:
```bash
git branch -b "Feature_Rama-Villanos"
git add .
git commit -m "villanos.md añadido"
git push --set-upstream origin Feature_Rama-Villanos
```

![[flujoPR_1.png]]

![[flujoPR_2.png]]

>Lo siguiente es realizar un `Pull request` desde Github y finalmente borrar la rama.

