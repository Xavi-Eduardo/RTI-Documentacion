# CURRENT_STATUS — léeme primero en cada sesión nueva

Última actualización: sesión del 2026-08-27 (verificación en código real de `tqaAuditorias` para
los comentarios C-008 y C-009).

## Dónde estamos

1. **Diagnóstico completo del RTI ya hecho.** Ver `contexto/PROJECT_CONTEXT.md`,
   `contexto/DOCUMENT_STRUCTURE.md` y `analisis/ACADEMIC_DIAGNOSIS.md`. No hace falta repetirlo
   salvo que el usuario lo pida o el documento académico haya cambiado de forma importante desde
   entonces (verificar contra el repo si hay duda).
2. **Compilación LaTeX: funcional.** XeLaTeX vía MiKTeX, recipe configurado en
   `.vscode/settings.json` del workspace del RTI. Se resolvió un problema de dependencias
   faltantes del paquete `changes` (`xstring`, `ulem`, `todonotes`, `truncate`) — todas instaladas.
   Detalle: `analisis/LATEX_DIAGNOSIS.md`.
3. **Los 16 comentarios del asesor ya están identificados, ubicados y resueltos/propuestos uno por
   uno** en `correcciones/correcciones.md` (formato C-001 a C-016, con texto LaTeX listo para
   copiar en cada uno que ya se puede resolver), con su origen en `correcciones/PROFESSOR_FEEDBACK.md`.
   Los comentarios ya están integrados directamente en el código fuente del RTI (paquete `changes`,
   marcas `\comment`/`\added`/`\deleted`/`\replaced`) — no viven en una rama aparte, se ven al
   compilar el PDF actual.
4. **Nuevo repositorio disponible para verificación de código:** `C:\Proyects\TQA\tqaAuditorias`
   (proyecto real de BeGlobal/auditorías, NetBeans/Jakarta EE). Se usó para verificar C-008 y C-009
   con evidencia directa de código (archivo:línea) en vez de depender solo de las cartas.
5. **Todavía NO se ha aplicado ninguna corrección al `.tex` académico.** Estamos en fase de
   propuesta, esperando aprobación del usuario para empezar a aplicar.

## Próximo paso acordado

Aplicar primero el bloque de correcciones ya listas sin bloqueos: **C-001, C-002, C-003, C-004
(con una microdecisión opcional de estilo), C-006, C-008, C-009, C-014, C-016** (9 de 16 — ver
`correcciones/correcciones.md` para el texto exacto de cada una, incluyendo C-008 y C-009 que
ahora tienen redacción verificada en código real, no solo propuesta). Después, resolver las que
requieren respuesta del usuario, empezando por **C-005** (la más rápida).

## Preguntas pendientes de respuesta del usuario

Ver la sección "Preguntas que necesito responder" al final de `correcciones/correcciones.md` — 8
preguntas consolidadas, relacionadas con C-004 (opcional), C-005, C-007, C-010, C-011, C-012,
C-013, C-015. Ninguna ha sido respondida todavía.

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
| Lista para aplicar (sin bloqueos) | C-001, C-002, C-003, C-004, C-006, C-008, C-009, C-014, C-016 |
| Requiere información del autor | C-005, C-007, C-010, C-011, C-013 |
| Requiere información del autor / revisar evidencia | C-012 |
| Requiere fuente | C-015 |
| Aplicada | — (ninguna todavía) |
| Verificada | — (ninguna todavía) |

C-008 y C-009 pasaron de "requiere información del autor" a "lista para aplicar" tras verificar
directamente el código real de `tqaAuditorias` (ver `correcciones/correcciones.md`).
