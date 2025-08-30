Tutorial:
https://cursos.devtalles.com/courses/take/git-github-control-versiones/lessons/35434992-pull-request-parte-2

- Si tenemos que realizar modificaciones en el Pull request de por ejemplo, un solo archivo, lo ideal es retroceder un commit anterior a ese cambio **exclusivamente para ese archivo**.

![[pr_1 1.png]]

```bash
git checkout 666351f miembros.md
```

>De esta manera, se recuperó el estado original del archivo antes de realizar nuestros cambios del Pull request

- En caso de querer realizar esta acción con varios archivos:

```bash
git checkout 666351f -- miembros.md README.md notas.md
```

⚠️ El `--` no siempre es obligatorio, pero se recomienda para que Git entienda claramente que lo que sigue son archivos y no ramas.

- Si queremos que todos los archivos se regresen al estado de ese commit:

```bash
git checkout 666351f -- .
```

Entonces, después de volver ha realizar un commit y push al repositorio del fork, nuestro Pull request se verá modificado:

![[pr_2 1.png]]

