# PENDING_WORK — plan de fases propuesto

Ninguna fase se ha ejecutado todavía. Esto es una propuesta, sujeta a la aprobación y reordenamiento
de Xavier antes de tocar cualquier archivo `.tex`.

## Fase 0 — Decisiones previas (bloqueantes, antes de tocar texto)
- Confirmar si hay más retroalimentación del profesor fuera de git (correo, verbal, Classroom).
- Decidir la visibilidad del repo de GitHub / qué hacer con `_analisis_texto` y datos personales (P0-1).
- Decidir si se recupera la estructura de 5 capítulos (Cap.4 Resultados / Cap.5 Conclusiones
  separados) o se mantiene la estructura condensada de 3 capítulos actual (P0-3).
- Confirmar si "Wali Fintech" debe nombrarse explícitamente o se omite a propósito por
  confidencialidad.
- Confirmar la relación real entre "Multicom Comercio" y "Red Total Pago Sin Límites" (P1-2).

## Fase 1 — Resolver observaciones del profesor (PF-001 a PF-016)
Ver PROFESSOR_FEEDBACK.md. Empezar por las de menor riesgo/mayor impacto:
1. Correcciones triviales primero: PF-002 (una→la organización), PF-010 (mayúsculas/acento en
   "Ingeniería en Sistemas Computacionales"), parte de PF-011 (Resumen: "claves"→"clave",
   "aplicacion"→"aplicación", quitar `\hl{[...]}`).
2. PF-012 (encabezado "Índice de figuras" en Introducción) — fix técnico de LaTeX.
3. PF-014 (título M. en C. en firma del director) — fix en `tesis.cls`.
4. PF-009 (explicar AE/OE en Capítulo 3) — depende de la decisión de Fase 0 sobre Capítulo 5.
5. PF-001, PF-003 a PF-008 (evidencia y justificaciones técnicas) — requieren redacción nueva,
   ver Fase 3.
6. PF-016 (adoptar o no el sistema de `changes` package) — decisión de flujo de trabajo.

## Fase 2 — Bibliografía
Ver BIBLIOGRAPHY_AUDIT.md. Agregar fuentes reales (no inventadas) para: Arquitectura Limpia, MVC,
REST, microservicios, y decidir si se usa o se elimina `Kaplan2009`.

## Fase 3 — Enriquecer Capítulo 2 con evidencia ya disponible
Ver ACADEMIC_DIAGNOSIS.md P1-1. Incorporar Docker, MongoDB, AWS CDK/API Gateway/Route53/AppRunner/
Cognito, JIRA, SonarAnalyzer/StyleCop, Serilog donde corresponda — con el respaldo de las cartas
y el CV ya transcritos. Esto también ayuda a resolver PF-003 (diagrama/relación herramientas-
actividades) si se agrega alguna figura o tabla resumen.

## Fase 4 — Estructura (si Fase 0 decide dividir capítulos)
Reorganizar Resultados/Conclusiones si se decide volver a 5 capítulos; renumerar referencias
cruzadas; decidir destino final de `Capitulo4.tex`/`Capitulo5.tex`/`desarrollo.tex`/`Simbolos.tex`
(eliminar o reincorporar).

## Fase 5 — Corrección puntual de coherencia (P2)
- Diferenciar las dos secciones "Contexto laboral" (P2-1).
- Revisar framing "Red Total Pago Sin Límites / Multicom" si Fase 0 lo confirma como necesario.

## Fase 6 — Limpieza LaTeX (P3)
`hyperref` duplicado, `inputenc` muerto, imágenes huérfanas (`frog.jpg`), archivos de plantilla sin
usar (`Simbolos.tex`, `desarrollo.tex`) — bajo riesgo, se puede hacer en cualquier momento.

## Fase 7 — Revisión de redacción y estilo completo
Pasada final de tono/voz/naturalidad sobre todo el documento ya con contenido estable, evitando
relleno genérico tipo IA.

## Fase 8 — Compilación final y verificación de PDF
Revisar `tesis.pdf` completo página por página, `git diff` final, decidir qué se commitea.

## Próximo paso concreto recomendado (uno solo, para arrancar)

**Fase 0, primer punto:** preguntarle a Xavier si hay retroalimentación del profesor fuera de git,
y presentarle la tabla de PROFESSOR_FEEDBACK.md para que decida el orden de atención. Es el
bloqueante de mayor impacto porque casi todas las demás fases dependen de esas decisiones.
