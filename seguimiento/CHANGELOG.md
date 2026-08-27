# SESSION_LOG

## 2026-08-26 — Sesión 1 (LaTeX no compilaba)
- Diagnóstico y arreglo de compilación en VS Code (MiKTeX instalado pero `PATH` no se propagaba
  al proceso de VS Code). Fix aplicado: rutas absolutas a los ejecutables de MiKTeX y
  `rootFile.path` fijo en `.vscode/settings.json`. Confirmado por Xavier: "ya quedó funcionando".
  Detalle completo en la memoria persistente del asistente (`project_latex_build_setup.md`) y en
  LATEX_DIAGNOSIS.md de esta carpeta.

## 2026-08-26 — Sesión 2 (Fase de análisis, sin modificar archivos académicos)
- Xavier pidió un diagnóstico exhaustivo antes de tocar nada: repo completo, estructura LaTeX,
  contenido académico, comentarios del profesor, bibliografía, evidencias, git, compilación,
  decisiones ya tomadas.
- Hallazgo principal: existe una rama remota `origin/Observaciones-06-03` con retroalimentación
  real y específica del director de tesis (M. en C. Jose Fernando Estrada Saldaña, commit del
  10-jun-2026 usando el paquete LaTeX `changes`), que **nunca fue fusionada** a la rama de trabajo
  actual. 16 puntos identificados, ninguno resuelto. Ver PROFESSOR_FEEDBACK.md.
- Se leyó y cruzó todo el contenido de `_analisis_texto/` (cartas laborales, informes de
  actividades, CV) contra Capitulo1.tex/Capitulo2.tex/Capitulo3.tex. Se encontraron tecnologías
  bien evidenciadas pero ausentes del texto (Docker, MongoDB, AWS CDK/API Gateway/Route53/
  AppRunner/Cognito, JIRA, SonarAnalyzer/StyleCop, Serilog) y una sección (AWS Lambda Node.js
  20→24) sin respaldo encontrado en la evidencia disponible. Ver ACADEMIC_DIAGNOSIS.md.
- Se detectó que `Capitulo4.tex`/`Capitulo5.tex` (plantillas originales de Resultados/
  Conclusiones) están huérfanos (no incluidos en `tesis.tex`) y contienen texto de plantilla sin
  terminar, incluida la definición de AE/OE que el profesor pidió explicar en Capítulo 3.
- Se detectó un problema de privacidad real: `_analisis_texto/` (con datos personales de Xavier y
  de dos referencias laborales) está trackeado en git y confirmado como pusheado a
  `origin/Development` en GitHub. Pendiente que Xavier confirme visibilidad del repo.
- Confirmado que el documento compila limpio (36 páginas, sin errores, 1 warning cosmético de
  overfull vbox).
- Estado del bibliografía: 3 entradas, 2 citadas, ambas al mismo sitio web de Multicom — sin
  fuentes técnicas. Coincide con el señalamiento explícito del profesor (PF-015).
- No se modificó ningún archivo académico (`.tex`, `.bib`, imágenes) en esta sesión. Se creó
  únicamente esta carpeta de contexto fuera del repositorio, tal como pidió Xavier.
- Se entregó reporte resumido en terminal con la estructura solicitada (13 secciones) y plan de
  fases (ver PENDING_WORK.md).

## Pendiente para la próxima sesión (registrado 2026-08-26, ver actualización 2026-08-27 abajo)
- Esperar decisiones de Fase 0 (ver PENDING_WORK.md) antes de escribir/editar cualquier `.tex`.
- Si Xavier aprueba empezar, comenzar por las correcciones triviales de Fase 1 (PF-002, PF-010,
  parte de PF-011) como primer commit pequeño y verificable.

## 2026-08-27 — Sesión 3 (organización de dos repositorios)
- Xavier formalizó la separación entre el repo académico (`RTIExperienciaProfesional2026`, fuente
  de verdad) y este repo de documentación (`RTI-Documentacion`, contexto/memoria persistente).
- Se reorganizó `RTI-Documentacion` en carpetas (`contexto/`, `correcciones/`, `analisis/`,
  `bibliografia/`, `seguimiento/`), moviendo los archivos planos que ya existían (subidos
  previamente por Xavier vía GitHub, contenido idéntico al de la sesión anterior — se verificó
  byte a byte salvo fin de línea). No se eliminó ni duplicó nada.
- Se creó `CLAUDE.md` (reglas permanentes de trabajo) y `contexto/CURRENT_STATUS.md`.
- Se actualizó la memoria persistente del asistente (fuera de ambos repos) con un puntero a este
  esquema de dos repositorios.

## 2026-08-27 — Sesión 4 (resolución de comentarios del asesor, con verificación en código)
- Se resolvieron/propusieron los 16 comentarios del asesor con texto LaTeX listo para copiar,
  siguiendo el formato C-001 a C-016 en `correcciones/correcciones.md`.
- Se usó el repositorio real del proyecto BeGlobal/auditorías (`C:\Proyects\TQA\tqaAuditorias`,
  solo lectura) para verificar dos comentarios con evidencia de código en vez de suposición:
  - **C-008** (asignación automática de responsables): se confirmó que sí se diseñó e implementó
    una función completa (`AuditAssigment.setUsersToAudit`, por departamento), pero su invocación
    quedó comentada en los dos únicos puntos de integración (`Audits.java:98`,
    `AuditDepartments.java:70`) — nunca se activó. La asignación real operaba de forma manual vía
    checkboxes (`AuditAssigments` servlet, acción `checkBox`). Pasó de "requiere información del
    autor" a "lista para aplicar".
  - **C-009** (JSON/AJAX/jQuery sin justificar): se confirmó con evidencia directa que jQuery vino
    integrado en el template de dashboard adoptado, que AJAX se usó sistemáticamente para evitar
    recargas de página en formularios de captura, y que JSON fue el formato de intercambio en
    ambos sentidos (`writeJson` del lado servidor). Pasó también a "lista para aplicar".
- Resultado: de 16 comentarios, 9 quedaron listos para aplicar (antes 6), 6 requieren respuesta de
  Xavier, 1 requiere fuente bibliográfica. Ninguna corrección se aplicó todavía al `.tex` — sigue
  pendiente la aprobación de Xavier para empezar a modificar el repositorio académico.
- Se actualizaron `contexto/CURRENT_STATUS.md` y este changelog. Ningún commit/push en ningún
  repositorio.

## 2026-08-27 — Sesión 5 (respuestas de Xavier + investigación técnica/bibliográfica verificada)
- Xavier respondió las 8 preguntas pendientes de la sesión anterior. Se actualizó
  `correcciones/correcciones.md` con cada respuesta integrada, sin volver a auditar el repo
  completo (se trabajó solo sobre el contexto ya existente + investigación puntual):
  - **C-004:** confirmado ajuste de texto (no el literal).
  - **C-005:** confirmado que "robusta y estable" era apreciación personal sin sustento — se quitó
    el adjetivo, se mantiene solo la descripción factual citada.
  - **C-007:** Xavier está elaborando un diagrama — se dejó texto introductorio/posterior y un
    `figure` de marcador de posición, comentario marcado como parcialmente pendiente.
  - **C-010:** confirmado que "Wali Fintech" NO debe aparecer (confidencial) — se redactó un
    ejemplo concreto usando descripciones funcionales genéricas, sin nombres propios internos.
  - **C-011:** se investigó y verificó en fuentes oficiales de Microsoft y AWS que la causa técnica
    real no es "GitHub Actions dejó de compilar .NET 6" (impreciso) sino: (a) fin de soporte
    oficial de .NET 6 el 12-nov-2024, y (b) AWS App Runner solo ofrecía .NET 6 como runtime
    administrado y anunció el fin de soporte de ese runtime (1-dic-2025) sin agregar versiones más
    recientes. Texto reescrito con la causa correcta y 2 referencias `.bib` verificadas.
  - **C-012:** confirmado que la migración sí ocurrió. Se verificó que Node.js 19.x nunca fue un
    runtime de AWS Lambda (Xavier recordaba mal), que 20.x (la versión que ya decía el documento)
    sí es correcta, que tiene fin de soporte programado desde el 30-abr-2026, y que 24.x es un
    runtime real vigente desde nov-2025. No hizo falta cambiar los números de versión del texto
    original, solo agregar la justificación verificada.
  - **C-013:** diferido a fase posterior por decisión explícita de Xavier, sin trabajarlo.
  - **C-015:** investigación bibliográfica completa. Se proponen 4 fuentes verificadas (Robert C.
    Martin para Clean Architecture, Krasner & Pope para MVC, Fielding para REST, Sam Newman para
    microservicios), con entradas `.bib` completas y texto sugerido de dónde citarlas — pendiente
    de aprobación de Xavier antes de tocar `referencias.bib`.
- Resultado: de 16 comentarios, 13 quedaron listos para aplicar (antes 9), 1 pendiente de diagrama,
  1 diferido, 1 pendiente de aprobación de fuentes. Ninguna corrección se aplicó todavía al `.tex`
  ni al `.bib` — sigue pendiente la aprobación de Xavier para modificar el repositorio académico.
- Se actualizaron `contexto/CURRENT_STATUS.md` y este changelog. Ningún commit/push en ningún
  repositorio.

## Pendiente para la próxima sesión (actualizado 2026-08-27, sesión 5)
- Esperar aprobación de Xavier para aplicar el bloque de 13 correcciones listas.
- Esperar aprobación de las 4 fuentes bibliográficas de C-015 antes de tocar `referencias.bib`.
- Esperar el diagrama de C-007.
- C-013 queda diferido hasta que Xavier lo retome explícitamente.
