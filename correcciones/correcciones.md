# Correcciones del asesor

Este archivo documenta **todos** los comentarios reales del M. en C. Jose Fernando Estrada Saldaña
(id `TUT` en el paquete `changes`) encontrados en el documento, verificados directamente en el
código fuente actual de `RTIExperienciaProfesional2026/` (no en una rama aparte — ya están
integrados en `tesis.tex`, `tesis.cls`, `Resumen.tex`, `Introduccion.tex`, `Capitulo1.tex`,
`Capitulo2.tex` y `Capitulo3.tex`, y el documento ya compila mostrándolos). No se encontraron
comentarios adicionales fuera de estos 16 (se revisó también `Agradecimientos.tex`,
`Dedicatoria.tex` y `ApendiceA.tex` — sin comentarios ahí).

No se modificó ningún archivo `.tex` para producir este documento.

## Tabla resumen

| ID | Sección | Comentario resumido | Estado | Prioridad |
|---|---|---|---|---|
| C-001 | Resumen | "Palabras claves"→"clave", "aplicacion"→"aplicación" (ya editado, falta aceptar) | Lista para corregir | Baja |
| C-002 | Introducción | Quitar frase "Con el fin de mantener un orden lógico..." (ya editado, falta aceptar) | Lista para corregir | Baja |
| C-003 | Introducción | Encabezado de página sigue diciendo "Índice de figuras" en vez de "Introducción" | Lista para corregir | Media |
| C-004 | Introducción | Quitar frase redundante sobre agradecimientos/dedicatoria (ya editado, falta aceptar) | Lista para corregir | Baja |
| C-005 | 1.1 Multicom Comercio | "En qué te basas para afirmar que la plataforma es robusta y estable, se necesitan evidencias" | Requiere información del autor | Alta |
| C-006 | 1.6 Área de sistemas | "una organización"→"la organización" (ya editado, falta aceptar) | Lista para corregir | Baja |
| C-007 | Cap. 2 (inicio) | Sugerencia: incluir gráfico/diagrama actividades-herramientas-aprendizajes | Requiere decisión del autor | Media |
| C-008 | 2.2.1 | "¿Cómo se implementó" la asignación automática de responsables? | Requiere información del autor | Alta |
| C-009 | 2.2.4 | Se menciona JSON/AJAX/jQuery pero no se explica por qué se eligieron | Requiere información del autor | Media |
| C-010 | 2.4 Segundo proyecto | "Valdría la pena poner un ejemplo concreto" | Requiere información del autor | Media |
| C-011 | 2.4.6 Migración .NET | "¿Por qué hasta esta versión? ¿ya es estable? ¿funcionalidad indispensable?" | Requiere información del autor | Media |
| C-012 | 2.4.7 AWS Lambda | Misma pregunta que C-011, aplicada a Node.js 20→24 | Requiere información del autor / revisar evidencia | Alta |
| C-013 | 3 (intro capítulo) | Explicar brevemente qué son los Atributos de Egreso (AE) y Objetivos Educacionales (OE) | Requiere información del autor | Alta |
| C-014 | 3.2 Conclusiones | Corregir mayúsculas/acento: "ingenieria en sistemas computacionales" | Lista para corregir | Baja |
| C-015 | Bibliografía | "Hace falta más bibliografía, por ejemplo de la tecnología referenciada" | Requiere fuente | Alta |
| C-016 | Anexo institucional (`tesis.cls`, carta de Liberación de Asesoría) | "Incluir mi título M. en C." en la firma del director | Lista para corregir | Baja |

---

## Corrección 1 — Resumen: "Palabras clave" y acentuación

### Comentario del asesor
El asesor no dejó texto en comentario aquí — hizo la corrección directamente con marcas de
control de cambios (`\deleted`, `\replaced`), que es su forma de indicar "esto está mal escrito,
así debe quedar".

### Ubicación
- Archivo: `Resumen.tex`
- Capítulo: Resumen (preliminares, numeración romana, antes del cuerpo principal)
- Sección: única
- Página aproximada: preliminares (antes de la página 1 arábiga, no aparece en el índice)
- Párrafo o fragmento afectado: línea 17, lista de palabras clave

### Texto actual
> `\textbf{Palabras clave\deleted[id=TUT]{s}}: memoria profesional, desarrollo de software, \replaced[id=TUT]{aplicación}{aplicacion} web, auditorias, APIs REST, microservicios, pruebas unitarias, AWS`

### Qué está señalando el asesor
Dos errores ortográficos: "Palabras claves" (el término correcto en español académico es
"Palabras clave", singular) y "aplicacion" (falta el acento en "aplicación").

### Qué hace falta
Aceptar las dos marcas de cambio y limpiar el texto para que quede en su forma final.

### Solución recomendada
Aceptar `\deleted[id=TUT]{s}` (queda "clave") y `\replaced[id=TUT]{aplicación}{aplicacion}` (queda
"aplicación"), dejando el texto limpio sin marcado de `changes`.

### Propuesta de texto corregido
> `\textbf{Palabras clave}: memoria profesional, desarrollo de software, aplicación web, auditorías, APIs REST, microservicios, pruebas unitarias, AWS`

Nota adicional (no señalada por el asesor, pero detectada de paso): "auditorias" también le falta
el acento ("auditorías"). Lo incluyo en la propuesta de texto porque es el mismo tipo de error que
el asesor ya está corrigiendo en la misma línea, pero avísame si prefieres que no lo toque hasta
que él lo señale explícitamente.

### Información adicional que necesito proporcionar
Ninguna. Esta corrección se puede aplicar tal cual.

### ¿Requiere fuente?
No.

### Impacto en otras secciones
Ninguno.

### Estado
**Lista para corregir.**

---

## Corrección 2 — Introducción: quitar frase sobre organización en capítulos

### Comentario del asesor
> "Yo quitaría el texto porque no aporta información adicional"

(sobre la frase que el asesor marcó como `\deleted`)

### Ubicación
- Archivo: `Introduccion.tex`
- Capítulo: Introducción
- Sección: única (chapter\*)
- Página aproximada: 2
- Párrafo o fragmento afectado: línea 18

### Texto actual
> `\deleted[id=TUT]{Con el fin de mantener un orden lógico, el documento se organiza en capítulos.} \comment[id=TUT]{ Yo quitaría el texto porque no aporta información adicional} En el Capítulo 1 se presenta el entorno laboral...`

### Qué está señalando el asesor
La frase "Con el fin de mantener un orden lógico, el documento se organiza en capítulos." es
relleno — no aporta información nueva antes de que el texto pase directamente a describir qué hay
en cada capítulo.

### Qué hace falta
Aceptar la eliminación ya marcada.

### Solución recomendada
Quitar la frase y dejar que el párrafo entre directo a "En el Capítulo 1 se presenta...".

### Propuesta de texto corregido
> "...lo cual permitió ampliar el dominio de herramientas y procesos utilizados en la industria del software.
>
> En el Capítulo 1 se presenta el entorno laboral, ofreciendo el contexto general de las organizaciones involucradas, así como información de referencia institucional y una descripción del área de trabajo y su dinámica. En el Capítulo 2 se expone la experiencia laboral de forma detallada..."

### Información adicional que necesito proporcionar
Ninguna.

### ¿Requiere fuente?
No.

### Impacto en otras secciones
Ninguno.

### Estado
**Lista para corregir.**

---

## Corrección 3 — Introducción: encabezado de página desactualizado

### Comentario del asesor
> "Ya no estás en ÍNDICE DE FIGURAS, así que hay que cambiarlo por introducción."

### Ubicación
- Archivo: `Introduccion.tex` (comentario) / posible ajuste en el propio archivo o en `tesis.cls`
- Capítulo: Introducción
- Sección: única
- Página aproximada: 2-3
- Párrafo o fragmento afectado: línea 23 (entre los dos párrafos finales)

### Texto actual
No hay texto de prosa afectado — es un comentario sobre el **encabezado de página** (running
head), no sobre el contenido.

### Qué está señalando el asesor
En las páginas de la Introducción, el encabezado superior sigue mostrando "Índice de figuras"
(el título de la sección anterior) en vez de "Introducción".

### Qué hace falta
Un ajuste técnico de LaTeX, no de redacción.

### Solución recomendada
`Introduccion.tex` usa `\chapter*{Introducción}` (capítulo sin numerar). El comando `\chapter*` de
LaTeX **no** llama a `\@mkboth`, por lo que no actualiza la marca de encabezado
(`\markboth`/`\rightmark`) que define `tesis.cls` en `\ps@headings`. El resultado es que el
encabezado conserva el último título que sí actualizó la marca (`\listoffigures`). La solución
estándar es agregar manualmente, justo después de `\chapter*{Introducción}\label{introduccion}`:
```latex
\markboth{}{Introducción}
```
Esto no cambia contenido académico, solo corrige el encabezado de página — es un ajuste de
formato/LaTeX, no de redacción.

### Propuesta de texto corregido
```latex
\chapter*{Introducción}\label{introduccion}
\markboth{}{Introducción}
```

### Información adicional que necesito proporcionar
Ninguna para aplicar el fix. Sí conviene que confirmes, después de recompilar, que el encabezado
se ve correcto en el PDF (puede que haga falta ajustar también si `\thispagestyle` o algo similar
interfiere en la primera página del capítulo, eso solo se ve compilando).

### ¿Requiere fuente?
No.

### Impacto en otras secciones
Ninguno directo, pero conviene revisar si el mismo problema ocurre en `Resumen.tex` y
`Dedicatoria.tex` (también usan `\chapter*` sin `\markboth`) — no fue señalado explícitamente por
el asesor, lo marco solo como observación relacionada, no como corrección obligatoria todavía.

### Estado
**Lista para corregir** (es un fix técnico conocido, no requiere información adicional).

---

## Corrección 4 — Introducción: quitar frase redundante sobre agradecimientos/dedicatoria

### Comentario del asesor
El asesor aplicó la marca `\deleted` directamente, sin comentario de texto adicional aquí (el
comentario de C-003 está pegado justo antes en el archivo, pero corresponde al encabezado, no a
esta frase).

### Ubicación
- Archivo: `Introduccion.tex`
- Capítulo: Introducción
- Sección: única
- Página aproximada: 2-3
- Párrafo o fragmento afectado: línea 24

### Texto actual
> `De manera complementaria, \deleted[id=TUT]{se incluyen apartados de agradecimientos y dedicatoria, en los que se reconoce el apoyo brindado por personas e instituciones que contribuyeron al desarrollo del presente trabajo.} Finalmente, se anexan las cartas laborales como evidencia documental...`

### Qué está señalando el asesor
Misma lógica que C-002: es información redundante/obvia (el lector ya vio los agradecimientos y
la dedicatoria antes de llegar a la introducción), no aporta valor nuevo.

### Qué hace falta
Aceptar la eliminación ya marcada.

### Solución recomendada
Quitar la frase y dejar la oración fluyendo directo hacia la mención de las cartas laborales.

### Propuesta de texto corregido
> "De manera complementaria, finalmente se anexan las cartas laborales como evidencia documental que valida el periodo de colaboración y las funciones desempeñadas, respaldando la información expuesta en la memoria."

(Ajusté la conjunción "De manera complementaria, finalmente" porque leído así, sin la frase
eliminada, "De manera complementaria" y "Finalmente" quedaban un poco encimados — es un ajuste
menor de conector, no de contenido. Si prefieres mantenerlo literal como quedó el `\deleted` sin
tocar nada más, dímelo y lo dejamos exactamente así: "De manera complementaria, Finalmente, se
anexan las cartas laborales...".)

### Información adicional que necesito proporcionar
Solo confirmar si prefieres el ajuste de conector que propongo o el texto literal resultante de
solo aceptar el `\deleted`.

### ¿Requiere fuente?
No.

### Impacto en otras secciones
Ninguno.

### Estado
**Lista para corregir** (con una micro-decisión de redacción pendiente, no bloqueante).

---

## Corrección 5 — Capítulo 1: afirmación sin sustento sobre Multicom

### Comentario del asesor
> "En que te basas para dar esa afirmación, se necesitan evidencias"

### Ubicación
- Archivo: `Capitulo1.tex`
- Capítulo: 1 — Entorno laboral
- Sección: 1.1 Multicom Comercio
- Página aproximada: 5
- Párrafo o fragmento afectado: línea 28

### Texto actual
> "La organización cuenta con una plataforma robusta y estable,\comment[id=TUT]{En que te basas para dar esa afirmación, se necesitan evidencias} orientada a la venta de productos de prepago, tiempo aire electrónico, pago de servicios y compra de pines electrónicos. Esta plataforma ha sido desarrollada y fortalecida a lo largo de los años, permitiendo a la empresa adaptarse a las necesidades de un mercado cambiante y ofrecer soluciones tecnológicas confiables a sus clientes.\cite{MulticomSobreMulticomServicios}"

### Qué está señalando el asesor
Se está afirmando algo (que la plataforma es "robusta y estable") sin ninguna fuente que lo
respalde directamente. Ya existe una cita (`\cite{MulticomSobreMulticomServicios}`) en el
documento, pero está al final de la oración *siguiente*, no respaldando esta afirmación
específica.

### Qué hace falta
Una de dos cosas: (a) una fuente que respalde directamente que la plataforma es "robusta y
estable", o (b) suavizar/reformular la afirmación para que no sea una aseveración categórica sin
respaldo.

### Solución recomendada
Recomiendo la opción (b) como la más segura académicamente, salvo que tengas una fuente concreta
para (a). Se puede reescribir la oración para que la caracterización de "robusta y estable" quede
ligada explícitamente a la fuente que ya existe (moviendo la cita) y/o presentarla como una
descripción institucional (lo que dice la propia empresa de sí misma en su sitio web) en vez de
una afirmación objetiva del autor.

### Propuesta de texto corregido
> "Según su información institucional, la organización cuenta con una plataforma orientada a la venta de productos de prepago, tiempo aire electrónico, pago de servicios y compra de pines electrónicos, la cual describe como robusta y estable.\cite{MulticomSobreMulticomServicios} Esta plataforma ha sido desarrollada y fortalecida a lo largo de los años..."

Esta propuesta no inventa ninguna fuente nueva — solo reubica la cita que ya existe para que
respalde directamente la afirmación, y aclara que "robusta y estable" es una caracterización de la
propia empresa, no una evaluación independiente del autor.

### Información adicional que necesito proporcionar
Para decidir entre mi propuesta (atribuir la afirmación a la fuente institucional) y una
alternativa, necesito que confirmes:

1. ¿La afirmación "robusta y estable" viene realmente de lo que dice la página web de Multicom
   (`multicomcomercio.com`), o es una impresión personal tuya basada en tu experiencia trabajando
   ahí?
2. Si es tu impresión personal, ¿tienes algún dato concreto que la sustente (por ejemplo, tiempo
   de actividad del servicio, volumen de operaciones, ausencia de caídas durante tu periodo ahí)?
   Si no, es mejor quitar el adjetivo o suavizarlo.

### ¿Requiere fuente?
**Probablemente sí** — si se mantiene la afirmación tal cual, necesita una fuente que hable
específicamente de estabilidad/robustez de la plataforma (podría ser la misma página web de
Multicom si ahí lo dice explícitamente, o quitar la afirmación si no hay respaldo).

### Impacto en otras secciones
Ninguno directo. Relacionado en espíritu con C-015 (bibliografía general insuficiente).

### Estado
**Requiere información del autor.**

---

## Corrección 6 — Capítulo 1: "una organización" → "la organización"

### Comentario del asesor
Corrección directa vía `\replaced`, sin comentario de texto.

### Ubicación
- Archivo: `Capitulo1.tex`
- Capítulo: 1 — Entorno laboral
- Sección: 1.6 Área de sistemas y desarrollo de software
- Página aproximada: 7
- Párrafo o fragmento afectado: línea 102

### Texto actual
> "...tiene como propósito crear, mantener y mejorar soluciones tecnológicas que apoyen los procesos internos o externos de \replaced[id=TUT]{la organización}{una organización}. En este contexto..."

### Qué está señalando el asesor
Corrección gramatical menor: en contexto, debe ser "la organización" (referencia específica a la
organización de la que se viene hablando), no "una organización" (genérica).

### Qué hace falta
Aceptar el reemplazo ya marcado.

### Solución recomendada
Aceptar `\replaced[id=TUT]{la organización}{una organización}` → queda "la organización".

### Propuesta de texto corregido
> "...tiene como propósito crear, mantener y mejorar soluciones tecnológicas que apoyen los procesos internos o externos de la organización. En este contexto..."

### Información adicional que necesito proporcionar
Ninguna.

### ¿Requiere fuente?
No.

### Impacto en otras secciones
Ninguno.

### Estado
**Lista para corregir.**

---

## Corrección 7 — Capítulo 2: sugerencia de gráfico/diagrama

### Comentario del asesor
> "Yo te sugiero incluir algún tipo de gráfico o diagrama que muestre la relación entre las actividades realizadas, las herramientas utilizadas y los aprendizajes adquiridos. Esto puede ayudar a visualizar mejor la experiencia laboral y su impacto en tu formación profesional."

### Ubicación
- Archivo: `Capitulo2.tex`
- Capítulo: 2 — Experiencia laboral
- Sección: inicio del capítulo (antes de 2.1)
- Página aproximada: 9
- Párrafo o fragmento afectado: línea 12

### Texto actual
> `\added[id=TUT]{Yo te sugiero incluir algún tipo de gráfico o diagrama...}` — **importante:** este comentario está marcado como `\added` (texto agregado), lo que significa que si simplemente se "acepta" el cambio sin más, el propio texto de la sugerencia del asesor quedaría impreso en el documento final como si fuera parte de tu redacción. Eso no se debe hacer — hay que **eliminar** este bloque una vez atendida la sugerencia (no aceptarlo como prosa).

### Qué está señalando el asesor
No es una corrección de un error, es una sugerencia de mejora: agregar un elemento visual
(diagrama, tabla o gráfico) que resuma la relación entre actividades, herramientas y aprendizajes
de ambas etapas.

### Qué hace falta
Decidir si se acepta la sugerencia y, si es así, decidir el formato: ¿tabla comparativa (BeGlobal
vs. Multicom), diagrama de flujo, línea de tiempo, mapa conceptual? Ya existe un recurso sin usar
en el repositorio que podría complementar esto: `_analisis_texto/imagenes/ER-MySQL-DB.png`
(diagrama entidad-relación de la base de datos de BeGlobal), aunque ese es específico de la parte
de datos, no de toda la relación actividades-herramientas-aprendizajes que pide el asesor.

### Solución recomendada
Crear una tabla (más simple de mantener en LaTeX que un diagrama, y con buen valor académico)
con columnas: Etapa | Actividad principal | Herramientas/tecnologías | Aprendizaje/competencia
fortalecida. Una fila por cada bloque temático ya existente en el capítulo (ej. una fila para
"Diseño de base de datos", otra para "Backend MVC/JSP/Servlets", etc. en BeGlobal; y filas
equivalentes para xUnit, APIs REST, EF/LINQ/Dapper, etc. en Multicom).

### Propuesta de texto corregido
No propongo la tabla completa todavía porque depende de qué actividades quieras destacar y de
cómo quieras nombrar cada "aprendizaje" — ver preguntas abajo.

### Información adicional que necesito proporcionar
1. ¿Prefieres una tabla, un diagrama (¿con qué herramienta lo generarías: TikZ, imagen externa?),
   o una línea de tiempo?
2. ¿Quieres una tabla por cada etapa (BeGlobal y Multicom por separado) o una sola tabla
   comparativa con ambas?
3. ¿Qué nivel de detalle: por actividad general (ej. "Backend") o por sub-actividad (ej. "MVC",
   "JSP", "Servlets" como filas separadas)?

### ¿Requiere fuente?
No.

### Impacto en otras secciones
Podría valer la pena mencionar la existencia de esta tabla/diagrama en el Resumen si se considera
un elemento destacado del capítulo — no obligatorio.

### Estado
**Requiere decisión del autor.**

---

## Corrección 8 — Capítulo 2: cómo se implementó la asignación automática de responsables

### Comentario del asesor
> "¿Cómo se implementó esta funcionalidad?"

### Ubicación
- Archivo: `Capitulo2.tex`
- Capítulo: 2 — Experiencia laboral
- Sección: 2.2.1 Qué problema o necesidad se atendió
- Página aproximada: 11
- Párrafo o fragmento afectado: línea 49

### Texto actual
> "Adicionalmente, se buscó incorporar una mejora orientada a la eficiencia operativa: que el sistema pudiera apoyar en la asignación automática de responsables \comment[id=TUT]{¿Cómo se implementó esta funcionalidad?} para realizar auditorías, con el objetivo de distribuir la actividad de forma más organizada y reducir la coordinación manual."

### Qué está señalando el asesor
El texto menciona la funcionalidad pero no explica el mecanismo: ¿cómo decide el sistema a quién
asignar? ¿Es una regla fija (round-robin), por disponibilidad, por área, aleatoria, manual con
sugerencia automática?

### Qué hace falta
Una explicación concreta y verificable del mecanismo de asignación (aunque sea simple), y también
aclarar si esta mejora **se llegó a implementar completamente** o quedó solo planteada (el texto
actual usa "se buscó incorporar", que es ambiguo sobre si se completó).

### Solución recomendada
Agregar 1-2 oraciones después de la mención actual explicando el criterio real de asignación
(por ejemplo: por área/departamento, de forma rotativa, por disponibilidad registrada en el
sistema, etc.) y aclarar el estado de esa funcionalidad (implementada, parcialmente implementada,
o solo diseñada).

### Propuesta de texto corregido
No puedo proponer el texto porque no existe información en el repositorio ([Consolidado en
`ACADEMIC_DIAGNOSIS.md`] revisé `_analisis_texto/` completo y no hay detalle sobre el criterio de
asignación automática) — inventar el mecanismo violaría la regla de no inventar actividades.

### Información adicional que necesito proporcionar
1. ¿Cuál era el criterio real para asignar responsables automáticamente (por área, por carga de
   trabajo, rotación, aleatorio, otro)?
2. ¿Esta funcionalidad se terminó de implementar, o quedó parcial/solo diseñada?
3. ¿Tú programaste esa lógica directamente, o fue una decisión de diseño en la que participaste
   pero alguien más la implementó?

### ¿Requiere fuente?
No — es experiencia propia, solo falta el detalle.

### Impacto en otras secciones
Capítulo 3 (Resultados) menciona "el planteamiento de una asignación automatizada de responsables
aportó una base para distribuir actividades..." — si aquí se aclara que quedó "solo planteada" (no
implementada), hay que revisar que el Capítulo 3 no la presente como un resultado logrado más
fuerte de lo que realmente fue.

### Estado
**Requiere información del autor.**

---

## Corrección 9 — Capítulo 2: justificar JSON, AJAX y jQuery

### Comentario del asesor
> "Se menciona JSON, AJAX y jQuery pero no explica porque se seleccionaron"

### Ubicación
- Archivo: `Capitulo2.tex`
- Capítulo: 2 — Experiencia laboral
- Sección: 2.2.4 Backend y lógica de negocio (Servlets y JSP) → subsección "Implementación de
  reglas de negocio y módulos principales"
- Página aproximada: 13
- Párrafo o fragmento afectado: línea 89-92

### Texto actual
> "En la práctica, se trabajó con operaciones tipo CRUD para administrar información base del sistema (catálogos y configuraciones). Para la interacción con la interfaz se utilizaron JSP apoyadas por JavaScript y librerías como jQuery, permitiendo enviar solicitudes asíncronas (AJAX) y actualizar la experiencia de usuario sin recargar páginas completas en cada acción. Cuando fue necesario, las respuestas se entregaban en formato JSON para facilitar su consumo desde el frontend, manteniendo consistencia en la comunicación entre capas. \comment[id=TUT]{Se menciona JSON, AJAX y jQuery pero no explica porque se seleccionaron}"

### Qué está señalando el asesor
Falta la justificación técnica: por qué se decidió usar jQuery (en vez de JavaScript puro u otra
librería), por qué AJAX en vez de recargar página completa, por qué JSON en vez de XML u otro
formato.

### Qué hace falta
Una breve justificación técnica de cada elección, ligada al contexto real del proyecto (por
ejemplo: jQuery ya venía integrado en el template base que se adaptó; AJAX se eligió para no
recargar la página completa en operaciones repetitivas de captura; JSON por ser el estándar
más simple de consumir desde JavaScript).

### Solución recomendada
Agregar una oración de justificación técnica inmediatamente después de mencionar estas
tecnologías, conectándolas con la necesidad real del proyecto (mejorar experiencia de usuario en
formularios de captura de auditorías, evitar recargas innecesarias, etc.).

### Propuesta de texto corregido
Propuesta condicionada a que confirmes que la razón real fue esta (es la justificación técnica más
plausible dado el contexto del capítulo, pero **no la voy a dar por hecha sin tu confirmación**):

> "...Para la interacción con la interfaz se utilizaron JSP apoyadas por JavaScript y librerías como jQuery — ya presente en el template base adoptado —, lo que permitió enviar solicitudes asíncronas (AJAX) sin recargar la página completa en cada acción de captura o consulta, mejorando la fluidez de uso durante el registro de auditorías. Cuando fue necesario, las respuestas se entregaban en formato JSON, por ser un formato ligero y de fácil consumo desde JavaScript, manteniendo consistencia en la comunicación entre capas."

### Información adicional que necesito proporcionar
1. ¿jQuery ya venía incluido en el template base que adaptaste, o lo agregaste tú deliberadamente?
2. ¿La razón principal de usar AJAX era evitar recargar la página en formularios de captura, o
   había otro motivo (por ejemplo, actualizar solo una parte de un dashboard)?
3. ¿Hubo alguna alternativa que se consideró y se descartó (por ejemplo, JavaScript puro sin
   jQuery, o XML en vez de JSON)?

### ¿Requiere fuente?
No — es una decisión técnica propia del proyecto, no una afirmación general.

### Impacto en otras secciones
Ninguno.

### Estado
**Requiere información del autor** (tengo una propuesta redactada, pero condicionada a que
confirmes que los motivos que propongo son los reales).

---

## Corrección 10 — Capítulo 2: ejemplo concreto en "Segundo proyecto"

### Comentario del asesor
> "Valdría la pena poner un ejemplo concreto"

### Ubicación
- Archivo: `Capitulo2.tex`
- Capítulo: 2 — Experiencia laboral
- Sección: 2.4 Segundo proyecto (Red Total Pago Sin Límites / Multicom)
- Página aproximada: 15
- Párrafo o fragmento afectado: línea 124

### Texto actual
> "El segundo proyecto corresponde al desarrollo y mantenimiento de una plataforma orientada a servicios digitales, construida bajo una arquitectura de microservicios.\comment[id=TUT]{Valdría la pena poner un ejemplo concreto} En este entorno se trabajaba con APIs REST, reglas de negocio distribuidas por servicio y persistencia de datos..."

### Qué está señalando el asesor
La descripción es abstracta ("plataforma orientada a servicios digitales", "arquitectura de
microservicios") sin un ejemplo concreto de qué hace la plataforma o qué tipo de microservicio.

### Qué hace falta
Un ejemplo concreto y verificable de un microservicio o funcionalidad real.

### Solución recomendada
**Nota importante de confidencialidad antes de proponer texto:** según la evidencia en
`_analisis_texto/` (carta de experiencia, informe de actividades y CV), el proyecto real se llama
**"Wali Fintech"** y los microservicios documentados se llaman **Clients, Wallet, Auth y Access**
— ninguno de estos nombres aparece hoy en el documento. No sé si la omisión del nombre del
proyecto y de los microservicios fue una decisión deliberada tuya por confidencialidad con
Multicom/el cliente, o simplemente no se incluyó todavía. Esto determina completamente cómo
redactar el ejemplo concreto que pide el asesor.

### Propuesta de texto corregido
Dos versiones, dependiendo de tu respuesta:

**Si se puede nombrar el proyecto y los microservicios:**
> "...construida bajo una arquitectura de microservicios, entre ellos los orientados a gestión de clientes, monederos digitales (wallet), autenticación y control de acceso. En este entorno se trabajaba con APIs REST..."

**Si se debe mantener genérico por confidencialidad**, se puede dar un ejemplo funcional sin
nombrar el proyecto ni los microservicios explícitamente, por ejemplo describiendo el tipo de
operación (ej. "un microservicio responsable de gestionar el saldo y las transacciones de cuentas
digitales de los usuarios") sin usar los nombres propios "Wali Fintech" ni "Wallet"/"Auth"/etc.

### Información adicional que necesito proporcionar
1. ¿Puedes nombrar el proyecto "Wali Fintech" y los microservicios (Clients, Wallet, Auth, Access)
   en el documento, o hay un acuerdo de confidencialidad con Multicom/el cliente que lo impide?
2. Si se puede dar un ejemplo, ¿hay alguna funcionalidad específica de la que te sientas cómodo
   dando más detalle (ej. un endpoint de transferencias, de autenticación, de consulta de saldo)?

### ¿Requiere fuente?
No.

### Impacto en otras secciones
Si decides nombrar "Wali Fintech", esto afectaría también el framing de "Red Total Pago Sin
Límites / Multicom" en Capítulo 1, Introducción y Agradecimientos (ver hallazgo P1-2 de
`ACADEMIC_DIAGNOSIS.md`) — son decisiones relacionadas, conviene resolverlas juntas.

### Estado
**Requiere información del autor** (y una decisión sobre confidencialidad).

---

## Corrección 11 — Capítulo 2: justificar la versión .NET 10

### Comentario del asesor
> "Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?"

### Ubicación
- Archivo: `Capitulo2.tex`
- Capítulo: 2 — Experiencia laboral
- Sección: 2.4.6 Migración y compatibilidad (.NET 6 a .NET 10)
- Página aproximada: 19
- Párrafo o fragmento afectado: línea 213-214

### Texto actual
> "Dentro de las actividades del proyecto se participó en tareas de actualización tecnológica, enfocadas en migrar servicios desarrollados en .NET 6 hacia versiones más recientes como .NET 10. \comment[id=TUT]{Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?}Esta actualización requirió identificar incompatibilidades, reemplazar funciones obsoletas y ajustar dependencias..."

### Qué está señalando el asesor
Falta justificar la decisión técnica: ¿por qué se migró específicamente a .NET 10 y no a una
versión intermedia (.NET 8, que es LTS)? ¿Ya es una versión estable? ¿Había alguna funcionalidad
de .NET 10 que fuera indispensable para el proyecto?

### Qué hace falta
Una justificación concreta de la decisión de versión, o si la decisión no fue tuya (fue del equipo
o del líder técnico), aclarar eso también.

### Solución recomendada
Agregar 1-2 oraciones explicando el motivo de la elección de versión (soporte a largo plazo,
mejoras de rendimiento específicas, alineación con el resto de los microservicios del equipo, o
simplemente que fue una decisión de arquitectura del equipo, no personal).

### Propuesta de texto corregido
No puedo proponer el texto porque no hay evidencia en el repositorio (la carta de experiencia solo
dice "actualización y migración de sistemas desarrollados originalmente en .NET 6 hacia versiones
más recientes como .NET Core 10", sin explicar el porqué de esa versión específica).

### Información adicional que necesito proporcionar
1. ¿Por qué se eligió migrar hasta .NET 10 específicamente (y no a una versión LTS anterior como
   .NET 8)?
2. ¿La decisión de versión fue tuya o del equipo/liderazgo técnico?
3. ¿Había alguna funcionalidad concreta de .NET 10 necesaria para el proyecto, o fue más bien
   "mantenerse en la versión más reciente" como política general del equipo?

### ¿Requiere fuente?
No — es una decisión técnica del proyecto, no una afirmación general sobre .NET.

### Impacto en otras secciones
Ninguno.

### Estado
**Requiere información del autor.**

---

## Corrección 12 — Capítulo 2: justificar AWS Lambda Node.js 20.x → 24.x (y verificar evidencia)

### Comentario del asesor
> "Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?" (idéntico al de C-011,
> aplicado aquí a la migración de runtime de Node.js)

### Ubicación
- Archivo: `Capitulo2.tex`
- Capítulo: 2 — Experiencia laboral
- Sección: 2.4.7 Actualización de runtime en AWS Lambda (Node.js 20.x a 24.x)
- Página aproximada: 20
- Párrafo o fragmento afectado: línea 223-224

### Texto actual
> "Como parte de actividades de mantenimiento y actualización tecnológica, se realizó la migración de funciones serverless desplegadas en AWS Lambda, actualizando el runtime de Node.js de la versión 20.x a la 24.x. \comment[id=TUT]{Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?} Esta tarea tuvo como objetivo mantener compatibilidad con versiones soportadas..."

### Qué está señalando el asesor
Misma pregunta que en C-011: por qué esa versión específica, si ya es estable, si era una
funcionalidad indispensable.

### Qué hace falta
Dos cosas, no solo una:
1. La justificación técnica que pide el asesor (igual que C-011).
2. **Un punto adicional que detecté yo, no el asesor:** esta actividad específica (migración de
   runtime de Node.js en AWS Lambda) **no aparece en ninguna de las cartas, el informe de
   actividades ni el CV** que están en `_analisis_texto/`. Toda la evidencia disponible sobre AWS
   se refiere a API Gateway, CDK, Route53, AppRunner y Cognito — nunca a Lambda/Node.js. Antes de
   redactar una justificación, hace falta confirmar que esta actividad ocurrió realmente tal como
   está descrita.

### Solución recomendada
Primero confirmar que la actividad es real y correctamente descrita; después, agregar la
justificación de versión igual que en C-011.

### Propuesta de texto corregido
No propongo texto todavía — depende de la respuesta a la pregunta de verificación.

### Información adicional que necesito proporcionar
1. **Verificación:** ¿Esta migración de runtime de Node.js en AWS Lambda realmente ocurrió como se
   describe? Ninguna de las cartas o el CV la mencionan — quiero confirmarlo contigo antes de
   seguir editando esta sección, no porque dude de tu trabajo, sino porque es la regla que
   acordamos (no dejar afirmaciones sin poder verificarlas).
2. Si sí ocurrió: ¿por qué se migró específicamente a la versión 24.x?
3. ¿Fue una decisión tuya o del equipo/AWS forzando el fin de soporte de la versión anterior
   (esto es común en Lambda, AWS deprecia runtimes con aviso previo)?

### ¿Requiere fuente?
No para la justificación de la decisión (es experiencia propia). Pero si se agrega contexto sobre
la política de deprecación de runtimes de AWS Lambda, esa sí sería una afirmación general que
convendría respaldar con la documentación oficial de AWS (no inventé ninguna referencia, solo lo
señalo como posible fuente futura si se decide agregar ese contexto).

### Impacto en otras secciones
Capítulo 3 (Resultados) menciona "actualización de runtime en funciones serverless" como parte de
los resultados — si se determina que esta actividad necesita ajustarse o no está bien evidenciada,
también hay que revisar esa mención en Resultados.

### Estado
**Requiere información del autor / requiere revisar evidencia.**

---

## Corrección 13 — Capítulo 3: explicar Atributos de Egreso (AE) y Objetivos Educacionales (OE)

### Comentario del asesor
> "Explica brevemente qué son los Atributos de Egreso y Objetivos Educacionales, para que el lector entienda la relación."

### Ubicación
- Archivo: `Capitulo3.tex`
- Capítulo: 3 — Resultados y Conclusiones
- Sección: párrafo introductorio del capítulo (antes de 3.1)
- Página aproximada: 21
- Párrafo o fragmento afectado: línea 7

### Texto actual
> "...Finalmente, se establece la relación entre la formación académica recibida y su aplicación en problemas reales del ámbito laboral, vinculando estos elementos con los Atributos de Egreso (AE) y los Objetivos Educacionales (OE) del programa.\comment[id=TUT]{Explica brevemente qué son los Atributos de Egreso y Objetivos Educacionales, para que el lector entienda la relación.}"

### Qué está señalando el asesor
El documento menciona AE y OE como si el lector ya supiera qué son, sin definirlos ni conectarlos
explícitamente con ningún contenido del capítulo.

### Qué hace falta
**Corrección respecto a lo que documenté antes en `ACADEMIC_DIAGNOSIS.md`:** revisé de nuevo
`Capitulo5.tex` (el capítulo huérfano de "Conclusiones" original) esperando encontrar ahí la
definición de AE/OE, pero **no la contiene** — solo tiene una descripción genérica del "perfil de
egreso" del programa y dos enlaces a videos de YouTube ("Ver vídeo") donde presumiblemente se
explican el AE y el OE, sin texto propio. Es decir: **la definición real de AE/OE no existe
todavía en ningún archivo del repositorio.** Se necesita el documento oficial del programa
(probablemente del coordinador de la carrera o de la página institucional) con la lista real de
Atributos de Egreso y Objetivos Educacionales de Ingeniería en Sistemas Computacionales de la
UACJ, y decidir cuáles de ellos se relacionan con tu experiencia.

### Solución recomendada
1. Conseguir el listado oficial de AE y OE del programa (Xavier debe proporcionarlo o indicar
   dónde consultarlo — los dos videos de YouTube que están en `Capitulo5.tex` son un punto de
   partida).
2. Redactar un párrafo breve definiendo qué son (una o dos oraciones) y después vincular
   explícitamente 2-3 AE/OE concretos con actividades ya descritas en el capítulo (ej. si existe
   un AE de "trabajo en equipo", conectarlo con la lista de competencias que ya aparece en
   Conclusiones).

### Propuesta de texto corregido
No puedo proponer texto todavía — no existe ninguna definición real de AE/OE en el repositorio
para trabajar con ella sin inventarla.

### Información adicional que necesito proporcionar
1. ¿Tienes el documento oficial (PDF, página web, o los videos de YouTube ya referenciados en
   `Capitulo5.tex`) con el listado real de Atributos de Egreso y Objetivos Educacionales del
   programa de Ingeniería en Sistemas Computacionales?
2. Si es por video, ¿puedes transcribir o resumir los AE/OE que se mencionan ahí para que los
   pueda usar como base?
3. ¿Hay algún AE/OE en particular que sientas más relacionado con tu experiencia (ej. trabajo en
   equipo, aprendizaje continuo, ética profesional, comunicación técnica — varios de estos ya
   aparecen como competencias en la lista de Conclusiones, solo falta etiquetarlos como AE/OE
   formales si corresponden)?

### ¿Requiere fuente?
**Sí** — necesita el documento institucional oficial de AE/OE del programa (no bibliografía
externa, sino un documento de la propia UACJ).

### Impacto en otras secciones
La lista de competencias que ya existe en la sección "Conclusiones" (líneas 46-56 de
`Capitulo3.tex`) probablemente se pueda reutilizar/conectar aquí una vez que tengamos el listado
oficial de AE/OE, en vez de crear contenido nuevo desde cero.

### Estado
**Requiere información del autor / requiere fuente (institucional).**

---

## Corrección 14 — Capítulo 3: mayúsculas y acento en "Ingeniería en Sistemas Computacionales"

### Comentario del asesor
> "En este caso debe de ir la primer letra de cada palabra en mayúscula, excepto preposiciones y conjunciones."

### Ubicación
- Archivo: `Capitulo3.tex`
- Capítulo: 3 — Resultados y Conclusiones
- Sección: 3.2 Conclusiones
- Página aproximada: 23-24
- Párrafo o fragmento afectado: línea 58-59

### Texto actual
> "...fortaleciendo la preparación para integrarse de manera competente al entorno laboral de la ingenieria en sistemas computacionales.\comment[id=TUT]{En este caso debe de ir la primer letra de cada palabra en mayúscula, excepto preposiciones y conjunciones.}"

### Qué está señalando el asesor
El nombre de la carrera debe ir en formato de nombre propio: "Ingeniería en Sistemas
Computacionales" (con mayúsculas iniciales, excepto "en"). Además, "ingenieria" le falta el acento
("Ingeniería").

### Qué hace falta
Corrección ortográfica pura, sin necesidad de información adicional.

### Solución recomendada
Reemplazar "ingenieria en sistemas computacionales" por "Ingeniería en Sistemas Computacionales",
consistente con el resto del documento (que sí usa el formato correcto en todas las demás
menciones).

### Propuesta de texto corregido
> "...fortaleciendo la preparación para integrarse de manera competente al entorno laboral de la Ingeniería en Sistemas Computacionales."

### Información adicional que necesito proporcionar
Ninguna.

### ¿Requiere fuente?
No.

### Impacto en otras secciones
Ninguno — es la única instancia mal escrita en todo el documento (verificado, el resto de menciones ya usan el formato correcto).

### Estado
**Lista para corregir.**

---

## Corrección 15 — Bibliografía: falta más bibliografía técnica

### Comentario del asesor
> "Hace falta más bibliografía, por ejemplo de la tecnología referenciada"

### Ubicación
- Archivo: `tesis.tex`
- Capítulo: N/A (línea de bibliografía, después del Capítulo 3)
- Sección: N/A
- Página aproximada: 25 (según `tesis.toc`, "Bibliografía")
- Párrafo o fragmento afectado: línea 142

### Texto actual
> `\bibliography{referencias} \comment[id=TUT]{Hace falta más bibliografía, por ejemplo de la tecnología referenciada}`

### Qué está señalando el asesor
`referencias.bib` solo tiene 3 entradas, de las cuales solo 2 están citadas, y ambas apuntan al
mismo sitio web de Multicom (`MulticomSobreMulticomServicios`, `MulticomMisionVision`). No hay
ninguna fuente técnica sobre las tecnologías y patrones mencionados a lo largo del documento
(Arquitectura Limpia, MVC, APIs REST, microservicios, etc.).

### Qué hace falta
Fuentes técnicas reales — no inventadas — para respaldar los conceptos generales que el documento
usa como si fueran hechos establecidos, no solo experiencia propia. Ver el detalle completo en
`BIBLIOGRAPHY_AUDIT.md`.

### Solución recomendada
Agregar entradas `.bib` para:
- Arquitectura Limpia / Clean Architecture (mencionada varias veces como principio de diseño).
- Patrón MVC (Modelo-Vista-Controlador).
- APIs REST como estilo arquitectónico.
- Microservicios como patrón arquitectónico.
- Posiblemente conectar `Kaplan2009` (ya existe en el `.bib` pero no está citada) con la sección de
  "Análisis de requerimientos" en el Capítulo 2.

### Propuesta de texto corregido
No propongo ninguna entrada `.bib` todavía — la regla es explícita: no inventar referencias, DOIs,
autores ni libros.

### Información adicional que necesito proporcionar
1. ¿Tienes ya en mente alguna fuente que hayas usado realmente para aprender/aplicar Arquitectura
   Limpia, MVC o REST durante la carrera o el trabajo (libro de texto de alguna materia,
   documentación oficial de Microsoft/.NET, el libro "Clean Architecture" de Robert C. Martin, algún
   curso)? Si la usaste de verdad, la citamos. Si no, busco opciones contigo y las revisamos antes
   de agregarlas — nunca las agrego sin que las veas primero.
2. ¿`Kaplan2009` ("Ingeniería de requisitos") se puede conectar con la sección de "Análisis de
   requerimientos y diseño inicial de base de datos" del Capítulo 2, o es una entrada que se puede
   eliminar por no ser relevante?

### ¿Requiere fuente?
**Sí**, es justamente lo que pide esta corrección. Tipo de fuente adecuada: libros/documentación
técnica reconocida sobre Arquitectura Limpia, MVC, REST y microservicios (no páginas web
genéricas tipo blog, dado que es un documento académico formal).

### Impacto en otras secciones
Capítulo 1 y Capítulo 2 son los que usan estos conceptos técnicos generales y se beneficiarían
directamente de las nuevas citas.

### Estado
**Requiere fuente.**

---

## Corrección 16 — Anexo institucional: incluir título del director en la firma

### Comentario del asesor
> "Incluir mi título M. en C."

### Ubicación
- Archivo: `tesis.cls`
- Capítulo: N/A — carta "Liberación de Asesoría" (macro `\approvalpage`, página institucional al
  inicio del documento)
- Sección: N/A
- Página aproximada: preliminares (numeración romana, antes de la Introducción)
- Párrafo o fragmento afectado: línea 480, dentro del bloque de firma

### Texto actual
```latex
\begin{center}
Atentamente:
\par\vspace{4\@line}
\comment[id=TUT]{Incluir mi título M. en C.}
\begin{tabular}{ccc} 
\@director	\\
Profesor Investigador \\
\end{tabular}
\end{center}
```
`\@director` solo imprime el nombre del director (definido vía `\director[opcional]{título}{nombre}`
en `tesis.tex` — el título "M. en C." se guarda aparte, en `\@directortitle`, y no se está usando
en este bloque de firma).

### Qué está señalando el asesor
La firma en esta carta específica solo muestra su nombre, sin su título académico "M. en C.". El
asesor quiere que aparezca, igual que ya aparece en la portada (`\maketitle`, que sí usa
`{\@directortitle\ \@director}`).

### Qué hace falta
Ajuste técnico simple en `tesis.cls`: usar `\@directortitle` junto con `\@director` en este bloque,
igual que ya se hace en `\maketitle`.

### Solución recomendada
Cambiar `\@director` por `\@directortitle\ \@director` dentro del `tabular` de la firma.

### Propuesta de texto corregido
```latex
\begin{center}
Atentamente:
\par\vspace{4\@line}
\begin{tabular}{ccc}
\@directortitle\ \@director	\\
Profesor Investigador \\
\end{tabular}
\end{center}
```

### Información adicional que necesito proporcionar
Ninguna — el valor de `\@directortitle` ya está definido correctamente en `tesis.tex`
(`\director{\hl{M. en C.}}{\hl{Jose Fernando Estrada Saldaña.}}`), aunque noto que ese valor
todavía está envuelto en `\hl{...}` (highlight de placeholder) — cuando se resuelva esta
corrección probablemente también convenga quitar el `\hl{}` de los datos de portada si ya están
confirmados como definitivos (no es parte de este comentario del asesor, lo menciono de paso).

### ¿Requiere fuente?
No.

### Impacto en otras secciones
Ninguno — es un archivo de clase (`tesis.cls`), no afecta el contenido académico de los capítulos.

### Estado
**Lista para corregir.**

---

# Información que necesito proporcionar

Consolidado de todas las preguntas pendientes, en el mismo orden que las correcciones:

1. **(C-004)** ¿Prefieres el ajuste de conector que propuse ("De manera complementaria,
   finalmente...") o el texto literal resultante de solo aceptar la eliminación del asesor?
2. **(C-005)** ¿La afirmación "robusta y estable" sobre la plataforma de Multicom viene de su
   página web, o es tu impresión personal? Si es personal, ¿hay algún dato concreto que la
   sustente?
3. **(C-007)** ¿Tabla, diagrama o línea de tiempo para la sugerencia de visualización del asesor?
   ¿Una tabla por etapa o una comparativa? ¿Qué nivel de detalle?
4. **(C-008)** ¿Cuál era el criterio real de la asignación automática de responsables? ¿Se llegó a
   implementar completamente? ¿La programaste tú?
5. **(C-009)** ¿jQuery ya venía en el template? ¿Por qué AJAX específicamente? ¿Se consideró
   alguna alternativa?
6. **(C-010)** ¿Se puede nombrar "Wali Fintech" y los microservicios (Clients, Wallet, Auth,
   Access), o hay confidencialidad de por medio? ¿Hay alguna funcionalidad específica que puedas
   detallar?
7. **(C-011)** ¿Por qué se migró específicamente hasta .NET 10? ¿Decisión tuya o del equipo?
8. **(C-012)** ¿La migración de runtime de Node.js en AWS Lambda realmente ocurrió? (no aparece en
   ninguna carta/CV). Si sí, ¿por qué la versión 24.x y quién decidió?
9. **(C-013)** ¿Tienes el documento oficial (o el contenido de los videos de YouTube ya
   referenciados en `Capitulo5.tex`) con el listado real de AE/OE del programa?
10. **(C-015)** ¿Qué fuente(s) reales usaste para Arquitectura Limpia/MVC/REST/microservicios?
    ¿Se conecta `Kaplan2009` con la sección de requerimientos, o se elimina?

# Fuentes que sería necesario buscar

- Arquitectura Limpia (Clean Architecture) — posible fuente: Robert C. Martin, si es lo que
  realmente usaste como referencia.
- Patrón MVC (Modelo-Vista-Controlador).
- APIs REST como estilo arquitectónico.
- Microservicios como patrón arquitectónico.
- Documento oficial de Atributos de Egreso y Objetivos Educacionales del programa de Ingeniería en
  Sistemas Computacionales, UACJ (fuente institucional, no bibliográfica en sentido estricto).
- Opcional: documentación de AWS sobre política de deprecación de runtimes de Lambda, si se decide
  agregar ese contexto a C-012.

Ninguna de estas se agregó todavía al `.bib` — son solo los temas identificados.

# Correcciones que pueden realizarse inmediatamente

(No requieren información adicional, son mecánicas o ya tienen solución técnica conocida)

- C-001 — Resumen: "Palabras clave" + acento en "aplicación" (y de paso "auditorías").
- C-002 — Introducción: quitar frase "Con el fin de mantener un orden lógico...".
- C-003 — Introducción: agregar `\markboth{}{Introducción}` para corregir el encabezado de página.
- C-006 — Capítulo 1: "una organización" → "la organización".
- C-014 — Capítulo 3: "Ingeniería en Sistemas Computacionales" con mayúsculas y acento correctos.
- C-016 — `tesis.cls`: agregar `\@directortitle` en la firma del director.

(C-004 está casi lista, solo pendiente de una micro-decisión de redacción, ver pregunta 1 arriba.)

# Correcciones que no deben realizarse todavía

(Requieren información, evidencia, fuente o una decisión tuya)

- C-005 — necesita saber en qué se basa la afirmación sobre Multicom.
- C-007 — necesita decisión de formato (tabla/diagrama) y nivel de detalle.
- C-008 — necesita detalle del mecanismo de asignación automática.
- C-009 — necesita confirmación de los motivos técnicos que propuse.
- C-010 — necesita decisión sobre confidencialidad de "Wali Fintech" y los microservicios.
- C-011 — necesita justificación de la versión .NET 10.
- C-012 — necesita **verificación** de que la actividad ocurrió, más la justificación de versión.
- C-013 — necesita el documento oficial de AE/OE.
- C-015 — necesita que confirmes qué fuentes usaste realmente (no se inventarán).

# Orden recomendado de implementación

1. **Primero, las mecánicas (C-001, C-002, C-003, C-006, C-014, C-016)** — se pueden aplicar en un
   solo commit pequeño, cero riesgo, no dependen de nada. Buen punto de partida para validar que
   el flujo de trabajo (compilar, revisar PDF, `git diff`, tú decides el commit) funciona bien.
2. **C-005** (evidencia Multicom) — depende solo de una respuesta corta tuya, bajo esfuerzo.
3. **C-009** (JSON/AJAX/jQuery) y **C-011** (.NET 10) — ambas son justificaciones técnicas cortas,
   una vez que respondas las preguntas se redactan rápido.
4. **C-012** (AWS Lambda) — primero verificar que la actividad es real; si no se puede confirmar,
   posiblemente haya que reescribir o quitar esa subsección completa, así que conviene resolverla
   antes de seguir puliendo el resto del Capítulo 2.
5. **C-010** (ejemplo concreto / confidencialidad de Wali Fintech) — es la que más impacto tiene en
   el resto del documento (Cap. 1, Introducción, Agradecimientos también usan "Red Total Pago Sin
   Límites"), conviene decidirla antes de tocar esas otras secciones.
6. **C-008** (asignación automática) — depende de tu respuesta, impacta también el Capítulo 3.
7. **C-013** (AE/OE) — probablemente la más lenta porque depende de conseguir el documento oficial
   del programa; se puede dejar en paralelo mientras se resuelve lo demás.
8. **C-007** (diagrama/tabla) — al final, porque idealmente resume actividades que ya deberían
   estar completamente correctas y ajustadas (C-008 a C-012) antes de visualizarlas.
9. **C-015** (bibliografía) — al final de todo el contenido, porque las fuentes técnicas deben
   respaldar el texto ya estabilizado, no al revés.
