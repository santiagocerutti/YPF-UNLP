# YPF-UNLP

Repositorio de trabajo para organizar materiales, datos, código, documentación y entregables del proyecto YPF-UNLP.

## Objetivo

Este repositorio centraliza todo el trabajo del proyecto en una estructura simple y ordenada, separando:

- documentación y notas
- datos y código
- recursos visuales
- bibliografía
- reportes y entregables

## Estructura del repositorio

```text
YPF-UNLP/
├─ bibliography/            # Referencias bibliográficas
├─ code/                    # Scripts, notebooks y código fuente
├─ data/                    # Datos crudos, intermedios y procesados
├─ docs/                    # Documentación del proyecto
│  └─ git_workflow.md       # Flujo de trabajo con ramas y PR
├─ enviados/                # Archivos enviados/entregables (incluye PDFs versionados)
├─ figures/                 # Figuras y gráficos para reportes/presentaciones
├─ imagenes/                # Imágenes auxiliares del proyecto
├─ notes/                   # Notas de reuniones, decisiones y tareas
├─ reports/                 # Reportes en LaTeX y estilos
│  ├─ estilos/
│  │  ├─ estilo_academico.tex
│  │  └─ estilo_empresarial.tex
│  └─ reporte/
│     └─ reporte.tex
└─ tables/                  # Tablas generadas para reportes
```

## Convenciones generales

- Mantener cada tipo de recurso en su carpeta correspondiente.
- Evitar mezclar datos, figuras y código en un mismo directorio.
- Versionar solo archivos necesarios para reproducibilidad y entregas.

## Flujo de trabajo con Git

La guía completa de ramas, actualización y PR está en:

- docs/git_workflow.md

Resumen rápido:

1. Crear una rama por tarea.
2. Hacer commits pequeños y descriptivos.
3. Actualizar la rama con `main` antes del PR.
4. Integrar cambios mediante Pull Request.

## Notas sobre LaTeX

El repositorio ignora archivos temporales de compilación (por ejemplo `.aux`, `.log`, `.toc`) y también los pdf para mantener limpio el historial de Git.

Solamente se guardan los PDFs finales que se encuentren en la carpeta `enviados/` para tener un registro de entregables.

## Mantenimiento sugerido

- Completar los README internos de cada carpeta a medida que crece el proyecto.
- Documentar decisiones importantes en `docs/` o `notes/`.
- Mantener nombres de archivos y carpetas consistentes y descriptivos.
