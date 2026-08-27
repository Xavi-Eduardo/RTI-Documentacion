# ACADEMIC_DIAGNOSIS

Clasificación por prioridad. P0 = crítico (veracidad/integridad/observaciones explícitas del
profesor). P1 = alta (coherencia/contenido/bibliografía/resultados). P2 = media (redacción,
redundancia, referencias cruzadas). P3 = baja (estilo, cosmética).

## P0 — Crítico

### P0-1. Privacidad: datos personales reales en el repositorio, ya subidos a GitHub
`_analisis_texto/` (texto e imágenes) y las dos imágenes de preview en la raíz están **trackeados
en git y confirmados en `origin/Development`** (verificado con `git ls-tree -r origin/Development`).
Contienen:
- Correo personal y teléfono de Xavier, y su domicilio particular (visible en el CV: "Pez Aguja Y
  Delfin #551").
- Nombre completo, cargo, teléfono y correo de dos referencias laborales reales (Alejandro
  Sariñana, Esteban Sosa Mendoza).
- Nombre del proyecto interno de Multicom ("Wali Fintech") y nombres de microservicios internos
  (Clients, Wallet, Auth, Access) — posible información propietaria de la empresa.
- Domicilio físico de Multicom.

**Acción recomendada:** verificar si el repositorio de GitHub (`Xavi-Eduardo/rti.seminario.experiencia`)
es privado o público. Si es público (o podría volverse público, ej. al compartir el enlace con el
comité), esto es una exposición real de datos personales de terceros, no solo de Xavier. No se
tocó nada — se reporta para que Xavier decida (hacer el repo privado, o sacar `_analisis_texto/`
del control de versiones con `.gitignore` + `git rm --cached`, conservando los archivos localmente).

### P0-2. Retroalimentación del profesor: 16 puntos, 0 resueltos
Ver PROFESSOR_FEEDBACK.md — detalle completo. Esto es el hallazgo más importante de esta sesión:
existe una rama `origin/Observaciones-06-03` con comentarios reales y específicos del director de
tesis, hecha el 10-jun-2026, que **nunca se fusionó** a la rama de trabajo actual. Ninguno de los
16 puntos está resuelto en el estado actual del documento.

### P0-3. Capítulos 4 y 5 (Resultados / Conclusiones de la plantilla original) están huérfanos
`Capitulo4.tex` y `Capitulo5.tex` conservan texto de plantilla sin completar (`\hl{[...]}`,
"Debe incluirse las conclusiones con respecto al objetivo general." repetido literalmente dos
veces) y **no están incluidos en `tesis.tex`**. El contenido real de "Resultados y Conclusiones"
vive todo junto en `Capitulo3.tex`. Esto en sí mismo puede ser una decisión de diseño válida
(condensar 5 capítulos en 3), pero:
- Deja huérfana la explicación de AE/OE que el profesor pidió (PF-009) — está en `Capitulo5.tex`,
  invisible para el lector del PDF final.
- Genera riesgo de que un revisor de la plantilla institucional pregunte por qué solo hay 3
  capítulos numerados en vez de 5.
**No se debe decidir unilateralmente** — es una decisión estructural que hay que confirmar con
Xavier (y posiblemente con el profesor) antes de tocar.

## P1 — Alta

### P1-1. El documento subutiliza la evidencia disponible en `_analisis_texto/`
Comparando `Capitulo1.tex`/`Capitulo2.tex` contra la carta de experiencia, el informe de
actividades y el CV, hay tecnologías y prácticas **bien documentadas en la evidencia** que no
aparecen para nada en el texto actual:
- **Docker y Docker Compose** (entornos locales) — CV + informe de Multicom lo mencionan.
- **MongoDB (Atlas / Compass)** en el microservicio "Access" — CV lo lista explícitamente en
  "Bases de Datos: MySQL, MongoDB".
- **AWS CDK, API Gateway, Route53, AppRunner, Cognito** — la propia carta redactada por Xavier
  menciona CDK, API Gateway y Route53 explícitamente; el CV agrega AppRunner y Cognito. El
  capítulo 2 solo menciona "AWS" genérico + una sección aislada de AWS Lambda (ver P1-3).
- **JIRA** (asignación de tareas por el líder técnico) — mencionado en el informe de Multicom.
- **SonarAnalyzer/SonarQube y StyleCop** (calidad de código) y **Serilog** (logging) — mencionados
  en el informe de Multicom, ausentes del capítulo.
Esto no es un error, es una oportunidad: el capítulo 2 podría ser más rico y específico usando
contenido que ya está evidenciado, en vez de quedarse en descripciones genéricas — y de paso
atendería parcialmente PF-003 (el profesor pidió más detalle/visualización de la relación entre
actividades y herramientas).

### P1-2. Framing de "Red Total Pago Sin Límites" como entidad separada de Multicom
El texto actual dice reiteradamente "Red Total Pago Sin Límites, en colaboración con Multicom"
(Capitulo1, Capitulo2, Introduccion, Agradecimientos), como si fueran dos organizaciones
distintas trabajando juntas. Según el CV ("Multicom | Red Total Pago sin Limite"), todo indica que
"Red Total Pago Sin Límite" es el nombre comercial/marca de Multicom, no una empresa aparte.
Ninguna de las cartas de evidencia usa "Red Total Pago Sin Límites" como membrete de una empresa
independiente. **Se recomienda que Xavier confirme la relación real** antes de decidir si se
corrige el framing (podría ser correcto si de verdad hay dos razones sociales distintas que él
conoce y la evidencia simplemente no lo aclara del todo).

### P1-3. Migración de AWS Lambda (Node.js 20.x → 24.x) sin respaldo en la evidencia disponible
`Capitulo2.tex`, sección "Actualización de runtime en AWS Lambda (Node.js 20.x a 24.x)", describe
una tarea específica y detallada que **no aparece en ninguna de las cartas, el informe de
actividades ni el CV** revisados en `_analisis_texto/`. Puede ser una actividad real que
simplemente no quedó documentada en esas cartas (las cartas no tienen por qué ser exhaustivas), o
puede ser contenido que se coló durante la reescritura y necesita verificarse. Se marca aquí en
cumplimiento explícito de la regla de Xavier: "ante falta de información, pregunta" / "no existe
evidencia suficiente en el repositorio para afirmar esto". Además, el profesor ya cuestionó esta
misma sección dos veces por otro motivo (PF-008: por qué justo esa versión).

### P1-4. AE/OE mencionados pero nunca explicados en el documento visible
Capitulo3.tex promete vincular la experiencia con "los Atributos de Egreso (AE) y los Objetivos
Educacionales (OE) del programa" en su párrafo introductorio, pero el cuerpo del capítulo no
define ni conecta explícitamente ningún AE/OE concreto — solo hay una lista genérica de
competencias sin etiquetarlas como AE/OE, y dos links de YouTube sueltos que quedaron en el
`Capitulo5.tex` huérfano. Esto es lo mismo que señaló el profesor en PF-009, y confirma que la
causa es estructural (contenido que quedó en el capítulo no incluido).

### P1-5. Bibliografía insuficiente
Ver BIBLIOGRAPHY_AUDIT.md. Confirma también PF-015.

## P2 — Media

### P2-1. "Contexto laboral" se usa como título de sección dos veces
`Capitulo2.tex` tiene **dos secciones distintas tituladas exactamente `\section{Contexto laboral}`**
(línea ~14, sobre BeGlobal, y línea ~114, sobre Multicom). Esto genera dos entradas idénticas en
el índice ("Contexto laboral" aparece dos veces sin diferenciarse), lo cual es confuso para el
lector y para la navegación del PDF (mismo texto en la tabla de contenido, sin forma de saber cuál
es cuál). Se recomienda diferenciarlas, ej. "Contexto laboral (BeGlobal Technology)" y "Contexto
laboral (Multicom / Wali Fintech)", o alguna convención similar.

### P2-2. Varios comentarios del profesor pendientes por falta de justificación técnica
PF-004, PF-005, PF-006, PF-007, PF-008 son todos del mismo tipo: el profesor pide que se explique
el "por qué" detrás de una decisión técnica (por qué esa librería, por qué esa versión, cómo se
implementó tal función). Esto es un patrón, no comentarios aislados — sugiere que, en general, el
capítulo 2 describe *qué* se hizo pero no *por qué*, y eso es lo que hay que reforzar en la
próxima pasada de redacción.

### P2-3. Inconsistencia menor de mayúsculas/acentos
"ingenieria en sistemas computacionales" (Capitulo3.tex, final de Conclusiones) — sin acento en
"ingeniería" y en minúsculas, cuando en el resto del documento la carrera se escribe correctamente
como "Ingeniería en Sistemas Computacionales". Coincide con PF-010.

## P3 — Baja / cosmética

- `hyperref` cargado dos veces en `tesis.tex` (ver LATEX_DIAGNOSIS.md).
- `\usepackage[utf8]{inputenc}` es código muerto bajo XeLaTeX.
- "Palabras claves" (debería ser "Palabras clave", singular) y "aplicacion" (falta acento) en
  `Resumen.tex`, además de que la lista de palabras clave sigue envuelta en `\hl{[...]}` como si
  fuera un placeholder sin finalizar — coincide con parte de PF-011 (rama del profesor).
- `frog.jpg` no se usa en ningún archivo incluido — parece un resto de la plantilla original.
- `Simbolos.tex` y `desarrollo.tex` son demos de plantilla sin contenido del alumno, huérfanos.
- Sección "Servicios" en Capitulo1.tex y contenido de "Área de sistemas..." en el mismo capítulo
  repiten información ya dicha en la sección "Multicom Comercio" (leve redundancia, no grave).

## Verificación de fechas / línea de tiempo

Usando únicamente lo respaldado por `_analisis_texto/` (cartas + CV) y el propio `tesis.tex`:

| Evento | Fecha según evidencia | Fecha según capítulos | ¿Coincide? |
|---|---|---|---|
| Inicio BeGlobal | Enero 2024 (CV) | "enero de 2024" (Capitulo2.tex) | Sí |
| Fin BeGlobal / inicio Multicom | Enero 2025 (CV, ambas cartas fechadas 29-30 enero 2026 dicen "desde el inicio de sus prácticas... a la fecha") | No se da una fecha explícita de inicio en Multicom en los capítulos incluidos | Sin conflicto, pero es una omisión — se podría agregar la fecha para mayor precisión, ya que sí está respaldada. |
| Fecha de las cartas de evidencia | 29 y 30 de enero de **2026** | — | Nota: son fechas futuras respecto al calendario real de cuando se redactaron por primera vez estos documentos de plantilla (el proyecto tiene commits desde marzo de 2026), pero coherente con la fecha del sistema de esta sesión (26-ago-2026) — no se detectó ninguna inconsistencia real, solo se documenta el dato tal cual aparece. |

No se encontraron inconsistencias de fechas entre el documento y la evidencia disponible.

## Nota sobre atribución de trabajo individual vs. de equipo (punto explícito de la petición de Xavier)

Se revisó específicamente si el texto se atribuye logros que la evidencia no respalda como
individuales:
- **BeGlobal:** tanto la carta redactada por Xavier como el informe de Alejandro Sariñana usan
  lenguaje de responsabilidad individual fuerte ("Fui responsable de la creación de la base de
  datos desde cero", "involucrándose en todo el ciclo de desarrollo"). El texto actual de
  Capitulo1/Capitulo2 usa voz impersonal/colectiva ("se participó", "se trabajó") — es en realidad
  **más conservador** que la propia evidencia, no hay sobre-atribución. Correcto.
- **Multicom/Wali Fintech:** el informe de actividades de Multicom aclara que las tareas se asignan
  "mediante el líder técnico... en JIRA", es decir, Xavier trabaja bajo dirección de un equipo, no
  de forma autónoma. El texto actual también usa voz colectiva/impersonal ("se participó", "el
  equipo"). Correcto, no hay sobre-atribución aquí tampoco.

**Conclusión de este punto: no se detectó ningún caso de atribución individual no sustentada.**
El único llamado de atención real es P1-3 (Lambda/Node.js) por falta de evidencia de que la
actividad haya ocurrido en absoluto, que es un problema distinto (verificabilidad de la actividad,
no de a quién se le atribuye).
