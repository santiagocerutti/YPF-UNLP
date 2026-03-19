# Guía simple de Git para el proyecto

Este documento explica el **workflow de Git** que usaremos para trabajar
en equipo sin pisarnos cambios.

El repositorio usa **protección en la rama `main`**, por lo que **nadie
puede hacer push directo a `main`**.\
Todos los cambios se integran mediante **Pull Requests (PR)**.

------------------------------------------------------------------------

# Estructura general

    main (rama protegida)
    │
    ├── rama_modulo_1
    ├── rama_clean_data
    └── rama_reporte_xx

Cada tarea tiene **su propia rama** y luego se abre un **Pull
Request** para integrar los cambios.

------------------------------------------------------------------------

# Paso 1 --- Empezar a trabajar

Antes de comenzar cualquier tarea:

``` bash
git checkout main
git pull
git checkout -b nombre_de_la_rama
```

Esto hace:

1.  Te mueve a `main`
2.  Descarga la versión más reciente del repositorio
3.  Crea una nueva rama para trabajar

------------------------------------------------------------------------

# Paso 2 --- Trabajar normalmente

Durante el trabajo puedes hacer todos los commits que quieras.

``` bash
git add .
git commit -m "agrega limpieza de datos"
```

Puedes trabajar varios días en tu rama sin problema.

------------------------------------------------------------------------

# Paso 3 --- Antes de subir cambios

Antes de abrir el Pull Request, debes actualizar tu rama con los cambios
recientes de `main`.

``` bash
git checkout main
git pull
git checkout nombre_de_la_rama
git merge main
```

Esto evita conflictos cuando intentes mergear.

Si Git detecta conflictos, deberás resolverlos antes de continuar.

------------------------------------------------------------------------

# Paso 4 --- Subir tu rama

``` bash
git push origin nombre_de_la_rama
```

Esto sube tu rama al repositorio en GitHub.

------------------------------------------------------------------------

# Paso 5 --- Crear el Pull Request

En GitHub aparecerá un botón:

    Compare & Pull Request

Crearás un PR:

    nombre_de_la_rama → main

Como el repositorio permite **0 approvals**, quien crea el PR puede
**mergearlo directamente**.

------------------------------------------------------------------------

# Paso 6 --- Después del merge
Una vez que el PR fue mergeado:

GitHub elimina automáticamente la rama remota

Pero la rama local sigue existiendo en tu computadora

Debes borrarla manualmente:

``` bash
git checkout main
git pull
git branch -d nombre_de_la_rama
```

Esto mantiene tu repositorio limpio y evita acumulación de ramas viejas.

------------------------------------------------------------------------
# Qué pasa si dos personas editan el mismo archivo

Puede ocurrir que dos personas modifiquen el mismo `.do`.

Hay dos casos:

### Caso 1 --- Cambios en líneas distintas

Git combina ambos cambios automáticamente.

### Caso 2 --- Cambios en la misma línea

Git genera un **conflicto** y alguien debe decidir qué versión queda.

Git marca el conflicto así:

    <<<<<<< HEAD
    cambio A
    =======
    cambio B
    >>>>>>> otra_rama

Se edita manualmente y se decide el resultado final.

------------------------------------------------------------------------

# Resumen del workflow

    git checkout main
    git pull
    git checkout -b nombre_de_la_rama

    # trabajar
    git add .
    git commit -m "mensaje"

    # antes del PR
    git checkout main
    git pull
    git checkout nombre_de_la_rama
    git merge main

    git push origin nombre_de_la_rama

Luego:

**Pull Request → Merge** (Desde Github)

Y finalmente (limpieza local):
``` bash
git checkout main
git pull
git branch -d nombre_de_la_rama
```
------------------------------------------------------------------------

Este workflow permite:

-   evitar sobrescribir cambios de otros
-   mantener un historial claro
-   trabajar en paralelo sin conflictos innecesarios
-   evitar acumulación de ramas innecesarias en el repositorio y en local
