# Correcciones del asesor

Actualizado: sesión del 2026-08-27 (segunda pasada — verificación en código real de
`C:\Proyects\TQA\tqaAuditorias` para los comentarios de la etapa BeGlobal/auditorías).

Este documento reemplaza y actualiza la versión anterior (misma fecha, primera pasada). No se
perdió nada del análisis previo — se conserva la ubicación exacta, el texto actual, el análisis y
las preguntas de cada comentario, y se **añade** para cada uno: el comentario en bloque LaTeX
literal, el texto sugerido listo para copiar en bloque LaTeX, el campo "Referencia necesaria" con
justificación explícita, y — para los dos comentarios de la etapa BeGlobal que lo permitían —
verificación directa contra el código fuente real del proyecto en `tqaAuditorias`.

**Ningún `.tex` fue modificado. Ningún commit ni push se realizó**, en ninguno de los tres
repositorios (RTI académico, RTI-Documentacion, tqaAuditorias — este último ni siquiera se abrió
en modo escritura, solo lectura).

## Resumen

```text
Comentarios encontrados: 16
Listos para aplicar: 9   (C-001, C-002, C-003, C-004, C-006, C-008, C-009, C-014, C-016)
Requieren información del autor: 6   (C-005, C-007, C-010, C-011, C-012, C-013)
Requieren fuente: 1   (C-015 — además C-005 y C-013 requieren fuente/documento como parte de su resolución, contadas también en "información del autor" porque dependen de una respuesta previa de Xavier)
Requieren verificación adicional: 1   (C-012, sobre si la actividad de AWS Lambda ocurrió tal como está descrita)
```

## Tabla resumen

| ID | Sección | Comentario resumido | Estado |
|---|---|---|---|
| C-001 | Resumen | "Palabras claves"→"clave", "aplicacion"→"aplicación" | LISTO PARA APLICAR |
| C-002 | Introducción | Quitar frase "Con el fin de mantener un orden lógico..." | LISTO PARA APLICAR |
| C-003 | Introducción | Encabezado de página "Índice de figuras" desactualizado | LISTO PARA APLICAR |
| C-004 | Introducción | Quitar frase redundante sobre agradecimientos/dedicatoria | LISTO PARA APLICAR |
| C-005 | 1.1 Multicom Comercio | "¿En qué te basas...? Se necesitan evidencias" | REQUIERE RESPUESTA DEL AUTOR |
| C-006 | 1.6 Área de sistemas | "una organización"→"la organización" | LISTO PARA APLICAR |
| C-007 | Cap. 2 (inicio) | Sugerencia de gráfico/diagrama actividades-herramientas | REQUIERE RESPUESTA DEL AUTOR |
| C-008 | 2.2.1 | "¿Cómo se implementó" la asignación automática de responsables? | **LISTO PARA APLICAR** (verificado en código) |
| C-009 | 2.2.4 | JSON/AJAX/jQuery sin justificar | **LISTO PARA APLICAR** (verificado en código) |
| C-010 | 2.4 Segundo proyecto | Falta ejemplo concreto | REQUIERE RESPUESTA DEL AUTOR |
| C-011 | 2.4.6 Migración .NET | Por qué .NET 10, ¿estable? | REQUIERE RESPUESTA DEL AUTOR |
| C-012 | 2.4.7 AWS Lambda | Misma pregunta + falta evidencia de que ocurrió | REQUIERE VERIFICACIÓN + RESPUESTA DEL AUTOR |
| C-013 | 3 (intro capítulo) | Explicar AE/OE | REQUIERE RESPUESTA DEL AUTOR (documento oficial) |
| C-014 | 3.2 Conclusiones | Mayúsculas/acento "Ingeniería en Sistemas Computacionales" | LISTO PARA APLICAR |
| C-015 | Bibliografía | Falta bibliografía técnica | REQUIERE FUENTE |
| C-016 | `tesis.cls` (carta institucional) | Incluir título M. en C. del director | LISTO PARA APLICAR |

---

## C-001 — Resumen: "Palabras clave" y acentuación

### Comentario del asesor
No hay comentario de texto — el asesor corrigió directamente con marcas de control de cambios.

### Texto actual relacionado
```latex
\textbf{Palabras clave\deleted[id=TUT]{s}}: memoria profesional, desarrollo de software, \replaced[id=TUT]{aplicación}{aplicacion} web, auditorias, APIs REST, microservicios, pruebas unitarias, AWS
```
Ubicación: `Resumen.tex`, línea 17.

### Qué está solicitando el asesor
Corregir "Palabras claves" → "Palabras clave" (singular correcto) y "aplicacion" → "aplicación"
(acento faltante).

### Solución
Aceptar las dos marcas de cambio y limpiar el texto. De paso corrijo "auditorias" → "auditorías"
(mismo tipo de error, en la misma línea, no señalado explícitamente por el asesor pero evidente).

### Texto sugerido en LaTeX
```latex
\textbf{Palabras clave}: memoria profesional, desarrollo de software, aplicación web, auditorías, APIs REST, microservicios, pruebas unitarias, AWS
```

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR.**

---

## C-002 — Introducción: quitar frase sobre organización en capítulos

### Comentario del asesor
```latex
\comment[id=TUT]{ Yo quitaría el texto porque no aporta información adicional}
```
(sobre el fragmento marcado `\deleted` inmediatamente antes)

### Texto actual relacionado
```latex
\deleted[id=TUT]{Con el fin de mantener un orden lógico, el documento se organiza en capítulos.} \comment[id=TUT]{ Yo quitaría el texto porque no aporta información adicional} En el Capítulo 1 se presenta el entorno laboral, ofreciendo el contexto general de las organizaciones
  involucradas, así como información de referencia institucional y una descripción del área de trabajo y su dinámica.
```
Ubicación: `Introduccion.tex`, línea 18.

### Qué está solicitando el asesor
Eliminar la frase de relleno antes de entrar directo a describir el contenido de cada capítulo.

### Solución
Aceptar la eliminación ya marcada por el asesor.

### Texto sugerido en LaTeX
```latex
En el Capítulo 1 se presenta el entorno laboral, ofreciendo el contexto general de las organizaciones
  involucradas, así como información de referencia institucional y una descripción del área de trabajo y su dinámica.
```

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR.**

---

## C-003 — Introducción: encabezado de página desactualizado

### Comentario del asesor
```latex
\comment[id=TUT]{Ya no estás en ÍNDICE DE FIGURAS, así que hay que cambiarlo por introducción.}
```

### Texto actual relacionado
No es un problema de prosa — es el encabezado de página (running head) que no se actualiza.
`Introduccion.tex` usa `\chapter*{Introducción}` (capítulo sin numerar), y `\chapter*` no llama a
`\@mkboth`, por lo que el encabezado sigue mostrando el último título que sí lo actualizó
(`\listoffigures`).

### Qué está solicitando el asesor
Que el encabezado de las páginas de la Introducción diga "Introducción" y no "Índice de figuras".

### Solución
Agregar manualmente la actualización de marca justo después del inicio del capítulo.

### Texto sugerido en LaTeX
```latex
\chapter*{Introducción}\label{introduccion}
\markboth{}{Introducción}
```
(agregar la segunda línea inmediatamente después de la primera, que ya existe en `Introduccion.tex` línea 2)

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR.**

---

## C-004 — Introducción: quitar frase redundante sobre agradecimientos/dedicatoria

### Comentario del asesor
Sin comentario de texto adicional — marca `\deleted` directa.

### Texto actual relacionado
```latex
De manera complementaria, \deleted[id=TUT]{se incluyen apartados de agradecimientos y dedicatoria, en los que se reconoce el apoyo brindado por personas e instituciones que contribuyeron al desarrollo
  del presente trabajo.} Finalmente, se anexan las cartas laborales como evidencia documental que valida el periodo de colaboración y las funciones desempeñadas, respaldando la
  información expuesta en la memoria.
```
Ubicación: `Introduccion.tex`, línea 24.

### Qué está solicitando el asesor
Quitar información redundante (el lector ya vio agradecimientos y dedicatoria antes de la
introducción).

### Solución
Aceptar la eliminación y ajustar el conector para que la oración fluya bien sin la frase quitada.

### Texto sugerido en LaTeX
```latex
De manera complementaria, finalmente se anexan las cartas laborales como evidencia documental que valida el periodo de colaboración y las funciones desempeñadas, respaldando la
  información expuesta en la memoria.
```

### Referencia necesaria
No.

### Pregunta para el autor
¿Te parece bien el ajuste de conector ("De manera complementaria, finalmente..."), o prefieres el
resultado literal de solo aceptar el `\deleted` sin tocar nada más ("De manera complementaria,
Finalmente, se anexan...")? Es la única razón por la que no lo marco 100% listo sin más — es una
microdecisión de estilo, no bloquea nada.

### Estado
**LISTO PARA APLICAR** (con una preferencia de estilo opcional pendiente de confirmar).

---

## C-005 — Capítulo 1: afirmación sin sustento sobre Multicom

### Comentario del asesor
```latex
\comment[id=TUT]{En que te basas para dar esa afirmación, se necesitan evidencias}
```

### Texto actual relacionado
```latex
La organización cuenta con una plataforma robusta y estable,\comment[id=TUT]{En que te basas para dar esa afirmación, se necesitan evidencias} orientada a la venta de productos de prepago, tiempo aire electrónico, pago de servicios y compra de pines electrónicos.
Esta plataforma ha sido desarrollada y fortalecida a lo largo de los años, permitiendo a la empresa adaptarse a las necesidades de un mercado cambiante y ofrecer soluciones
tecnológicas confiables a sus clientes.\cite{MulticomSobreMulticomServicios}
```
Ubicación: `Capitulo1.tex`, línea 28. No aplica código de `tqaAuditorias` (es sobre Multicom, no
BeGlobal); tampoco hay repositorio de Multicom/Wali Fintech disponible para verificar en código.

### Qué está solicitando el asesor
Que la afirmación "robusta y estable" tenga respaldo — ya existe una cita en el documento, pero
respalda la oración siguiente, no esta afirmación específica.

### Solución
Reubicar la cita ya existente para que respalde directamente la afirmación, y dejar claro que es
una caracterización de la propia empresa (fuente institucional), no una evaluación independiente
del autor — salvo que Xavier confirme que tiene una base distinta.

### Texto sugerido en LaTeX
```latex
Según su información institucional, la organización cuenta con una plataforma orientada a la venta de productos de prepago, tiempo aire electrónico, pago de servicios y compra de pines electrónicos, la cual describe como robusta y estable.\cite{MulticomSobreMulticomServicios} Esta plataforma ha sido desarrollada y fortalecida a lo largo de los años, permitiendo a la empresa adaptarse a las necesidades de un mercado cambiante y ofrecer soluciones
tecnológicas confiables a sus clientes.
```

### Referencia necesaria
Sí (probablemente) — ya existe (`MulticomSobreMulticomServicios`), el ajuste es de ubicación/
atribución, no de agregar una fuente nueva.

### Preguntas para el autor
1. ¿"Robusta y estable" viene realmente de lo que dice la página web de Multicom, o es tu
   impresión personal trabajando ahí?
2. Si es personal, ¿tienes algún dato concreto que la sustente (tiempo de actividad del servicio,
   volumen de operaciones, ausencia de caídas durante tu periodo)? Si no, mejor suavizar o quitar
   el adjetivo.

### Estado
**REQUIERE RESPUESTA DEL AUTOR.**

---

## C-006 — Capítulo 1: "una organización" → "la organización"

### Comentario del asesor
Sin comentario de texto — marca `\replaced` directa.

### Texto actual relacionado
```latex
tiene como propósito crear, mantener y mejorar soluciones tecnológicas que apoyen los procesos internos o externos de \replaced[id=TUT]{la organización}{una organización}. En este contexto, el trabajo realizado no se
```
Ubicación: `Capitulo1.tex`, línea 102.

### Qué está solicitando el asesor
Corrección gramatical: referencia específica ("la organización"), no genérica ("una organización").

### Solución
Aceptar el reemplazo ya marcado.

### Texto sugerido en LaTeX
```latex
tiene como propósito crear, mantener y mejorar soluciones tecnológicas que apoyen los procesos internos o externos de la organización. En este contexto, el trabajo realizado no se
```

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR.**

---

## C-007 — Capítulo 2: sugerencia de gráfico/diagrama

### Comentario del asesor
```latex
\added[id=TUT]{Yo te sugiero incluir algún tipo de gráfico o diagrama que muestre la relación entre las actividades realizadas, las herramientas utilizadas y los aprendizajes adquiridos. Esto puede ayudar a visualizar mejor la experiencia laboral y su impacto en tu formación profesional.}
```
**Atención:** está marcado como `\added` (texto agregado) — si se acepta el cambio sin más, el
propio texto de la sugerencia del asesor quedaría impreso como si fuera prosa tuya. Hay que
**eliminar** este bloque una vez atendida la sugerencia, no aceptarlo como contenido.

### Texto actual relacionado
Ubicación: `Capitulo2.tex`, línea 12 (antes de `\section{Contexto laboral}`).

### Qué está solicitando el asesor
Un elemento visual (tabla, diagrama o línea de tiempo) que resuma la relación entre actividades,
herramientas y aprendizajes de ambas etapas.

### Solución
Recomiendo una tabla (más simple de mantener en LaTeX puro que un diagrama) con columnas: Etapa |
Actividad principal | Herramientas | Aprendizaje/competencia. No propongo el contenido todavía
porque depende de decisiones tuyas (ver preguntas).

### Texto sugerido en LaTeX
No aplica todavía — pendiente de tu decisión de formato antes de redactarlo.

### Referencia necesaria
No.

### Preguntas para el autor
1. ¿Tabla, diagrama (¿con qué herramienta: TikZ o imagen externa?) o línea de tiempo?
2. ¿Una tabla por etapa o una sola comparativa?
3. ¿Nivel de detalle por actividad general o por sub-actividad?

### Estado
**REQUIERE RESPUESTA DEL AUTOR** (decisión de formato).

---

## C-008 — Capítulo 2: cómo se implementó la asignación automática de responsables

### Comentario del asesor
```latex
\comment[id=TUT]{¿Cómo se implementó esta funcionalidad?}
```

### Texto actual relacionado
```latex
Adicionalmente, se buscó incorporar una mejora orientada a la eficiencia operativa: que el sistema pudiera apoyar en la asignación automática de responsables \comment[id=TUT]{¿Cómo se implementó esta funcionalidad?} para realizar auditorías,
  con el objetivo de distribuir la actividad de forma más organizada y reducir la coordinación manual.
```
Ubicación: `Capitulo2.tex`, línea 49.

### Qué está solicitando el asesor
El mecanismo real de la asignación automática: ¿qué criterio usa el sistema para decidir a quién
asignar?

### Verificación en código (`tqaAuditorias`)
Se revisó directamente el código fuente del proyecto. Hallazgos concretos:

- **Sí se diseñó e implementó** una función de asignación automática por departamento:
  `AuditAssigment.setUsersToAudit(departmentId, auditId, createUserId)` en
  `src/main/java/tqa/models/AuditAssigment.java` (líneas 167-196). Consulta todos los usuarios de
  un departamento (`User.getUsersByDepartmentId(departmentId)`) y crea automáticamente un registro
  de asignación (`audit_assigment`) por cada uno.
- **Pero su invocación quedó sin activar.** Los dos únicos puntos donde se llamaría a esa función
  —justo al crear una auditoría— están comentados:
  - `src/main/java/tqa/servlets/Audits.java`, línea 98:
    `//AuditAssigment.setUsersToAudit(departmentId, audit.getAuditId(), user.getUserId() );`
  - `src/main/java/tqa/servlets/AuditDepartments.java`, línea 70 (dentro de un bloque `case "add"`
    mayormente comentado también).
- **Lo que sí funcionaba y se usaba en producción** era la asignación manual: el servlet
  `AuditAssigments.java` (acción `checkBox` en `doPost`) permite marcar/desmarcar usuarios
  individuales como responsables de una auditoría, uno por uno, desde una lista de checkboxes
  (`src/main/webapp/js/addAudits.js`, función `selectUser()`, líneas 508-522 — hace
  `$.ajax POST` a `AuditAssigments` con `actionUser: "checkBox"` por cada clic).

Es decir: existió diseño, modelo de datos y una función completa para automatizar la asignación
por departamento, pero nunca se integró al flujo real; la asignación de responsables durante el
periodo de participación se hacía manualmente, usuario por usuario.

### Solución
Corregir el texto para reflejar exactamente esto: se planteó y se llegó a programar el mecanismo
automático, pero no se integró al flujo de creación de auditorías, por lo que operativamente la
asignación fue manual.

### Texto sugerido en LaTeX
```latex
Adicionalmente, se diseñó una mejora orientada a la eficiencia operativa: que el sistema pudiera asignar automáticamente a los usuarios de un departamento como responsables de una auditoría al momento de crearla, con el objetivo de distribuir la actividad de forma más organizada y reducir la coordinación manual. Esta lógica se implementó a nivel de modelo, mediante un método que consulta a los usuarios pertenecientes al departamento seleccionado y genera un registro de asignación por cada uno; sin embargo, su invocación no llegó a integrarse en el flujo de creación de auditorías durante el periodo descrito en esta memoria, por lo que la asignación de responsables se realizaba de forma manual, mediante una interfaz que permitía marcar individualmente a cada usuario como responsable de una auditoría específica.
```

### Referencia necesaria
No — es experiencia propia, verificada directamente en el código del proyecto.

### Impacto en otras secciones
Capítulo 3 (Resultados) dice "el planteamiento de una asignación automatizada de responsables
aportó una base para distribuir actividades..." — conviene revisar esa frase para que sea
consistente con "se planteó y se diseñó, pero no se integró al flujo" en vez de sugerir que quedó
operando.

### Estado
**LISTO PARA APLICAR** (verificado en código, no requiere información adicional del autor).

---

## C-009 — Capítulo 2: justificar JSON, AJAX y jQuery

### Comentario del asesor
```latex
\comment[id=TUT]{Se menciona JSON, AJAX y jQuery pero no explica porque se seleccionaron}
```

### Texto actual relacionado
```latex
En la práctica, se trabajó con operaciones tipo CRUD para administrar información base del sistema (catálogos y configuraciones).
  Para la interacción con la interfaz se utilizaron JSP apoyadas por JavaScript y librerías como jQuery, permitiendo enviar solicitudes asíncronas (AJAX) y actualizar la
  experiencia de usuario sin recargar páginas completas en cada acción. Cuando fue necesario, las respuestas se entregaban en formato JSON para facilitar su consumo desde el frontend,
  manteniendo consistencia en la comunicación entre capas. \comment[id=TUT]{Se menciona JSON, AJAX y jQuery pero no explica porque se seleccionaron}
```
Ubicación: `Capitulo2.tex`, línea 92 (subsección "Implementación de reglas de negocio y módulos
principales", dentro de 2.2.4).

### Qué está solicitando el asesor
Por qué se eligió jQuery (en vez de JavaScript puro), por qué AJAX (en vez de recarga completa) y
por qué JSON (en vez de otro formato).

### Verificación en código (`tqaAuditorias`)
Confirmado con evidencia directa:

- **jQuery venía integrado en el template de dashboard adoptado**, no fue una elección aislada:
  bajo `src/main/webapp/assets/lib/` está el conjunto completo de plugins basados en jQuery del
  template (`select2`, `parsley`, `summernote`, `sweetalert2`, `datatables`, `jquery.fullcalendar`,
  etc.) — coincide con lo que el propio Capítulo 2 ya dice sobre integrar "un template base con
  estilo tipo dashboard" (sección 2.2.3).
- **AJAX se usó sistemáticamente para no recargar la página** en operaciones de captura/consulta:
  patrón `$.ajax({type: "GET"/"POST", url: "<Servlet>", data: {...}, success: function(data){...}})`
  repetido en `src/main/webapp/js/addAudits.js` (altas/bajas de preguntas, usuarios, departamentos,
  áreas y asignaciones — ej. líneas 82-91, 251-282, 318-348, 483-521) y en otros JS del proyecto
  (`responseAudits.js`, `users.js`).
- **JSON se usó como formato de intercambio en ambos sentidos**: jQuery serializa automáticamente
  los objetos JS (`jsonGetAudit`, `jsonPostAuditAssigmentByUser`, etc.) al enviar la solicitud, y
  el backend responde en JSON explícitamente vía `super.writeJson(...)` (visible en
  `AuditAssigments.java`, líneas 46, 49, 53, 98) — un helper de la clase base `BssServlet`.

### Solución
Agregar una explicación breve, ligada a la necesidad real (evitar recargar la página en formularios
de captura de auditorías/preguntas/asignaciones) y al origen de jQuery (ya integrado en el template
adoptado), sin entrar a nivel de código.

### Texto sugerido en LaTeX
```latex
Para la interacción con la interfaz se utilizaron JSP apoyadas por JavaScript y librerías como jQuery —ya integradas en el template de dashboard adoptado—, lo que permitió enviar solicitudes asíncronas (AJAX) hacia los Servlets sin recargar la página completa en cada acción de captura o consulta (por ejemplo, al agregar preguntas, usuarios o asignaciones a una auditoría). Cuando fue necesario, las respuestas se entregaban en formato JSON, por ser un formato ligero y de fácil consumo desde JavaScript, manteniendo consistencia en la comunicación entre capas.
```

### Referencia necesaria
Opcional. La mayor parte del párrafo describe decisiones verificadas dentro del propio proyecto
(no requiere fuente). Si se quisiera respaldar la caracterización general de JSON como "formato
ligero", cabría una fuente técnica (ej. documentación oficial de JSON, `json.org`, o MDN) — no es
indispensable porque es una caracterización ampliamente aceptada y no controvertida, no una
afirmación institucional que necesite evidencia externa.

### Estado
**LISTO PARA APLICAR** (verificado en código, no requiere información adicional del autor).

---

## C-010 — Capítulo 2: ejemplo concreto en "Segundo proyecto"

### Comentario del asesor
```latex
\comment[id=TUT]{Valdría la pena poner un ejemplo concreto}
```

### Texto actual relacionado
```latex
El segundo proyecto corresponde al desarrollo y mantenimiento de una plataforma orientada a servicios digitales, construida bajo una arquitectura de microservicios.\comment[id=TUT]{Valdría la pena poner un ejemplo concreto} En este entorno se
  trabajaba con APIs REST, reglas de negocio distribuidas por servicio y persistencia de datos, por lo que era indispensable mantener consistencia en contratos, validaciones y manejo de
  errores para asegurar un funcionamiento estable.
```
Ubicación: `Capitulo2.tex`, línea 124. No aplica `tqaAuditorias` (es del proyecto de Multicom, sin
repositorio de código disponible para esta sesión).

### Qué está solicitando el asesor
Un ejemplo concreto de qué hace la plataforma o qué tipo de microservicio, en vez de la descripción
abstracta actual.

### Solución
**Nota de confidencialidad, antes de proponer texto:** según la evidencia ya documentada en
`RTI-Documentacion/analisis/ACADEMIC_DIAGNOSIS.md` (hallazgo P1-2), el proyecto real se llama
"Wali Fintech" y los microservicios documentados en las cartas/CV son Clients, Wallet, Auth y
Access — ninguno aparece hoy en el documento. No sé si es una omisión deliberada por
confidencialidad o simplemente no se incluyó. Esto determina el texto exacto.

### Texto sugerido en LaTeX
Dos versiones, según tu respuesta:

**Si se puede nombrar el proyecto/microservicios:**
```latex
El segundo proyecto corresponde al desarrollo y mantenimiento de una plataforma orientada a servicios digitales, construida bajo una arquitectura de microservicios, entre ellos los orientados a la gestión de clientes, monederos digitales (wallet), autenticación y control de acceso. En este entorno se
  trabajaba con APIs REST, reglas de negocio distribuidas por servicio y persistencia de datos...
```

**Si se debe mantener genérico por confidencialidad:**
```latex
El segundo proyecto corresponde al desarrollo y mantenimiento de una plataforma orientada a servicios digitales, construida bajo una arquitectura de microservicios, entre ellos uno responsable de gestionar el saldo y las transacciones de cuentas digitales de los usuarios. En este entorno se
  trabajaba con APIs REST, reglas de negocio distribuidas por servicio y persistencia de datos...
```

### Referencia necesaria
No.

### Preguntas para el autor
1. ¿Se puede nombrar "Wali Fintech" y los microservicios (Clients, Wallet, Auth, Access), o hay
   confidencialidad de por medio con Multicom/el cliente?
2. Si sí, ¿hay alguna funcionalidad específica de la que te sientas cómodo dando más detalle?

### Estado
**REQUIERE RESPUESTA DEL AUTOR.**

---

## C-011 — Capítulo 2: justificar la versión .NET 10

### Comentario del asesor
```latex
\comment[id=TUT]{Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?}
```

### Texto actual relacionado
```latex
Dentro de las actividades del proyecto se participó en tareas de actualización tecnológica, enfocadas en migrar servicios desarrollados en .NET 6 hacia versiones más recientes
  como .NET 10. \comment[id=TUT]{Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?}Esta actualización requirió identificar incompatibilidades, reemplazar funciones obsoletas y ajustar dependencias para mantener la correcta compilación y ejecución de
  los servicios.
```
Ubicación: `Capitulo2.tex`, línea 213-214. Proyecto de Multicom, sin repositorio de código
disponible.

### Qué está solicitando el asesor
Justificar por qué se migró específicamente hasta .NET 10 y no una versión LTS anterior, y si ya
es estable / si había una funcionalidad indispensable que la requiriera.

### Solución
Agregar 1-2 oraciones con el motivo real de la elección de versión.

### Texto sugerido en LaTeX
No propongo texto todavía — no hay evidencia en `_analisis_texto/` (la carta solo dice que se
migró "hacia versiones más recientes como .NET Core 10", sin explicar el porqué) y sin el
repositorio de código de Multicom no puedo verificarlo de forma independiente.

### Referencia necesaria
No — es una decisión técnica del proyecto, no una afirmación general sobre .NET.

### Preguntas para el autor
1. ¿Por qué se eligió migrar hasta .NET 10 específicamente (y no una LTS anterior como .NET 8)?
2. ¿La decisión fue tuya o del equipo/liderazgo técnico?
3. ¿Había alguna funcionalidad concreta de .NET 10 necesaria, o fue política general de "mantenerse
   en la versión más reciente"?

### Estado
**REQUIERE RESPUESTA DEL AUTOR.**

---

## C-012 — Capítulo 2: AWS Lambda Node.js 20.x → 24.x (justificar y verificar evidencia)

### Comentario del asesor
```latex
\comment[id=TUT]{Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?}
```

### Texto actual relacionado
```latex
Como parte de actividades de mantenimiento y actualización tecnológica, se realizó la migración de funciones serverless desplegadas en AWS Lambda, actualizando el runtime de Node.js
  de la versión 20.x a la 24.x. \comment[id=TUT]{Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?} Esta tarea tuvo como objetivo mantener compatibilidad con versiones soportadas...
```
Ubicación: `Capitulo2.tex`, línea 223-224. Proyecto de Multicom, sin repositorio de código
disponible para verificar.

### Qué está solicitando el asesor
Misma pregunta que C-011, aplicada a esta migración de runtime.

### Solución
Antes de justificar la versión, hace falta confirmar que la actividad ocurrió tal como está
descrita: **no aparece en ninguna de las cartas, el informe de actividades ni el CV** en
`_analisis_texto/` (toda la evidencia sobre AWS ahí se refiere a API Gateway, CDK, Route53,
AppRunner y Cognito — nunca a Lambda/Node.js).

### Texto sugerido en LaTeX
No propongo texto todavía — depende de la verificación.

### Referencia necesaria
No para la justificación de versión (experiencia propia). Si se agrega contexto sobre la política
de deprecación de runtimes de AWS Lambda, ahí sí convendría una fuente oficial de AWS — no se buscó
todavía porque depende de si esta sección se conserva.

### Preguntas para el autor
1. **Verificación:** ¿esta migración realmente ocurrió como se describe? No aparece en ninguna
   carta/CV.
2. Si sí ocurrió: ¿por qué la versión 24.x específicamente?
3. ¿Fue decisión tuya o AWS forzó el fin de soporte de la versión anterior (común en Lambda)?

### Estado
**REQUIERE VERIFICACIÓN + REQUIERE RESPUESTA DEL AUTOR.**

---

## C-013 — Capítulo 3: explicar Atributos de Egreso (AE) y Objetivos Educacionales (OE)

### Comentario del asesor
```latex
\comment[id=TUT]{Explica brevemente qué son los Atributos de Egreso y Objetivos Educacionales, para que el lector entienda la relación.}
```

### Texto actual relacionado
```latex
Finalmente, se establece la relación entre la formación académica recibida
  y su aplicación en problemas reales del ámbito laboral, vinculando estos elementos con los Atributos de Egreso (AE) y los Objetivos Educacionales (OE) del programa.\comment[id=TUT]{Explica brevemente qué son los Atributos de Egreso y Objetivos Educacionales, para que el lector entienda la relación.}
```
Ubicación: `Capitulo3.tex`, línea 7.

### Qué está solicitando el asesor
Definir brevemente AE y OE antes de usarlos.

### Solución
Se revisó `Capitulo4.tex`/`Capitulo5.tex` (huérfanos, no incluidos en `tesis.tex`) buscando una
definición reutilizable. **No existe texto de definición real** — solo un párrafo genérico de
"perfil de egreso" y dos enlaces a videos de YouTube ("Ver vídeo"), sin contenido textual propio.
No hay ninguna fuente en el repositorio con el listado real de AE/OE.

### Texto sugerido en LaTeX
No propongo texto — inventar la definición de AE/OE violaría la regla de no inventar información
institucional.

### Referencia necesaria
Sí — documento oficial del programa (institucional, no bibliografía externa).

### Preguntas para el autor
1. ¿Tienes el documento oficial (o el contenido de los videos ya referenciados en `Capitulo5.tex`)
   con el listado real de AE/OE del programa de Ingeniería en Sistemas Computacionales?
2. ¿Hay algún AE/OE que sientas más relacionado con tu experiencia? (varias competencias ya listadas
   en la sección "Conclusiones" podrían conectarse una vez que tengamos el listado oficial, en vez
   de escribir contenido nuevo desde cero).

### Estado
**REQUIERE RESPUESTA DEL AUTOR** (documento oficial).

---

## C-014 — Capítulo 3: mayúsculas y acento en "Ingeniería en Sistemas Computacionales"

### Comentario del asesor
```latex
\comment[id=TUT]{En este caso debe de ir la primer letra de cada palabra en mayúscula, excepto preposiciones y conjunciones.}
```

### Texto actual relacionado
```latex
En conjunto, se concluye que la experiencia profesional descrita aportó un impacto significativo en el desarrollo técnico y profesional, fortaleciendo la preparación para integrarse
  de manera competente al entorno laboral de la ingenieria en sistemas computacionales.\comment[id=TUT]{En este caso debe de ir la primer letra de cada palabra en mayúscula, excepto preposiciones y conjunciones.}
```
Ubicación: `Capitulo3.tex`, línea 58-59.

### Qué está solicitando el asesor
Formato de nombre propio: "Ingeniería en Sistemas Computacionales" (con acento y mayúsculas
iniciales).

### Solución
Corrección ortográfica directa.

### Texto sugerido en LaTeX
```latex
En conjunto, se concluye que la experiencia profesional descrita aportó un impacto significativo en el desarrollo técnico y profesional, fortaleciendo la preparación para integrarse
  de manera competente al entorno laboral de la Ingeniería en Sistemas Computacionales.
```

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR.**

---

## C-015 — Bibliografía: falta más bibliografía técnica

### Comentario del asesor
```latex
\comment[id=TUT]{Hace falta más bibliografía, por ejemplo de la tecnología referenciada}
```

### Texto actual relacionado
```latex
\bibliography{referencias} \comment[id=TUT]{Hace falta más bibliografía, por ejemplo de la tecnología referenciada}
```
Ubicación: `tesis.tex`, línea 142.

### Qué está solicitando el asesor
`referencias.bib` solo tiene 2 citas activas, ambas al mismo sitio web de Multicom. No hay fuentes
técnicas sobre Arquitectura Limpia, MVC, REST, microservicios, etc.

### Solución
Agregar entradas `.bib` reales (no inventadas) para los conceptos técnicos generales usados en el
documento. Ver detalle completo en `RTI-Documentacion/bibliografia/BIBLIOGRAPHY_AUDIT.md`.

### Texto sugerido en LaTeX
No se genera ninguna entrada `.bib` todavía — regla explícita de no inventar referencias, DOIs,
autores ni libros.

### Uso dentro del `.tex` (una vez que existan las entradas)
```latex
...siguiendo principios de Arquitectura Limpia\cite{clean_architecture} para separar responsabilidades entre las distintas capas del sistema.
```
(ejemplo de dónde iría la cita, no la clave real todavía)

### Referencia necesaria
Sí, es justamente el objeto de esta corrección.

### Preguntas para el autor
1. ¿Tienes en mente alguna fuente que hayas usado realmente para Arquitectura Limpia, MVC o REST
   (libro de alguna materia, documentación oficial de Microsoft/.NET, "Clean Architecture" de
   Robert C. Martin, algún curso)? Si la usaste de verdad, la citamos — si no, buscamos opciones
   juntos y las revisas antes de que se agreguen.
2. ¿`Kaplan2009` (ya existe en el `.bib`, sin usar) se conecta con "Análisis de requerimientos y
   diseño inicial de base de datos" del Capítulo 2, o se elimina por no ser relevante?

### Estado
**REQUIERE FUENTE.**

---

## C-016 — Anexo institucional: incluir título del director en la firma

### Comentario del asesor
```latex
\comment[id=TUT]{Incluir mi título M. en C.}
```

### Texto actual relacionado
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
Ubicación: `tesis.cls`, línea 480 (macro `\approvalpage`, carta "Liberación de Asesoría").

### Qué está solicitando el asesor
Que su título "M. en C." aparezca junto a su nombre en esta firma — ya aparece en la portada
(`\maketitle` usa `\@directortitle\ \@director`), pero aquí solo se imprime `\@director`.

### Solución
Usar `\@directortitle` igual que en `\maketitle`.

### Texto sugerido en LaTeX
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

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR.**

---

# Preguntas que necesito responder

Consolidado, agrupadas por comentario:

- **C-004:** ¿ajuste de conector o texto literal tras aceptar el `\deleted`? (no bloqueante)
- **C-005:** ¿"robusta y estable" viene de la web de Multicom o es tu impresión? ¿Algún dato que la
  sustente?
- **C-007:** ¿tabla, diagrama o línea de tiempo? ¿por etapa o comparativa? ¿nivel de detalle?
- **C-010:** ¿se puede nombrar "Wali Fintech" y los microservicios, o hay confidencialidad?
  ¿alguna funcionalidad específica que puedas detallar?
- **C-011:** ¿por qué .NET 10 específicamente? ¿decisión tuya o del equipo?
- **C-012:** ¿la migración de AWS Lambda realmente ocurrió? Si sí, ¿por qué 24.x y quién decidió?
- **C-013:** ¿tienes el documento oficial (o el contenido de los videos referenciados) con el
  listado real de AE/OE del programa?
- **C-015:** ¿qué fuente(s) reales usaste para Arquitectura Limpia/MVC/REST/microservicios?
  ¿se conecta `Kaplan2009` con la sección de requerimientos o se elimina?

# Ruta del documento

`C:\Proyects\RTI-Docs\RTI-Documentacion\correcciones\correcciones.md`
