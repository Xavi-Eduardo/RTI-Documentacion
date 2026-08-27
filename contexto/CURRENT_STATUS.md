# CURRENT_STATUS — léeme primero en cada sesión nueva

Última actualización: sesión del 2026-08-27 (reorganización de `RTI-Documentacion` en carpetas).

## Dónde estamos

1. **Diagnóstico completo del RTI ya hecho.** Ver `contexto/PROJECT_CONTEXT.md`,
   `contexto/DOCUMENT_STRUCTURE.md` y `analisis/ACADEMIC_DIAGNOSIS.md`. No hace falta repetirlo
   salvo que el usuario lo pida o el documento académico haya cambiado de forma importante desde
   entonces (verificar contra el repo si hay duda).
2. **Compilación LaTeX: funcional.** XeLaTeX vía MiKTeX, recipe configurado en
   `.vscode/settings.json` del workspace del RTI. Se resolvió un problema de dependencias
   faltantes del paquete `changes` (`xstring`, `ulem`, `todonotes`, `truncate`) — todas instaladas.
   Detalle: `analisis/LATEX_DIAGNOSIS.md`.
3. **Los 16 comentarios del asesor ya están identificados, ubicados y documentados uno por uno**
   en `correcciones/correcciones.md` (formato C-001 a C-016), con su origen en
   `correcciones/PROFESSOR_FEEDBACK.md`. Los comentarios ya están integrados directamente en el
   código fuente del RTI (paquete `changes`, marcas `\comment`/`\added`/`\deleted`/`\replaced`) —
   no viven en una rama aparte, se ven al compilar el PDF actual.
4. **Todavía NO se ha aplicado ninguna corrección al `.tex`.** Estamos en fase de análisis/
   propuesta, esperando aprobación del usuario para empezar a aplicar.

## Próximo paso acordado

Aplicar primero el bloque de correcciones mecánicas (sin necesitar información adicional del
usuario): **C-001, C-002, C-003, C-006, C-014, C-016** (ver `correcciones/correcciones.md` para el
texto exacto de cada una). Después, resolver **C-005** (la más rápida de las que sí necesitan una
respuesta del usuario).

## Preguntas pendientes de respuesta del usuario

Ver la sección "Información que necesito proporcionar" al final de `correcciones/correcciones.md`
— 10 preguntas consolidadas, relacionadas con C-004, C-005, C-007 a C-013, C-015. Ninguna ha sido
respondida todavía.

## Decisiones estructurales pendientes (bloqueantes para partes del trabajo, no para todo)

- ¿Se mantiene la estructura condensada de 3 capítulos, o se recupera la de 5 (separando
  Resultados/Conclusiones de vuelta en `Capitulo4.tex`/`Capitulo5.tex`)? Ver
  `contexto/PENDING_WORK.md`, Fase 0.
- ¿Se puede nombrar el proyecto "Wali Fintech" y sus microservicios, o hay confidencialidad de por
  medio? (afecta C-010 y el framing "Red Total Pago Sin Límites / Multicom" en varios capítulos).
- ¿Se hace pública o se mantiene privada la visibilidad del repo de GitHub del RTI? (hay datos
  personales del usuario y de dos referencias laborales ya subidos en `_analisis_texto/` — ver
  `analisis/ACADEMIC_DIAGNOSIS.md`, hallazgo P0-1).

## Organización de este repositorio

Reorganizado el 2026-08-27 en carpetas (`contexto/`, `correcciones/`, `analisis/`, `bibliografia/`,
`seguimiento/`) a partir de los archivos planos que existían antes en la raíz. Ningún contenido se
eliminó, solo se movió. Ver `CLAUDE.md` para las reglas permanentes de trabajo con este proyecto.

## Estado de correcciones (resumen — detalle completo en `correcciones/correcciones.md`)

| Estado | IDs |
|---|---|
| Lista para aplicar (sin bloqueos) | C-001, C-002, C-003, C-006, C-014, C-016 |
| Requiere información del autor | C-004 (micro-decisión), C-005, C-008, C-009, C-010, C-011, C-013 |
| Requiere decisión del autor | C-007 |
| Requiere información del autor / revisar evidencia | C-012 |
| Requiere fuente | C-015 |
| Aplicada | — (ninguna todavía) |
| Verificada | — (ninguna todavía) |
