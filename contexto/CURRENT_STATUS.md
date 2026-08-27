# CURRENT_STATUS — léeme primero en cada sesión nueva

Última actualización: sesión del 2026-08-27 (respuestas de Xavier integradas + investigación
técnica/bibliográfica verificada para C-011, C-012 y C-015).

## Dónde estamos

1. **Diagnóstico completo del RTI ya hecho.** Ver `contexto/PROJECT_CONTEXT.md`,
   `contexto/DOCUMENT_STRUCTURE.md` y `analisis/ACADEMIC_DIAGNOSIS.md`. No hace falta repetirlo
   salvo que el usuario lo pida o el documento académico haya cambiado de forma importante desde
   entonces (verificar contra el repo si hay duda).
2. **Compilación LaTeX: funcional.** XeLaTeX vía MiKTeX, recipe configurado en
   `.vscode/settings.json` del workspace del RTI. Detalle: `analisis/LATEX_DIAGNOSIS.md`.
3. **13 de los 16 comentarios del asesor están LISTOS PARA APLICAR**, con texto LaTeX final en
   `correcciones/correcciones.md` (C-001 a C-016). C-007 queda parcialmente pendiente (falta el
   diagrama que Xavier está elaborando), C-013 se difiere a fase posterior por decisión de Xavier,
   y C-015 (bibliografía) está lista para que Xavier apruebe 4 fuentes propuestas antes de tocar
   `referencias.bib`.
4. **Repositorio de código real disponible:** `C:\Proyects\TQA\tqaAuditorias` (BeGlobal/auditorías).
   Se usó para verificar C-008 y C-009 con evidencia de código real (archivo:línea).
5. **Investigación técnica/bibliográfica verificada en fuentes oficiales** (Microsoft, AWS, y
   fuentes académicas primarias) para C-011 (.NET 6→10) y C-012 (Node.js 20.x→24.x en AWS Lambda) —
   ver el detalle completo y las entradas `.bib` propuestas en `correcciones/correcciones.md`.
6. **Todavía NO se ha aplicado ninguna corrección al `.tex`/`.bib` académico.** Seguimos en fase de
   propuesta, esperando aprobación explícita de Xavier para empezar a modificar el repo académico.

## Próximo paso acordado

Falta que Xavier apruebe explícitamente antes de tocar el `.tex`:
1. Aplicar el bloque de 13 correcciones listas (C-001, C-002, C-003, C-004, C-005, C-006, C-008,
   C-009, C-010, C-011, C-012, C-014, C-016).
2. Aprobar las 4 fuentes de C-015 (Martin, Krasner & Pope, Fielding, Newman) antes de agregarlas a
   `referencias.bib`, y decidir sobre `Kaplan2009`.
3. Revisar el `\comment[id=XAV]` de precaución dejado en C-010 antes de aceptarlo.
4. Esperar el diagrama de C-007 antes de darlo por resuelto.

## Preguntas pendientes de respuesta del usuario

Todas las de la ronda anterior fueron respondidas. Solo quedan las nuevas/derivadas — ver
"Preguntas que necesito responder" al final de `correcciones/correcciones.md` (C-007 diagrama,
C-010 revisión de confidencialidad, C-015 aprobación de fuentes, C-013 diferido).

## Decisiones estructurales pendientes (bloqueantes para partes del trabajo, no para todo)

- ¿Se mantiene la estructura condensada de 3 capítulos, o se recupera la de 5? Ver
  `contexto/PENDING_WORK.md`, Fase 0.
- ¿Se hace pública o se mantiene privada la visibilidad del repo de GitHub del RTI? (hay datos
  personales del usuario y de dos referencias laborales ya subidos en `_analisis_texto/` — ver
  `analisis/ACADEMIC_DIAGNOSIS.md`, hallazgo P0-1). Nota: la confidencialidad de "Wali Fintech" ya
  se resolvió (C-010, no se nombra) — esto es un tema aparte, sobre visibilidad del repo en sí.

## Organización de este repositorio

Carpetas: `contexto/`, `correcciones/`, `analisis/`, `bibliografia/`, `seguimiento/`. Ver
`CLAUDE.md` para las reglas permanentes de trabajo con este proyecto.

## Estado de correcciones (resumen — detalle completo en `correcciones/correcciones.md`)

| Estado | IDs |
|---|---|
| Lista para aplicar | C-001, C-002, C-003, C-004, C-005, C-006, C-008, C-009, C-010, C-011, C-012, C-014, C-016 |
| Pendiente de diagrama | C-007 |
| Diferido a fase posterior | C-013 |
| Lista para revisión de fuentes (bibliografía) | C-015 |
| Aplicada | — (ninguna todavía) |
| Verificada | — (ninguna todavía) |
