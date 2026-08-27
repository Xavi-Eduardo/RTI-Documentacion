# LATEX_DIAGNOSIS — estado de compilación

## Resultado actual

**Compila correctamente.** Último log (`tesis.log`, 26-ago-2026 14:15): XeLaTeX vía MiKTeX 25.12,
`Output written on tesis.pdf (36 pages)`. Sin errores fatales. Un solo warning menor:

```
Overfull \vbox (15.56143pt too high) has occurred while \output is active []
```
ocurre justo después de insertar la segunda imagen de `ApendiceA.tex` (carta laboral Multicom) —
cosmético, probablemente la imagen es un poco más alta de lo que cabe en la página junto con
`\thispagestyle{empty}`. Prioridad P3 (baja).

`inputenc` también avisa (irrelevante, es normal en motores Unicode):
```
Package inputenc Warning: inputenc package ignored with utf8 based engines.
```
XeLaTeX ya es Unicode nativo, por eso `\usepackage[utf8]{inputenc}` (línea 52 de `tesis.tex`) no
hace nada — no rompe nada, pero es código muerto. Se puede quitar con seguridad si se limpia el
preámbulo, no es urgente.

BibTeX (`tesis.blg`) corrió sin warnings, usó 2 de las 3 entradas del `.bib` (ver
BIBLIOGRAPHY_AUDIT.md).

## Cómo compila hoy (mecánica real, no lo que dice la plantilla original)

- Motor: **XeLaTeX** (no pdflatex — la recomendación previa de "instala MiKTeX" terminó usándose
  con XeLaTeX porque así estaba configurado el recipe en `.vscode/settings.json` desde antes).
- Recipe en `.vscode/settings.json`: `xelatex → bibtex → xelatex → xelatex` (4 pasadas, necesarias
  para resolver bibliografía + índice + referencias cruzadas).
- Root file fijado explícitamente: `RTIExperienciaProfesional2026/tesis.tex` (vía
  `latex-workshop.latex.rootFile.path`), para que compile sin importar qué pestaña esté activa.
- Los comandos `xelatex`/`bibtex` en `settings.json` usan **rutas absolutas** a
  `C:\Users\zemog\AppData\Local\Programs\MiKTeX\miktex\bin\x64\` en vez de depender del `PATH` del
  sistema, porque el proceso de VS Code no recogía el `PATH` actualizado tras instalar MiKTeX
  (problema resuelto en la sesión anterior de este proyecto).
- No hay `latexmkrc` ni `Makefile` en el repo — todo el flujo de compilación vive únicamente en
  `.vscode/settings.json`. Si Xavier compila en otra máquina, esas rutas absolutas de MiKTeX no
  van a existir y hay que reconfigurarlas (documentado también en la memoria del asistente).

## Problemas detectados en el código LaTeX (no bloquean compilación, pero valen la pena)

1. **`hyperref` se carga dos veces** en `tesis.tex`: línea 19
   (`\usepackage[colorlinks=false,linkcolor=red]{hyperref}`) y línea 61 (`\usepackage{hyperref}`
   sin opciones). No genera error porque la segunda vez no pasa opciones nuevas, pero es
   redundante y desprolijo. P3.
2. **`\usepackage[utf8]{inputenc}`** es un no-op bajo XeLaTeX (ver warning arriba). Código muerto,
   heredado de una época en que el proyecto probablemente compilaba con pdflatex. P3.
3. **`ApendiceA.tex`** referencia las imágenes con ruta relativa hacia afuera de la carpeta del
   documento (`../_analisis_texto/imagenes/...`). Funciona hoy porque XeLaTeX corre con el cwd en
   `RTIExperienciaProfesional2026/` y sí puede subir un nivel, pero es frágil: si algún día se
   compila con una herramienta que restrinja el "root" al directorio del proyecto (Overleaf,
   algunos pipelines de CI), esta ruta fallaría. Recomendación a futuro: copiar esas dos imágenes
   dentro de `RTIExperienciaProfesional2026/` (o a una subcarpeta `imagenes/` local) en vez de
   apuntar fuera. No se ha tocado — es una decisión de organización, no urgente mientras compile
   localmente.
4. **PF-012 (comentario del profesor, ver PROFESSOR_FEEDBACK.md):** el encabezado de página
   (running head) probablemente sigue mostrando "Índice de figuras" en las páginas de la
   Introducción. Causa técnica probable: `Introduccion.tex` usa `\chapter*{Introducción}` (capítulo
   sin numerar), y `\chapter*` en LaTeX **no llama a `\@mkboth`**, por lo que no actualiza la marca
   de encabezado (`\markboth`/`\rightmark`) que define `tesis.cls` en `\ps@headings`. El resultado:
   el header sigue mostrando lo último que sí actualizó la marca (`\listoffigures`, que sí escribe
   su propio título). Esto se puede resolver agregando un `\markboth{}{Introducción}` manual justo
   después de `\chapter*{Introducción}` en `Introduccion.tex` (patrón común para este problema en
   LaTeX). **No implementado todavía** — pendiente de que Xavier apruebe el cambio.
5. **`Simbolos.tex`** tiene un typo de encoding evidente en sus comentarios de cabecera
   ("SÌmbolos" en vez de "Símbolos") — típico de un archivo guardado alguna vez con codificación
   incorrecta. No afecta la compilación porque el archivo no se incluye. Si se recupera, corregir.

## Warnings NO presentes (verificado explícitamente, para que quede registrado)

- No hay "Reference undefined" ni "Citation undefined" en el log actual.
- No hay "Overfull \\hbox" de texto (solo el `\\vbox` de imagen mencionado arriba).
- No hay errores de encoding/fuentes.
- No hay imágenes faltantes (`File ... not found`).

## Conclusión

El estado de compilación **no es el problema del proyecto ahora mismo** — el documento compila
limpio. Los problemas reales están en contenido, retroalimentación del profesor sin atender, y
bibliografía (ver los otros archivos de contexto).
