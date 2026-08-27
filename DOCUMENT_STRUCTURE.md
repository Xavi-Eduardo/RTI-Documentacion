# DOCUMENT_STRUCTURE — árbol real del proyecto LaTeX

## Archivo raíz

`RTIExperienciaProfesional2026/tesis.tex` (carpeta renombrada el 13-ago-2026 desde
"RTI - Experiencia Profesional 2026" — sin espacios ni guiones, por los problemas de compilación
que motivaron el renombre).

Clase: `tesis.cls` (v2.0, plantilla institucional UACJ/IIT, opciones `final, fmstyle, lic`).
Motor: XeLaTeX (ver LATEX_DIAGNOSIS.md).

## Orden real de inclusión en `tesis.tex`

```text
tesis.tex
├── \maketitle            (portada, vía tesis.cls)
├── \approvalpage          (carta "Liberación de Asesoría", tesis.cls)
├── \approvalprint         (carta "Autorización de publicación", tesis.cls)
├── \originalpage          (Declaración de Originalidad, tesis.cls)
├── \include{Agradecimientos}
├── \include{Dedicatoria}
├── \include{Resumen}
├── \tableofcontents
├── \listoffigures
├── \include{Introduccion}     ← \chapter* (sin numerar)
├── \include{Capitulo1}        ← Cap. 1 "Entorno laboral"
├── \include{Capitulo2}        ← Cap. 2 "Experiencia laboral"
├── \include{Capitulo3}        ← Cap. 3 "Resultados y Conclusiones"
├── \bibliographystyle{ieeetr} + \bibliography{referencias}
├── \appendix
└── \include{ApendiceA}        ← Ap. A "Cartas laborales" (2 imágenes)
```

## Archivos que existen en el repo pero NO se incluyen en la compilación (huérfanos)

| Archivo | Contenido | Relevancia |
|---|---|---|
| `Capitulo4.tex` | Plantilla original "Resultados" — placeholder `\hl{[...]}` sin rellenar | El contenido de "Resultados" real terminó viviendo dentro de `Capitulo3.tex` en vez de aquí. Archivo obsoleto/redundante. |
| `Capitulo5.tex` | Plantilla original "Conclusiones" — placeholder `\hl{[...]}`, con explicación de qué son Atributos de Egreso (AE) y Objetivos Educacionales (OE), enlaces de YouTube, texto sin terminar ("Debe incluirse las conclusiones..." repetido dos veces) | **Importante**: aquí está la definición de AE/OE que el profesor pidió incluir en Capítulo 3 (PF-009) y nunca se trasladó. Archivo obsoleto/redundante como bloque completo, pero contiene una pieza de contenido que sí hace falta. |
| `desarrollo.tex` | Demo genérica de la plantilla (cómo insertar figuras/teoremas/definiciones) | Puramente instructivo, no es contenido del alumno. Puede eliminarse con seguridad. |
| `Simbolos.tex` | Demo de tabla de símbolos (glosario matemático) | No aplica a este tipo de memoria profesional (no hay simbología matemática). Puede eliminarse con seguridad. |

**Recomendación (no ejecutada todavía, requiere aprobación de Xavier):** decidir si Capitulo4.tex
y Capitulo5.tex se eliminan del repo (ya que su función migró a Capitulo3.tex) o si, por el
contrario, el profesor espera la estructura clásica de 5 capítulos separados y hay que *dividir*
Capitulo3.tex de vuelta en Resultados (Cap. 4) y Conclusiones (Cap. 5). Esto cambia numeración y
es una decisión estructural, no cosmética — no tocar sin decidirlo con Xavier primero.

## Bibliografía

`referencias.bib` — 3 entradas totales, 2 citadas:
- `Kaplan2009` (artículo, "Ingenieria de requisitos") — **no citado en ningún capítulo**.
- `MulticomSobreMulticomServicios` (misc, página web Multicom) — citado en Capitulo1.tex y Capitulo2.tex.
- `MulticomMisionVision` (misc, página web Multicom) — citado en Capitulo1.tex (Misión y Visión).

Ver BIBLIOGRAPHY_AUDIT.md para el detalle y lo que el profesor pidió (PF-015).

## Imágenes

| Archivo | Uso |
|---|---|
| `Escudo-uacj2015-color-sin-fondo.png` | Logo UACJ, usado en portada (`tesis.cls`) y en `desarrollo.tex` (huérfano). |
| `frog.jpg` | No referenciada en ningún `.tex` incluido — parece un archivo de prueba de la plantilla original, sin uso. |
| `_analisis_texto/imagenes/carta_laboral_beglobal.png` | Usada en `ApendiceA.tex`. |
| `_analisis_texto/imagenes/carta_laboral.png` | Usada en `ApendiceA.tex` (carta de Multicom). |
| `_analisis_texto/imagenes/ER-MySQL-DB.png` | **No usada en ningún `.tex`.** Es un diagrama entidad-relación de la base de datos MySQL (probablemente del proyecto BeGlobal). Candidato natural para ilustrar la sección "Análisis de requerimientos y diseño inicial de base de datos" en Capitulo2.tex — hoy esa sección no tiene ninguna figura. |
| `carta_laboral_beglobal_preview.jpg`, `carta_laboral_multicom_preview.jpg` (raíz del repo) | Miniaturas/preview de las cartas, no referenciadas en LaTeX. Contienen los mismos datos personales que las cartas — ver nota de privacidad en ACADEMIC_DIAGNOSIS.md. |

## Carpeta `_analisis_texto/` (evidencia transcrita, fuera del documento compilado)

Contiene las transcripciones en texto plano de las cartas laborales, informes de actividades y CV
de Xavier. **No forma parte del documento académico compilado**, pero SÍ está versionada en git y
pusheada a GitHub. Es la fuente primaria más confiable para verificar fechas, tecnologías, roles y
nombres de proyecto — usada extensamente en ACADEMIC_DIAGNOSIS.md.

## Configuración de VS Code / compilación

`.vscode/settings.json` — define herramientas `xelatex`/`bibtex` con rutas absolutas a MiKTeX y
`latex-workshop.latex.rootFile.path` fijo. Detalle completo en LATEX_DIAGNOSIS.md.
