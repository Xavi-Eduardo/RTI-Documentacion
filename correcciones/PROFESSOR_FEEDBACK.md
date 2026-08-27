# Retroalimentación del profesor — estado de atención

Fuente: rama remota `origin/Observaciones-06-03`, commit único `361a5d5` ("Revision junio 10"),
autor `estradafernando <festrada@uacj.mx>` (= M. en C. Jose Fernando Estrada Saldaña, director de
tesis), fecha 2026-06-10. Esta rama parte de `348fc62` (14-may-2026) y **nunca fue fusionada** a
`Development` ni a `Correccion-redaccion-cap-1-y-2` (verificado con
`git branch --all --contains 361a5d5` → solo aparece en `origin/Observaciones-06-03`).

El profesor usó comandos del paquete LaTeX `changes` (`\comment`, `\added`, `\deleted`,
`\replaced`) que él mismo configuró en `tesis.tex` (autores XAV=Xavier azul, TUT=Fernando naranja,
REV=Revisor verde). Esa infraestructura de control de cambios **tampoco existe en la rama actual**.

Todos los puntos siguientes se compararon contra el contenido real actual (revisado línea por
línea en esta sesión) — todos siguen **pendientes**, ninguno resuelto.

| ID | Archivo | Comentario original del profesor | Estado actual verificado |
|----|---------|-----------------------------------|---------------------------|
| PF-001 | Capitulo1.tex, sección "Multicom Comercio" | "En que te basas para dar esa afirmación, se necesitan evidencias" — sobre "La organización cuenta con una plataforma robusta y estable..." | **Pendiente.** La cita `\cite{MulticomSobreMulticomServicios}` existe pero está al final del párrafo siguiente, no respalda directamente esta frase subjetiva. |
| PF-002 | Capitulo1.tex, sección "Área de sistemas..." | Corrección menor ya aplicada por el profesor: "una organización" → "la organización" | **Pendiente de aplicar.** El texto actual sigue diciendo "una organización". Es un cambio trivial, se puede aplicar directo. |
| PF-003 | Capitulo2.tex, inicio del capítulo | "Yo te sugiero incluir algún tipo de gráfico o diagrama que muestre la relación entre las actividades realizadas, las herramientas utilizadas y los aprendizajes adquiridos." | **Pendiente.** No existe ningún diagrama de este tipo en el capítulo. |
| PF-004 | Capitulo2.tex, "asignación automática de responsables" (auditorías) | "¿Cómo se implementó esta funcionalidad?" | **Pendiente.** El texto sigue mencionando la funcionalidad sin explicar el cómo. |
| PF-005 | Capitulo2.tex, párrafo de JSP/AJAX/jQuery/JSON | "Se menciona JSON, AJAX y jQuery pero no explica porque se seleccionaron" | **Pendiente.** Sin justificación técnica agregada. |
| PF-006 | Capitulo2.tex, inicio de "Segundo proyecto (Red Total Pago Sin Límites / Multicom)" | "Valdría la pena poner un ejemplo concreto" | **Pendiente.** |
| PF-007 | Capitulo2.tex, "Migración y compatibilidad (.NET 6 a .NET 10)" | "Porque hasta esta versión. ¿ya es estable? ¿funcionalidad indispensable?" | **Pendiente.** |
| PF-008 | Capitulo2.tex, "Actualización de runtime en AWS Lambda (Node.js 20.x a 24.x)" | Misma pregunta: "Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?" | **Pendiente.** Nota adicional (hallazgo propio, no del profesor): esta sección no tiene respaldo en las cartas/CV de `_analisis_texto` — ver ACADEMIC_DIAGNOSIS.md. |
| PF-009 | Capitulo3.tex, párrafo introductorio (mención de AE/OE) | "Explica brevemente qué son los Atributos de Egreso y Objetivos Educacionales, para que el lector entienda la relación." | **Pendiente.** La definición de AE/OE solo existe en `Capitulo5.tex`, que **no está incluido** en `tesis.tex` (ver DOCUMENT_STRUCTURE.md). |
| PF-010 | Capitulo3.tex, párrafo final de Conclusiones | "En este caso debe de ir la primer letra de cada palabra en mayúscula, excepto preposiciones y conjunciones" — sobre "ingenieria en sistemas computacionales" | **Pendiente.** Sigue en minúsculas y sin acento: "ingenieria en sistemas computacionales" → debe ser "Ingeniería en Sistemas Computacionales". |
| PF-011 | Introduccion.tex | Profesor eliminó (`\deleted`) la frase "Con el fin de mantener un orden lógico, el documento se organiza en capítulos." con nota: "Yo quitaría el texto porque no aporta información adicional" | **Pendiente.** La frase sigue completa en el texto actual. |
| PF-012 | Introduccion.tex | "Ya no estás en ÍNDICE DE FIGURAS, así que hay que cambiarlo por introducción." | **Pendiente — requiere revisión técnica de LaTeX, no solo redacción.** Es sobre el encabezado de página (running head) que probablemente sigue mostrando "Índice de figuras" en las páginas de la Introducción porque `\chapter*` no actualiza `\markboth`/`\rightmark`. Ver LATEX_DIAGNOSIS.md. |
| PF-013 | Introduccion.tex, párrafo final | Profesor eliminó "se incluyen apartados de agradecimientos y dedicatoria, en los que se reconoce el apoyo brindado por personas e instituciones que contribuyeron al desarrollo del presente trabajo." | **Pendiente.** Sigue completo en el texto actual. |
| PF-014 | tesis.cls, macro `\approvalpage` (firma del director) | "Incluir mi título M. en C." | **Pendiente.** El bloque de firma imprime solo `\@director` (nombre), no `\@directortitle` (título). Comparar con `\maketitle`, que sí usa `{\@directortitle\ \@director}`. |
| PF-015 | tesis.tex, línea de `\bibliography{referencias}` | "Hace falta más bibliografía, por ejemplo de la tecnología referenciada" | **Pendiente.** `referencias.bib` solo tiene 2 fuentes citadas (ambas páginas web de Multicom) + 1 sin usar (Kaplan2009). No hay ninguna fuente técnica sobre Arquitectura Limpia, REST, MVC, microservicios, xUnit, etc. Ver BIBLIOGRAPHY_AUDIT.md. |
| PF-016 (hallazgo estructural, no un comentario puntual) | tesis.tex | El profesor configuró todo un sistema de control de cambios/comentarios en LaTeX (paquete `changes`, con `\xadd`, `\xdel`, `\xrep`, `\xcom`, `\tcom`, `\rcom`) pensado como mecanismo continuo de retroalimentación dentro del propio documento. | **Nunca adoptado.** No existe en la rama de trabajo actual. Vale la pena preguntarle a Xavier si quiere recuperar este flujo de trabajo (permitiría que el profesor deje comentarios directamente en el `.tex` en vez de por fuera). |

## Causa raíz de por qué nada de esto se resolvió

La rama `Correccion-redaccion-cap-1-y-2` (donde se hizo la reescritura fuerte de Capítulos 1-3,
commit `9e427d4` "Populate thesis sections and add figures", 14-may-2026) partió del mismo punto
que la rama del profesor (`348fc62`), pero **antes** de que el profesor comentara (10-jun-2026).
El desarrollo posterior (cambio de nombre de carpeta 13-ago-2026, recompilaciones) nunca trajo de
vuelta los cambios de `Observaciones-06-03`. Es decir: el commit de observaciones del profesor
quedó "huérfano" en una rama remota que nadie volvió a tocar.

## Acción recomendada inmediata

Antes de escribir una sola palabra nueva, se debería:
1. Confirmar con Xavier si haya *más* retroalimentación fuera de git (correo, verbal, PDF anotado, Classroom, etc.) que no esté capturada aquí.
2. Decidir si se quiere recuperar el mecanismo de `changes` package del profesor, o resolver los 16 puntos directamente en prosa final.
3. Priorizar PF-009/PF-015 (bibliografía y AE/OE) porque tienen efecto en cascada sobre otras secciones.
